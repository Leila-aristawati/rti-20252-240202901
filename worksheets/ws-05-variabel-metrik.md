# WS-05: Variabel & Metrik

> **Bab 5 — Metric, Measurement & Data**

---

## Ringkasan Materi

### Measurement Alignment Model

Setiap pengukuran yang valid harus bisa ditelusuri melalui rantai ini tanpa lompatan logis:

```
Problem → Concept → Variable → Metric → Data → Result
```

### Operationalization = Keputusan Desain

Menerjemahkan konsep abstrak menjadi variabel terukur bukan proses mekanis. "Code quality" yang diukur via SonarQube code smells membawa asumsi implisit. Setiap operasionalisasi harus didokumentasikan dan dijustifikasi.

### Empat Tipe Data (NOIR)

| Tipe | Ciri | Contoh | Operasi Valid |
|------|------|--------|---------------|
| **Nominal** | Kategori, tanpa urutan | Jenis algoritma (RF, SVM, CNN) | Modus, chi-square |
| **Ordinal** | Urutan, interval tidak sama | Skala Likert (1-5) | Median, Spearman |
| **Interval** | Jarak bermakna, tanpa nol absolut | Suhu Celsius | Mean, Pearson, t-test |
| **Ratio** | Jarak bermakna + nol absolut | Waktu eksekusi (ms) | Semua operasi |

Tipe data menentukan uji statistik yang valid. Kebanyakan metrik performa TI = ratio; persepsi pengguna = ordinal.

### Kriteria Pemilihan Metrik

- **Representative** — Mewakili konsep yang diteliti
- **Sensitive** — Cukup peka menangkap perbedaan bermakna (hindari ceiling effect)
- **Feasible** — Bisa dikumpulkan dalam batasan waktu dan biaya

### Pre-registration

Metrik harus ditentukan **sebelum** eksperimen. Memilih metrik setelah melihat data = **p-hacking**. Metrik tambahan yang ditemukan kemudian dilaporkan sebagai *exploratory*, bukan *confirmatory*.

### Primary vs Secondary Metric

- **Primary Metric** — Langsung terikat ke hipotesis, menentukan kesimpulan
- **Secondary Metric** — Pendukung, dilaporkan di samping primary; statusnya suplementer

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Pemilihan metrik | Berdasarkan kebiasaan/tool yang ada | Berdasarkan construct validity |
| Anomali | Dihapus untuk laporan bersih | Diinvestigasi — bisa jadi temuan |
| Kapan dipilih | Setelah sistem jadi (monitoring) | Sebelum eksperimen (by design) |

### Istilah Penting

- **Operationalization** — Transformasi konsep abstrak menjadi variabel terukur
- **Construct Validity** — Sejauh mana pengukuran benar-benar mengukur konsep yang dimaksud
- **Measurement Scale** — Klasifikasi data (NOIR) yang menentukan analisis valid
- **Multi-metric Evaluation** — Menggunakan beberapa metrik untuk menangkap konsep kompleks

---

## Template A.5 — Definisi Variabel, Metrik & Justifikasi

```
VARIABLE & METRIC DEFINITION

Research Question:   Apakah literasi digital, keterbatasan anggaran, dan dukungan infrastruktur teknologi secara signifikan mempengaruhi kinerja UMKM di Kota Bandung, diukur menggunakan SEM-PLS pada 150 responden?

| Variabel | Tipe | Konsep | Metrik | Skala | Satuan | Cara Mengukur | Justifikasi |
|----------|------|--------|--------|-------|--------|---------------|-------------|
| Literasi Digital      | IV   | Kemampuan pelaku UMKM dalam menggunakan teknologi digital | Skor rata-rata 5 item kuesioner   | Ordinal | Skala 1–5     | Kuesioner Likert 5 poin (sangat tidak setuju–sangat setuju) | Literasi digital terbukti sebagai hambatan utama adopsi teknologi pada UMKM |
| Keterbatasan Anggaran | IV   | Kemampuan finansial UMKM untuk berinvestasi pada teknologi | Skor rata-rata 4 item kuesioner  | Ordinal | Skala 1–5     | Kuesioner Likert 5 poin                            | Keterbatasan modal dan anggaran menjadi salah satu kelemahan utama UMKM dalam mengadopsi teknologi digital |
| Dukungan Infrastruktur| IV   | Ketersediaan internet dan perangkat teknologi di lingkungan UMKM | Skor rata-rata 4 item kuesioner | Ordinal | Skala 1–5     | Kuesioner Likert 5 poin                            | Infrastruktur TI yang belum memadai menjadi penghambat signifikan terutama di luar pusat kota |
| Kinerja UMKM          | DV   | Tingkat efisiensi, produktivitas, dan pertumbuhan usaha UMKM | Path coefficient (β) & t-value  | Ordinal | Skala 1–5 / t-value | Kuesioner Likert 5 poin + analisis SEM-PLS (SmartPLS 3.0) | Kinerja UMKM diukur secara persepsional melalui self-report yang umum digunakan pada penelitian sejenis |

Alignment Check:
  RQ → Concept → Variable → Metric → Data → Result
  [✔] Setiap langkah terdokumentasi
  [✔] Tidak ada "lompatan logis"
  [✔] Metrik mengukur apa yang dimaksud (construct validity)
```

---

## Latihan 1 — Operationalization Chain

Gunakan RQ dari WS-04. Definisikan variabel dan metriknya.

**RQ:** Apakah literasi digital, keterbatasan anggaran, dan dukungan infrastruktur teknologi
secara signifikan mempengaruhi kinerja UMKM di Kota Bandung, diukur menggunakan
SEM-PLS pada 150 responden?

| Variabel | Tipe | Konsep Abstrak | Metrik Konkret | Skala (NOIR) | Satuan |
|----------|------|---------------|----------------|-------------|--------|
| Literasi Digital | IV | Kemampuan pelaku UMKM menggunakan teknologi digital dalam operasional bisnis | Skor rata-rata 5 item kuesioner Likert | Ordinal | Skala 1–5 |
| Keterbatasan Anggaran | IV | Kemampuan finansial UMKM untuk berinvestasi pada teknologi | Skor rata-rata 4 item kuesioner Likert | Ordinal | Skala 1–5 |
| Dukungan Infrastruktur | IV | Ketersediaan internet dan perangkat teknologi di lingkungan UMKM | Skor rata-rata 4 item kuesioner Likert | Ordinal | Skala 1–5 |
| Kinerja UMKM | DV | Tingkat efisiensi operasional, produktivitas, dan pertumbuhan pendapatan usaha | Path coefficient (β), t-value, R² dari SEM-PLS | Ordinal | Skala 1–5 |
| Ukuran Usaha | CV | Klasifikasi UMKM (mikro/kecil/menengah) yang dapat mempengaruhi kinerja | Kategori berdasarkan UU No. 20 Tahun 2008 | Nominal | Kategori |

**Apakah ada lompatan logis dalam rantai?** [ ] Ya / [✔] Tidak
> Jika ya, di mana? ____________________________________

---

## Latihan 2 — Evaluasi Metrik

Evaluasi metrik DV yang dipilih di Latihan 1 menggunakan 3 kriteria.

| Kriteria | Skor (1-5) | Justifikasi |
|----------|-----------|-------------|
| Representative | 5 | Path coefficient langsung menunjukkan besar dan arah pengaruh setiap variabel IV terhadap kinerja UMKM (DV), sehingga sangat mewakili konsep yang diteliti |
| Sensitive | 4 | SEM-PLS cukup peka menangkap perbedaan pengaruh antar variabel; namun sensitifitasnya bergantung pada kualitas instrumen kuesioner yang digunakan |
| Feasible | 5 | Data dikumpulkan melalui kuesioner yang relatif mudah disebar ke 150 responden; analisis menggunakan SmartPLS 3.0 yang tersedia gratis (Student License) |

**Apakah perlu secondary metric?** [✔] Ya / [ ] Tidak
> Jika ya, apa dan mengapa? Secondary metric: **R² (koefisien determinasi). Alasan: R² menunjukkan seberapa besar variansi kinerja UMKM yang bisa dijelaskan oleh ketiga variabel IV secara bersama-sama. Ini melengkapi path coefficient yang hanya menunjukkan pengaruh per variabel. Baseline R² adalah 0,492, penelitian ini menargetkan R² yang lebih tinggi dengan variabel yang lebih terfokus.

**Contoh kasus ceiling effect untuk metrik ini:**
> Ceiling effect bisa terjadi jika mayoritas responden memberikan skor 4–5 pada semua
> item kuesioner (terlalu positif), sehingga tidak ada variasi yang cukup untuk
> mendeteksi perbedaan pengaruh antar variabel. Mitigasi: pastikan item kuesioner
> mencakup pernyataan negatif (reverse scoring) untuk mendorong variasi jawaban.


---

## Latihan 3 — Data Quality Check

Bayangkan data yang akan dikumpulkan dari eksperimen. Evaluasi 4 dimensi kualitas data.

| Dimensi | Pertanyaan | Jawaban | Strategi Mitigasi |
|---------|-----------|---------|------------------|
| Completeness | Apakah semua data point terkumpul? | Belum tentu, ada kemungkinan kuesioner tidak diisi lengkap oleh responden | Menetapkan minimum 150 responden valid; kuesioner yang tidak lengkap (>10% kosong) akan dibuang dan diganti |
| Consistency | Apakah ada kontradiksi internal? | Mungkin terjadi, responden bisa memberikan jawaban tidak konsisten antar item yang mengukur konsep sama | Menggunakan uji composite reliability dan Cronbach's Alpha (≥ 0,7) untuk mendeteksi inkonsistensi instrumen |
| Validity | Apakah benar-benar mengukur yang dimaksud? | Perlu diverifikasi, item kuesioner harus benar-benar mengukur literasi digital, anggaran, infrastruktur, dan kinerja UMKM | Melakukan uji validitas konvergen (outer loading ≥ 0,708, AVE ≥ 0,5) menggunakan SmartPLS sebelum analisis utama |
| Representativeness | Apakah sampel mewakili populasi target? | Belum tentu,150 responden harus proporsional mewakili mikro, kecil, dan menengah | Menggunakan stratified random sampling berdasarkan klasifikasi UMKM (mikro/kecil/menengah) agar proporsional |

---

## Refleksi

> Mengapa memilih metrik setelah melihat data dianggap p-hacking? Apa bedanya dengan eksplorasi data yang sah?

**Jawaban:**
> Memilih metrik setelah melihat data dianggap p-hacking karena peneliti bisa secara
> tidak sadar (atau sengaja) memilih metrik yang menghasilkan hasil signifikan, bukan
> metrik yang paling valid secara konseptual. Ini menciptakan ilusi bahwa hipotesis
> terbukti padahal sebenarnya hanya kebetulan statistik.
> Bedanya dengan eksplorasi data yang sah: eksplorasi data boleh dilakukan untuk
> menemukan pola baru, tetapi hasilnya harus dilaporkan sebagai temuan *exploratory*
> (bukan *confirmatory*), dan tidak boleh diklaim sebagai bukti pengujian hipotesis
> yang sudah ditetapkan sebelumnya. Metrik utama untuk pengujian hipotesis tetap
> harus ditetapkan sebelum data dikumpulkan (pre-registration).
