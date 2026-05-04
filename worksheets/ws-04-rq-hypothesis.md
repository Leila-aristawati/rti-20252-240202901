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
menggunakan pendekatan statistik SEM-PLS yang hanya menjelaskan hubungan antar variabel,namun belum mampu memprediksi kinerja UMKM secara akurat. Belum ada penelitian yang membandingkan kemampuan prediksi algoritma machine learning (Random Forest vs Logistic Regression) dalam memprediksi kinerja UMKM berdasarkan faktor-faktor adopsi teknologi digital di Kota Bandung.


Research Question:
  Tipe         : [✔] Comparison  [ ] Improvement  [ ] Exploratory
  Formulasi    : Apakah Random Forest menghasilkan akurasi dan F1-Score yang lebih tinggi dibandingkan Logistic Regression dalam memprediksi kinerja UMKM berdasarkan faktor adopsi teknologi digital (literasi digital, keterbatasan anggaran, dan dukungan infrastruktur) di Kota Bandung?
  Variabel IV  : Algoritma klasifikasi — Random Forest vs Logistic Regression
  Variabel DV  : Akurasi prediksi kinerja UMKM
  Metrik       : Accuracy, F1-Score, Precision, Recall
  Dataset      : Data kuesioner primer dari 150 UMKM di Kota Bandung (fitur: literasi digital, keterbatasan anggaran, dukungan infrastruktur
  label: kinerja UMKM — tinggi/rendah)
  Baseline     : Logistic Regression (sebagai model klasifikasi dasar/sederhana)

Quality Check RQ:
  [✔] Variabel spesifik
  [✔] Metrik jelas
  [✔] Baseline ada
  [✔] Konteks disebutkan
  [✔] Memerlukan eksperimen (bukan hanya survei literatur)

Contribution Statement:
  Apa yang baru diketahui : Penelitian ini akan menghasilkan bukti empiris algoritma mana (Random Forest atau Logistic Regression) yang lebih akurat dalam memprediksi kinerja UMKM berdasarkan faktor adopsi teknologi digital, sehingga dapat menjadi rekomendasi tools prediksi bagi pengambil kebijakan dan pelaku UMKM di Bandung.
  Jenis kontribusi        : [ ] Improvement  [✔] Comparison  [ ] Novel approach
  Gap yang diisi          : Method Gap — penelitian sebelumnya hanya menggunakan SEM-Method Gap — penelitian sebelumnya hanya menggunakan SEM-PLS untuk menjelaskan hubungan variabel, belum ada yang menggunakan machine learning untuk memprediksi kinerja UMKM berdasarkan faktor adopsi teknologi di Kota Bandung.

Hypothesis Pair:
  H₀ : Tidak ada perbedaan signifikan antara akurasi Random Forest dan Logistic Regression dalam memprediksi kinerja UMKM berdasarkan faktor adopsi teknologi digital di Kota Bandung.
  H₁ : Random Forest menghasilkan akurasi dan F1-Score yang lebih tinggi secara signifikan dibandingkan Logistic Regression dalam memprediksi kinerja UMKM berdasarkan faktor adopsi teknologi digital di Kota Bandung.
  Threshold : Akurasi ≥ 80% dan F1-Score lebih tinggi minimal 5% dibandingkan baseline Logistic Regression
  Justifikasi threshold : Threshold akurasi 80% merupakan standar minimum yang umum digunakan pada penelitian klasifikasi di bidang bisnis dan sosial (Mustafa & Yaakub, 2018); selisih 5% F1-Score dianggap perbedaan yang praktis signifikan antar model.
```

---

## Latihan 1 — Dari Gap ke RQ

Gunakan gap yang ditemukan di WS-03. Transformasikan menjadi Research Question.

**Gap dari WS-03:** Penelitian sebelumnya (Puspitaningsih et al., 2022) hanya menggunakan SEM-PLS untuk
menjelaskan hubungan antar variabel adopsi teknologi pada UMKM, namun belum ada yang
menggunakan pendekatan machine learning untuk memprediksi kinerja UMKM berdasarkan
faktor-faktor tersebut. Ini adalah method gap yang membuka peluang perbandingan algoritma
prediksi di konteks UMKM Kota Bandung.

**RQ versi pertama (tulis bebas):**
> Algoritma machine learning mana yang paling akurat untuk memprediksi kinerja UMKM
berdasarkan faktor adopsi teknologi digital?

**Evaluasi RQ:**

| Komponen | Ada? | Isi |
|----------|------|-----|
| Metode spesifik | Ya | Random Forest vs Logistic Regression |
| Metrik terukur | Ya | Accuracy, F1-Score, Precision, Recall |
| Baseline | Ya | Logistic Regression sebagai model klasifikasi dasar |
| Dataset/konteks | Ya | 150 UMKM Kota Bandung, data kuesioner primer |

**Tipe RQ:** [✔] Comparison / [ ] Improvement / [ ] Exploratory

**RQ versi revisi (setelah evaluasi):**
> Apakah Random Forest menghasilkan akurasi dan F1-Score yang lebih tinggi dibandingkan
Logistic Regression dalam memprediksi kinerja UMKM berdasarkan faktor adopsi teknologi
digital (literasi digital, keterbatasan anggaran, dukungan infrastruktur) di Kota Bandung?
---

## Latihan 2 — Hypothesis Pair

Rumuskan pasangan hipotesis dari RQ di Latihan 1.

| Komponen | Isi |
|----------|-----|
| H₀ | Tidak ada perbedaan signifikan antara akurasi Random Forest dan Logistic Regression dalam memprediksi kinerja UMKM berdasarkan faktor adopsi teknologi digital di Kota Bandung |
| H₁ | Random Forest menghasilkan akurasi dan F1-Score lebih tinggi secara signifikan dibandingkan Logistic Regression dalam memprediksi kinerja UMKM berdasarkan faktor adopsi teknologi digital di Kota Bandung |
| Metrik | Accuracy, F1-Score, Precision, Recall |
| Threshold | Akurasi ≥ 80%; F1-Score Random Forest lebih tinggi minimal 5% dari Logistic Regression |
| Justifikasi threshold | Standar minimum akurasi 80% umum digunakan pada penelitian klasifikasi di domain bisnis dan sosial |

**Apakah hipotesis ini falsifiable?** [✔] Ya / [ ] Tidak
> Bagaimana cara membuktikannya salah? Cara membuktikannya salah: Jika akurasi Random Forest < 80% atau F1-Score Random Forest
tidak lebih tinggi minimal 5% dari Logistic Regression, maka H₁ ditolak dan H₀ tidak
dapat ditolak, artinya Random Forest tidak terbukti lebih unggul dari Logistic Regression
untuk prediksi kinerja UMKM.

---

## Latihan 3 — Rantai Operasionalisasi

Lengkapi rantai dari RQ hingga metode analisis.

| Tahap | Isi |
|-------|-----|
| RQ | Apakah Random Forest menghasilkan akurasi lebih tinggi dari Logistic Regression dalam memprediksi kinerja UMKM berdasarkan faktor adopsi teknologi digital di Kota Bandung? |
| Variable (IV) | Algoritma klasifikasi: Random Forest vs Logistic Regression |
| Variable (DV) | Akurasi prediksi kinerja UMKM (label: kinerja tinggi / kinerja rendah) |
| Metric | Accuracy, F1-Score, Precision, Recall — dihitung dari confusion matrix |
| Data source | Kuesioner primer skala Likert 5 poin; 150 UMKM Kota Bandung; fitur input: literasi digital (X₁), keterbatasan anggaran (X₂), dukungan infrastruktur (X₃); label output: kinerja UMKM (Y) |
| Analysis method | Python (scikit-learn): preprocessing → split data train/test (80:20) → training Random Forest & Logistic Regression → evaluasi dengan confusion matrix → bandingkan Accuracy & F1-Score |

**Apakah rantai lengkap?** [✔] Ya / [ ] Tidak
> Jika tidak, tahap mana yang perlu direvisi? ______________

---

## Refleksi

> Ambil satu judul skripsi/paper yang pernah dibaca. Coba ekstrak RQ-nya. Apakah RQ tersebut memenuhi semua komponen (metode, metrik, baseline, konteks)? Jika tidak, apa yang hilang?

**Judul:** Faktor yang Mempengaruhi UMKM dalam Mengadopsi Komputasi Awan di Kota Bandung  
**RQ yang diekstrak:** Faktor apa saja yang mempengaruhi UMKM di Kota Bandung dalam mengadopsi teknologi komputasi awan?  
**Komponen yang hilang:** RQ paper tersebut tidak menyebutkan metrik perbandingan secara eksplisit, tidak ada
baseline model, dan tidak ada komponen prediksi. RQ hanya bersifat eksploratif
(hubungan antar variabel) tanpa ada perbandingan metode. Penelitian ini mengisi gap
tersebut dengan menambahkan komponen perbandingan algoritma machine learning sehingga
RQ menjadi lebih testable dan menghasilkan rekomendasi yang lebih konkret.