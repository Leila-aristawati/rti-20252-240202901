# WS-07: Experimental Design & Validity

> **Bab 7 — Experimental Design & Validity**

---

## Ringkasan Materi

### Correlation ≠ Causality

Kausalitas membutuhkan 3 syarat:
1. **Covariance** — X dan Y bergerak bersama
2. **Temporal precedence** — X berubah sebelum Y
3. **Elimination of alternatives** — Tidak ada faktor lain yang menjelaskan Y

Controlled experiment adalah satu-satunya metode yang bisa membuktikan kausalitas.

### Empat Jenis Validitas

| Jenis | Pertanyaan | Ancaman Umum |
|-------|-----------|-------------|
| **Internal** | Apakah hubungan IV→DV nyata? | Confounding variable, selection bias |
| **External** | Apakah bisa digeneralisasi? | Dataset terlalu spesifik |
| **Construct** | Apakah mengukur konsep yang benar? | Metrik tidak sesuai |
| **Conclusion** | Apakah kesimpulan statistik valid? | Sample size kecil, uji salah |

Internal dan external validity sering berkonflik: semakin terkontrol (internal kuat) → semakin artificial (external lemah).

### Tiga Tipe Eksperimen dalam Riset TI

| Tipe | Deskripsi | Kapan Digunakan |
|------|----------|----------------|
| **Comparison Study** | Metode A vs B pada kondisi identik | Membandingkan pendekatan berbeda |
| **Ablation Study** | Full system → lepas komponen satu per satu | Mengukur kontribusi tiap komponen |
| **Parameter Study** | Variasikan satu parameter, amati dampak | Uji sensitifitas/robustness |

### Fairness dalam Perbandingan

Perbandingan yang adil = **kondisi identik** untuk semua metode: dataset sama, preprocessing sama, tuning effort sebanding, environment sama, metrik sama.

Contoh tidak adil: Transformer (30 fitur tambahan + Bayesian optimization) vs RF (default params) → hasilnya misleading.

### Threats to Validity = Diidentifikasi Sebelum Eksperimen

Ancaman validitas harus diidentifikasi **sebelum** eksperimen dan mitigasinya dirancang sebagai bagian dari desain — bukan ditulis sebagai boilerplate setelah selesai.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan testing | Memastikan sistem memenuhi requirement | Membuktikan hubungan kausal antar variabel |
| Baseline | Versi sebelumnya (last release) | Metode tervalidasi dari literatur |
| Kegagalan | Bug → fix → release | H₀ tidak ditolak → tetap kontribusi ilmiah |
| Sukses | 100% test pass | Evidence valid — mendukung atau menolak hipotesis |

### Istilah Penting

- **Causality** — Hubungan sebab-akibat (covariance + temporal + elimination)
- **Controlled Experiment** — Ubah satu variabel, kontrol sisanya, amati efek
- **Fairness** — Semua metode diuji pada kondisi yang benar-benar identik
- **Threats to Validity** — Faktor yang bisa melemahkan kesimpulan jika tidak dimitigasi
- **Conclusion Validity** — Validitas statistik: power, sample size, uji yang tepat

---

## Template A.7 — Desain Eksperimen Lengkap

```
EXPERIMENT DESIGN

Research Question : Apakah literasi digital, keterbatasan anggaran, dan dukungan infrastruktur teknologi secara signifikan mempengaruhi kinerja UMKM di Indonesia, diukur menggunakan SEM-PLS
Hypothesis        : 
  H₀₁: Literasi digital tidak berpengaruh signifikan terhadap kinerja UMKM di Indonesia
  H₁₁: Literasi digital berpengaruh signifikan positif terhadap kinerja UMKM di Indonesia
  H₀₂: Keterbatasan anggaran tidak berpengaruh signifikan terhadap kinerja UMKM di Indonesia
  H₁₂: Keterbatasan anggaran berpengaruh signifikan negatif terhadap kinerja UMKM di Indonesia
  H₀₃: Dukungan infrastruktur tidak berpengaruh signifikan terhadap kinerja UMKM di Indonesia
  H₁₃: Dukungan infrastruktur berpengaruh signifikan positif terhadap kinerja UMKM di Indonesia
Tipe Eksperimen   : [ ] Comparison  [✔] Ablation  [ ] Parameter

Kondisi Eksperimen:
| Kondisi | Deskripsi | IV Value | CV Settings |
|---------|-----------|----------|-------------|
| Full Model  | Semua 3 variabel IV dimasukkan ke model SEM-PLS | X₁ + X₂ + X₃ → Y                            | 150 responden, stratified random sampling, α=0,05 |
| – X₁        | Model tanpa Literasi Digital                   | X₂ + X₃ → Y                                  | Kondisi lain tetap sama                          |
| – X₂        | Model tanpa Keterbatasan Anggaran              | X₁ + X₃ → Y                                  | Kondisi lain tetap sama                          |
| – X₃        | Model tanpa Dukungan Infrastruktur             | X₁ + X₂ → Y                                  | Kondisi lain tetap sama                          |

Fairness Checklist:
  [✔] Dataset identik untuk semua kondisi — kuesioner yang sama (150 responden)
  [✔] Preprocessing setara — semua data melalui uji validitas & reliabilitas yang sama
  [✔] Tuning effort setara — semua kondisi dianalisis dengan SmartPLS 3.0 tanpa penyesuaian manual
  [✔] Environment identik — SmartPLS 3.0, threshold t-value > 1,96, α = 0,05
  [✔] Metrik evaluasi sama — path coefficient (β), t-value, dan R² untuk semua kondisi
  
Threat Analysis:
| Threat Type | Ancaman Spesifik | Mitigasi |
|-------------|-----------------|----------|
| Internal    | Common method bias — IV dan DV diukur dari responden yang sama (self-report)  | Menggunakan Harman's single factor test untuk mendeteksi common method bias                   |
| External    | Sampel mungkin tidak merata dari seluruh wilayah Indonesia — hasil mungkin tidak merepresentasikan semua konteks  | Menyatakan secara eksplisit batasan generalisasi; merekomendasikan replikasi dengan sampel dari berbagai wilayah Indonesia     |
| Construct   | Responden salah memahami item kuesioner — jawaban tidak mencerminkan konsep   | Pilot test kuesioner pada 10–15 responden sebelum penyebaran massal                          |
| Conclusion  | Sampel 150 mungkin tidak cukup untuk mendeteksi efek kecil                   | Menggunakan G*Power untuk menghitung minimum sample size yang dibutuhkan sebelum pengumpulan  |
Statistical Plan:
  Uji statistik    :SEM-PLS (Structural Equation Modelling - Partial Least Squares) menggunakan SmartPLS 3.0; bootstrapping 5000 iterasi untuk t-value 
  Justifikasi      : SEM-PLS sesuai untuk data ordinal (Likert), sampel relatif kecil, dan model dengan multiple IV → DV, konsisten dengan baseline
  Alpha            : α = 0,05 (t-value > 1,96)
  Effect size min  : R² ≥ 0,26 (medium effect size menurut Cohen, 1988)
```

---

## Latihan 1 — Desain Eksperimen

Susun desain eksperimen berdasarkan RQ, variabel, dan sistem dari WS-04 sampai WS-06.

**RQ:** Apakah literasi digital, keterbatasan anggaran, dan dukungan infrastruktur teknologi
secara signifikan mempengaruhi kinerja UMKM di Kota Bandung?
**Tipe eksperimen:** [ ] Comparison / [✔] Ablation / [ ] Parameter

| Kondisi | Deskripsi | IV Value | CV Settings |
|---------|-----------|----------|-------------|
| Full Model | Semua 3 variabel IV dimasukkan ke model SEM-PLS | X₁ + X₂ + X₃ → Y | 150 responden, stratified sampling, α = 0,05, SmartPLS 3.0 |
| – X₁ | Model tanpa Literasi Digital | X₂ + X₃ → Y | Semua kondisi lain tetap sama |
| – X₂ | Model tanpa Keterbatasan Anggaran | X₁ + X₃ → Y | Semua kondisi lain tetap sama |
| – X₃ | Model tanpa Dukungan Infrastruktur | X₁ + X₂ → Y | Semua kondisi lain tetap sama |

---

## Latihan 2 — Fairness Checklist

Evaluasi apakah desain eksperimen di Latihan 1 sudah fair.

| Kriteria | Status | Detail |
|----------|--------|--------|
| Dataset identik | ✅ | Semua kondisi menggunakan data kuesioner yang sama dari 150 responden UMKM Kota Bandung |
| Preprocessing setara | ✅ | Semua kondisi melalui uji outer model (validitas & reliabilitas) yang identik di SmartPLS 3.0 |
| Tuning effort setara | ✅ | Tidak ada penyesuaian manual pada model; semua kondisi menggunakan default bootstrapping 5000 iterasi |
| Environment identik | ✅ | Semua kondisi dianalisis menggunakan SmartPLS 3.0 dengan threshold yang sama (α = 0,05, t-value > 1,96) |
| Metrik evaluasi sama | ✅ | Path coefficient (β), t-value, dan R² digunakan secara konsisten untuk semua kondisi |

**Ada yang tidak fair?** [ ] Ya / [✔] Tidak
> Jika ya, bagaimana cara memperbaikinya? ________________

---

## Latihan 3 — Threat Analysis

Identifikasi ancaman validitas untuk desain eksperimen ini.

| Threat Type | Ancaman Spesifik | Mitigasi |
|-------------|-----------------|----------|
| Internal | Common method bias — semua variabel (IV dan DV) diukur dari sumber yang sama (self-report kuesioner), sehingga korelasi bisa artifisial | Melakukan Harman's single factor test; memisahkan pengukuran IV dan DV dalam sesi pengisian yang berbeda jika memungkinkan |
| External | Sampel mungkin tidak merata dari seluruh wilayah Indonesia — hasil tidak bisa langsung digeneralisasi ke semua segmen UMKM | Menyatakan batasan generalisasi secara eksplisit di bagian keterbatasan penelitian; merekomendasikan replikasi dengan sampel yang lebih merata dari berbagai wilayah Indonesia |
| Construct | Item kuesioner mungkin tidak dipahami dengan benar oleh pelaku UMKM — terutama item tentang literasi digital yang bersifat teknis | Pilot test kuesioner pada 10–15 responden UMKM sebelum penyebaran massal; revisi item yang tidak dipahami |
| Conclusion | Jumlah sampel 150 mungkin tidak memiliki statistical power yang cukup untuk mendeteksi efek kecil | Melakukan power analysis menggunakan G*Power sebelum pengumpulan data untuk memastikan sampel memadai |


**Ancaman mana yang paling sulit dimitigasi?** Internal Validity — Common Method Bias
**Mengapa?**
> Common method bias sulit dimitigasi sepenuhnya karena dalam penelitian survei,
> sangat sulit untuk memisahkan pengukuran IV dan DV dari responden yang sama.
> Meskipun Harman's single factor test bisa mendeteksinya, tidak ada cara yang
> benar-benar menghilangkan bias ini dalam desain cross-sectional survey.
> Ini adalah keterbatasan inheren dari metode survei yang harus diakui secara
> transparan dalam laporan penelitian.
---

## Refleksi

> Sebuah paper melaporkan "metode kami mengalahkan semua baseline." Apa 3 pertanyaan pertama yang harus diajukan untuk mengevaluasi klaim ini?

**Jawaban:**
1. **Apakah kondisi perbandingan sudah fair?**
   Apakah semua metode diuji pada dataset yang sama, preprocessing yang sama, dan
   tuning effort yang sebanding? Atau metode mereka mendapat keuntungan tambahan
   (lebih banyak fitur, hyperparameter tuning lebih intensif) dibanding baseline?

2. **Apakah metrik yang digunakan tepat dan tidak cherry-picked?**
   Apakah metrik dipilih sebelum eksperimen atau setelah melihat hasil? Apakah
   hanya melaporkan metrik yang menguntungkan mereka dan menyembunyikan metrik
   lain yang mungkin tidak signifikan?

3. **Apakah hasil statistik signifikan secara praktis, bukan hanya statistik?**
   Berapa effect size-nya? Apakah perbedaan performa cukup besar untuk bermakna
   secara praktis, atau hanya signifikan karena sample size yang sangat besar
   sehingga perbedaan kecil pun tampak signifikan secara statistik?