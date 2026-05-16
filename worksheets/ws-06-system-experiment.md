# WS-06: System-Experiment Mapping

> **Bab 6 — System Design sebagai Experimental Artifact**

---

## Ringkasan Materi

### Sistem = Instrumen Pengujian, Bukan Produk

Seorang engineer bertanya "apakah sistem bekerja?" — seorang peneliti bertanya "apa yang bisa dibuktikan sistem ini?" Sistem dalam riset adalah **artifact** — objek yang sengaja dibuat untuk menguji klaim spesifik.

### System as Experiment Model

```
RQ → Variable → System Component → Experimental Setup → Output
```

Setiap komponen sistem harus bisa ditelusuri ke variabel riset (top-down), dan setiap pengukuran harus menjawab RQ (bottom-up).

### Mapping Variabel ke Komponen

| Tipe Variabel | Peran di Sistem | Contoh |
|---------------|----------------|--------|
| **IV** (Independent) | Modul yang bisa di-toggle/swap | Algoritma A vs B |
| **DV** (Dependent) | Modul pengukuran | Logger, metrics collector |
| **CV** (Control) | Config yang dikunci | Dataset, parameter tetap |

Jika variabel tidak bisa di-map ke komponen apapun → arsitektur perlu didesain ulang.

### 4 Prinsip Desain Eksperimental

| Prinsip | Pertanyaan Kunci |
|---------|-----------------|
| **Traceability** | Komponen ini melayani variabel yang mana? |
| **Modularity** | Bisakah IV diubah tanpa memengaruhi yang lain? |
| **Controllability** | Apakah CV dieksternalisasi ke config file? |
| **Measurability** | Apakah sistem otomatis menghasilkan data yang dibutuhkan? |

### Variable Isolation melalui Arsitektur

- **Modular architecture** — Pisahkan berdasarkan variabel
- **Configuration-driven** — Ubah config (YAML/JSON), bukan code
- **Feature toggles** — On/off flag untuk ablation study

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan sistem | Memenuhi kebutuhan user | Menguji hipotesis, menghasilkan bukti |
| Arsitektur | Optimasi performa & skalabilitas | Optimasi isolasi variabel & reprodusibilitas |
| Konfigurasi | Sering hardcoded | Dieksternalisasi ke config file |
| Fitur tambahan | Menambah nilai user | Menambah noise jika tidak terkait RQ |

### Istilah Penting

- **Artifact** — Objek yang sengaja dibuat untuk memecahkan masalah atau menguji proposisi
- **Traceability** — Kemampuan menelusuri hubungan RQ → variabel → komponen → output
- **Variable Isolation** — Mengubah hanya satu variabel sambil menahan yang lain konstan
- **Ablation Study** — Menguji kontribusi tiap komponen dengan melepasnya satu per satu
- **Configuration-driven Execution** — Semua parameter di config file, bukan hardcoded

---

## Template A.6 — Mapping RQ ke Arsitektur Sistem

```
SYSTEM-EXPERIMENT MAPPING

Research Question: Apakah literasi digital, keterbatasan anggaran, dan dukungan infrastruktur teknologi secara signifikan mempengaruhi kinerja UMKM di Kota Bandung, diukur menggunakan SEM-PLS pada 150 responden?


Variable → Component Mapping:
| Variabel | Tipe | Komponen Sistem | Cara Manipulasi/Pengukuran |
|----------|------|-----------------|---------------------------|
| Literasi Digital       | IV   | Modul instrumen kuesioner (blok X₁)   | Skor rata-rata 5 item Likert; diubah per responden      |
| Keterbatasan Anggaran  | IV   | Modul instrumen kuesioner (blok X₂)   | Skor rata-rata 4 item Likert; diubah per responden      |
| Dukungan Infrastruktur | IV   | Modul instrumen kuesioner (blok X₃)   | Skor rata-rata 4 item Likert; diubah per responden      |
| Kinerja UMKM           | DV   | Modul pengukuran output (blok Y)      | Path coefficient (β) & t-value dihasilkan SmartPLS 3.0  |
| Ukuran Usaha           | CV   | Config filter responden               | Dikunci berdasarkan klasifikasi mikro/kecil/menengah     

4 Prinsip Desain:
  [✔] Traceability — Setiap blok kuesioner (X₁, X₂, X₃, Y) bisa ditelusuri ke variabel
  [✔] Variable Isolation — Setiap IV diukur pada blok terpisah; perubahan satu blok tidak mempengaruhi blok lain
  [✔] Measurement Integration — SmartPLS otomatis menghasilkan path coefficient, t-value, dan R² sebagai output pengukuran DV
  [✔] Reproducibility — Instrumen kuesioner dan konfigurasi SmartPLS terdokumentasi sehingga bisa direkonstruksi

Experimental Setup:
  Input data     :Data kuesioner primer dari 150 UMKM Kota Bandung (format Excel/CSV)
  Parameter      :Skala Likert 1–5, threshold t-value > 1,96 (α = 0,05),outer loading ≥ 0,708, AVE ≥ 0,5
  Output format  : Path coefficient (β), t-value, R², AVE, composite reliability (dihasilkan SmartPLS 3.0, diekspor ke tabel hasil)
```

---

## Latihan 1 — Variable-to-Component Mapping

Gunakan RQ dan variabel dari WS-05. Petakan ke komponen sistem.

**RQ:** __________________________________________________

| Variabel | Tipe | Komponen Sistem | Cara Manipulasi / Pengukuran |
|----------|------|-----------------|---------------------------|
| Literasi Digital | IV | Blok kuesioner X₁ (5 item Likert) | Skor diinput per responden; dianalisis sebagai konstruk laten di SmartPLS |
| Keterbatasan Anggaran | IV | Blok kuesioner X₂ (4 item Likert) | Skor diinput per responden; dianalisis sebagai konstruk laten di SmartPLS |
| Dukungan Infrastruktur | IV | Blok kuesioner X₃ (4 item Likert) | Skor diinput per responden; dianalisis sebagai konstruk laten di SmartPLS |
| Kinerja UMKM | DV | Blok kuesioner Y + modul analisis SmartPLS | Path coefficient (β) & t-value dihitung otomatis oleh SmartPLS 3.0 |
| Ukuran Usaha | CV | Config filter & stratifikasi sampling | Dikunci dengan stratified random sampling (mikro/kecil/menengah) |

**Apakah semua variabel bisa di-map?** [✔] Ya / [ ] Tidak
> Jika tidak, komponen apa yang perlu ditambahkan? _________

---

## Latihan 2 — 4 Prinsip Desain

Evaluasi desain sistem terhadap 4 prinsip.

| Prinsip | Status | Bukti / Penjelasan |
|---------|--------|-------------------|
| Traceability | ✅ | Setiap blok kuesioner (X₁, X₂, X₃, Y) berlabel variabel spesifik dan dapat ditelusuri langsung ke hipotesis H₁, H₂, H₃ |
| Modularity | ✅ | Setiap variabel IV diukur pada blok kuesioner yang terpisah; penambahan atau penghapusan satu blok tidak mempengaruhi blok lainnya |
| Controllability | ✅ | Variabel kontrol (ukuran usaha) dieksternalisasi melalui stratified random sampling yang terdokumentasi, bukan hardcoded dalam instrumen |
| Measurability | ✅ | SmartPLS 3.0 secara otomatis menghasilkan semua metrik yang dibutuhkan (path coefficient, t-value, R², AVE) tanpa intervensi manual |

**Prinsip mana yang paling sulit dipenuhi?** Controllability
**Strategi untuk mengatasinya:**
> Variabel kontrol (ukuran usaha) sulit dikontrol secara ketat karena bergantung pada
> kejujuran responden dalam mengisi klasifikasi usahanya. Strategi mitigasi: verifikasi
> silang klasifikasi usaha dengan data omzet atau jumlah karyawan yang juga ditanyakan
> dalam kuesioner, sehingga inkonsistensi bisa dideteksi dan dikeluarkan dari sampel.
---

## Latihan 3 — Ablation Study Planning

Jika sistem memiliki 3 komponen utama, rencanakan ablation study.

| Kondisi | Komponen A | Komponen B | Komponen C | Hasil yang Diharapkan |
|---------|-----------|-----------|-----------|----------------------|
| Full | ✅ Literasi Digital | ✅Keterbatasan Anggaran | ✅Dukungan Infrastruktur | R² tertinggi; semua pengaruh terukur |
| – A | ❌ (tanpa literasi digital) | ✅ | ✅ | R² menurun jika literasi digital berkontribusi signifikan |
| – B | ✅ | ❌ (tanpa anggaran) | ✅ | R² menurun jika anggaran berkontribusi signifikan |
| – C | ✅ | ✅ | ❌ (tanpa infrastruktur) | R² menurun jika infrastruktur berkontribusi signifikan |

**Komponen mana yang diprediksi paling berkontribusi?** Komponen A — Literasi Digital (X₁)
**Mengapa?**
> Berdasarkan literatur (Suwarni et al., 2019; Putri et al., 2023), literasi digital
> secara konsisten disebut sebagai hambatan utama UMKM dalam mengadopsi dan memanfaatkan
> teknologi. UMKM yang memiliki literasi digital rendah cenderung tidak mampu
> memaksimalkan teknologi yang tersedia meskipun anggaran dan infrastruktur memadai.
> Oleh karena itu, menghapus komponen ini diprediksi akan menghasilkan penurunan R²
> paling besar dibandingkan komponen lainnya.
---

## Refleksi

> Apa risiko jika sistem dibangun seperti produk (monolitik, fitur lengkap) lalu baru dilakukan eksperimen? Mengapa arsitektur modular penting untuk riset?

**Jawaban:**
> Jika sistem dibangun monolitik seperti produk, risiko utamanya adalah tidak bisa
> mengisolasi pengaruh satu variabel dari variabel lainnya. Ketika hasil eksperimen
> tidak sesuai harapan, peneliti tidak bisa mengetahui komponen mana yang menjadi
> penyebabnya karena semua komponen saling terkait dan tidak bisa dilepas satu per satu.
> Arsitektur modular penting dalam riset karena memungkinkan variable isolation —
> peneliti bisa mengubah satu komponen (misalnya menghapus satu blok variabel) tanpa
> mengganggu komponen lain. Ini adalah syarat dasar eksperimen yang valid dan
> reproducible: orang lain harus bisa mereplikasi eksperimen dengan konfigurasi yang
> sama dan mendapatkan hasil yang sama.