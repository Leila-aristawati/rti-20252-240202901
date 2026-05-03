# WS-04: Research Question & Hypothesis

> **Bab 4 — Research Question, Contribution & Hypothesis**

---

## Ringkasan Materi

### RQ Bukan Pertanyaan Biasa

Research Question yang baik secara implisit mengandung cetak biru eksperimen: subjek, baseline, metrik, domain, dataset.

| Kualitas | Contoh |
|----------|--------|
| **Buruk** | "Bagaimana pengaruh deep learning terhadap deteksi malware?" |
| **Baik** | "Apakah CNN menghasilkan F1-Score lebih tinggi dari RF pada CIC-MalMem-2022?" |

Perbedaan: RQ yang baik menyebutkan **metode spesifik**, **metrik terukur**, **baseline**, dan **dataset**.

### Tiga Jenis RQ

| Jenis | Pola | Kebutuhan |
|-------|------|-----------|
| **Comparison** | A vs B → mana lebih baik? | ≥ 2 metode, metrik sama |
| **Improvement** | A' vs A → modifikasi lebih baik? | Pre/post, bukti perbaikan |
| **Exploratory** | Faktor X₁...Xₙ → pengaruh terhadap Y? | Multi-variabel, korelasi/regresi |

### Contribution Statement

Tiga jenis kontribusi: **Improvement** (metode terbukti lebih baik), **Comparison** (perbandingan sistematis yang belum ada), **Novel Approach** (pendekatan baru). Kontribusi harus terhubung langsung dengan gap — kontribusi tanpa gap = klaim tanpa justifikasi.

### Hypothesis H₀ / H₁

- **H₀** (Null) = Tidak ada perbedaan signifikan — asumsi default, harus dibuktikan salah
- **H₁** (Alternative) = Ada perbedaan signifikan — diterima hanya jika H₀ ditolak
- Harus **falsifiable**, mengandung **metrik terukur**, dirumuskan **SEBELUM eksperimen**

### Rantai Operasionalisasi

```
RQ → Variable → Metric → Data → Analysis
```

Jika rantai ini tidak lengkap, RQ belum mature. Bi-directional: RQ yang tidak bisa jadi hipotesis testable harus direvisi mundur.

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan pertanyaan | Apa yang harus dibangun? | Apa yang harus dibuktikan? |
| Bentuk jawaban | Sistem yang berfungsi | Bukti empiris terukur |
| Sukses diukur oleh | User satisfaction, uptime | Signifikansi statistik, effect size |
| Jika gagal | Debug dan perbaiki | Laporkan, analisis mengapa |

### Istilah Penting

- **Research Question (RQ)** — Pertanyaan spesifik: variabel terukur + metrik + konteks
- **Contribution Statement** — Apa yang diketahui setelah riset selesai yang sebelumnya belum ada
- **H₀ / H₁** — Null vs Alternative Hypothesis
- **Falsifiability** — Kondisi hipotesis ditolak harus bisa didefinisikan sebelum eksperimen
- **Operationalization** — Proses mewujudkan konsep abstrak menjadi variabel terukur

---

## Template A.4 — RQ-Contribution-Hypothesis

```
RQ-CONTRIBUTION-HYPOTHESIS

Gap Statement  :Penelitian sebelumnya tentang adopsi teknologi pada UMKM (Puspitaningsih et al., 2022)
  hanya dilakukan dengan sampel kecil (50 responden) dan hanya menemukan 2 dari 13
  variabel yang signifikan, sehingga 50,8% variansi adopsi teknologi belum terjelas.
  Belum ada penelitian yang secara komprehensif mengukur pengaruh literasi digital,
  keterbatasan anggaran, dan dukungan infrastruktur secara bersamaan terhadap kinerja
  UMKM di Kota Bandung dengan sampel yang lebih representatif.

Research Question:
  Tipe         : [ ] Comparison  [ ] Improvement  [✔ ] Exploratory
  Formulasi    : Apakah literasi digital, keterbatasan anggaran, dan ketersediaan infrastruktur teknologi secara signifikan mempengaruhi kinerja UMKM di Kota Bandung, diukur menggunakan SEM-PLS pada sampel 150 responden?
  Variabel IV  : 1. Literasi Digital (kemampuan penggunaan teknologi digital)
  2. Keterbatasan Anggaran (kemampuan finansial adopsi teknologi)
  3. Dukungan Infrastruktur (ketersediaan internet & perangkat)
  Variabel DV  : Kinerja UMKM (efisiensi operasional produktivitas, pendapatan)
  Metrik       : Path coefficient, nilai t-value (> 1,96), R² model SEM-PLS
  Dataset      : Kuesioner primer dari 150 UMKM di Kota Bandung
  Baseline     : Puspitaningsih et al. (2022) — SEM-PLS 50 responden UMKM Bandung. R² = 0,492, hanya 2 variabel signifikan dari 13

Quality Check RQ:
  [✔] Variabel spesifik
  [✔] Metrik jelas
  [✔] Baseline ada
  [✔] Konteks disebutkan
  [✔] Memerlukan eksperimen (bukan hanya survei literatur)

Contribution Statement:
  Apa yang baru diketahui : Penelitian ini akan menghasilkan model empiris yang lebih komprehensif tentang pengaruh hambatan adopsi teknologi (literasi digital, anggaran, infrastruktur) terhadap kinerja UMKM di Kota Bandung, dengan sampel 3x lebih besar dari penelitian baseline sehingga lebih representatif.
  Jenis kontribusi        : [✔] Improvement  [✔] Comparison  [ ] Novel approach
  Gap yang diisi          : Context Gap + Performance Gap — R² baseline hanya 49,2% dengan 13 variabel; penelitian ini memfokuskan 3 variabel hambatan utama yang paling relevan secara praktis bagi pelaku UMKM.

Hypothesis Pair:
 H₀₁ : Literasi digital tidak berpengaruh signifikan terhadap kinerja UMKM di Kota Bandung.
  H₁₁ : Literasi digital berpengaruh signifikan positif terhadap kinerja UMKM di Kota Bandung.

H₀₂ : Keterbatasan anggaran tidak berpengaruh signifikan terhadap kinerja UMKM di Kota Bandung.
  H₁₂ : Keterbatasan anggaran berpengaruh signifikan negatif terhadap kinerja UMKM di Kota Bandung.

H₀₃ : Dukungan infrastruktur teknologi tidak berpengaruh signifikan terhadap kinerja UMKM di Kota Bandung.
  H₁₃ : Dukungan infrastruktur teknologi berpengaruh signifikan positif terhadap kinerja UMKM di Kota Bandung.

Threshold              : α = 0,05 (t-value > 1,96)
Justifikasi threshold  : Standar umum pada penelitian sosial dan bisnis dengan pendekatan SEM-PLS (Hair et al., 2017); konsisten dengan threshold yang digunakan pada baseline Puspitaningsih et al. (2022)
```

---

## Latihan 1 — Dari Gap ke RQ

Gunakan gap yang ditemukan di WS-03. Transformasikan menjadi Research Question.

**Gap dari WS-03:** Belum ada penelitian kuantitatif yang secara komprehensif mengukur pengaruh faktor-faktor hambatan adopsi teknologi (literasi digital, anggaran, infrastruktur) terhadap kinerja UMKM di Kota Bandung dengan sampel yang representatif. Penelitian sebelumnya (Puspitaningsih et al., 2022) hanya menggunakan 50 sampel dan menemukan bahwa lebih dari 50% variansi masih belum terjelas.

**RQ versi pertama (tulis bebas):**
> Faktor apa saja yang mempengaruhi kinerja UMKM dalam adopsi teknologi digital di Kota Bandung?

**Evaluasi RQ:**

| Komponen | Ada? | Isi |
|----------|------|-----|
| Metode spesifik |Ya|SEM-PLS |
| Metrik terukur |Ya |Path coefficient, t-value, R² |
| Baseline |Ya |Puspitaningsih et al. (2022) — 50 responden, R² = 0,492 |
| Dataset/konteks |Ya |150 UMKM Kota Bandung, kuesioner primer |

**Tipe RQ:** [ ] Comparison / [ ] Improvement / [✔] Exploratory

**RQ versi revisi (setelah evaluasi):**
> Apakah literasi digital, keterbatasan anggaran, dan dukungan infrastruktur teknologi secara signifikan mempengaruhi kinerja UMKM di Kota Bandung, diukur menggunakan SEM-PLS pada 150 responden?

---

## Latihan 2 — Hypothesis Pair

Rumuskan pasangan hipotesis dari RQ di Latihan 1.

| Komponen | Isi |
|----------|-----|
| H₀₁ | Literasi digital tidak berpengaruh signifikan terhadap kinerja UMKM di Kota Bandung |
| H₁₁ | Literasi digital berpengaruh signifikan positif terhadap kinerja UMKM di Kota Bandung |
| H₀₂ | Keterbatasan anggaran tidak berpengaruh signifikan terhadap kinerja UMKM di Kota Bandung |
| H₁₂ | Keterbatasan anggaran berpengaruh signifikan negatif terhadap kinerja UMKM di Kota Bandung |
| H₀₃ | Dukungan infrastruktur tidak berpengaruh signifikan terhadap kinerja UMKM di Kota Bandung |
| H₁₃ | Dukungan infrastruktur berpengaruh signifikan positif terhadap kinerja UMKM di Kota Bandung |
| Metrik | Path coefficient & t-value (SEM-PLS) |
| Threshold | α = 0,05 (t-value > 1,96) |
| Justifikasi threshold | Standar umum penelitian sosial/bisnis dengan SEM-PLS (Hair et al., 2017) |

**Apakah hipotesis ini falsifiable?** [✔] Ya / [ ] Tidak
> Bagaimana cara membuktikannya salah? Cara membuktikannya salah: Jika t-value < 1,96 dan p-value > 0,05 pada hasil SEM-PLS, maka H₁ ditolak dan H₀ tidak dapat ditolak — artinya variabel tersebut tidak terbukti berpengaruh signifikan terhadap kinerja UMKM.

---

## Latihan 3 — Rantai Operasionalisasi

Lengkapi rantai dari RQ hingga metode analisis.

| Tahap | Isi |
|-------|-----|
| RQ | Apakah literasi digital, keterbatasan anggaran, dan dukungan infrastruktur teknologi berpengaruh signifikan terhadap kinerja UMKM di Kota Bandung? |
| Variable (IV) | 1. Literasi Digital (X₁) — kemampuan menggunakan perangkat & aplikasi digital; 2. Keterbatasan Anggaran (X₂) — kemampuan finansial investasi teknologi; 3. Dukungan Infrastruktur (X₃) — ketersediaan internet & perangkat |
| Variable (DV) | Kinerja UMKM (Y) — efisiensi operasional, produktivitas, pertumbuhan pendapatan |
| Metric | Path coefficient (β), t-value, p-value, R² dari model SEM-PLS |
| Data source | Kuesioner primer skala Likert 5 poin; 150 UMKM Kota Bandung (stratified random sampling berdasarkan klasifikasi mikro, kecil, menengah) |
| Analysis method | SEM-PLS menggunakan SmartPLS 3.0; outer model (convergent & discriminant validity, composite reliability); inner model (R², path coefficient, bootstrapping) |

**Apakah rantai lengkap?** [✔] Ya / [ ] Tidak
> Jika tidak, tahap mana yang perlu direvisi? ______________

---

## Refleksi

> Ambil satu judul skripsi/paper yang pernah dibaca. Coba ekstrak RQ-nya. Apakah RQ tersebut memenuhi semua komponen (metode, metrik, baseline, konteks)? Jika tidak, apa yang hilang?

**Judul:** Faktor yang Mempengaruhi UMKM dalam Mengadopsi Komputasi Awan di Kota Bandung  
**RQ yang diekstrak:** Faktor apa saja yang mempengaruhi UMKM di Kota Bandung dalam mengadopsi teknologi komputasi awan?  
**Komponen yang hilang:** RQ paper ini tidak menyebutkan metrik secara eksplisit dalam pertanyaan penelitiannya, dan tidak ada baseline perbandingan yang jelas dinyatakan di RQ. Selain itu, RQ tidak menyebutkan ukuran sampel target maupun threshold signifikansi yang digunakan. Akibatnya, RQ terasa lebih seperti pertanyaan deskriptif daripada pertanyaan yang mengandung "cetak biru eksperimen" yang lengkap.