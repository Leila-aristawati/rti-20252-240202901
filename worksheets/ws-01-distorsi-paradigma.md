# WS-01: Distorsi & Paradigma

> **Bab 1 — Research Mindset in IT**

---

## Ringkasan Materi

### Research Trust Model

Pengetahuan ilmiah tidak muncul langsung dari kenyataan. Ia melewati **6 tahap transformasi** yang masing-masing rawan distorsi:

```
Reality → Data → Processing → Analysis → Inference → Knowledge
```

Etika mencegah distorsi yang disengaja (fabrikasi, cherry-picking). Validitas mendeteksi distorsi yang tidak disengaja (confounding variable, sampling bias).

### Tiga Jenis Validitas

| Jenis | Pertanyaan | Contoh Ancaman |
|-------|-----------|----------------|
| **Internal Validity** | Apakah hubungan kausal benar ada? | Confounding variable |
| **External Validity** | Apakah bisa digeneralisasi? | Dataset terlalu homogen |
| **Construct Validity** | Apakah mengukur hal yang benar? | Metrik tidak sesuai klaim |

### Paradigma Riset

Mata kuliah ini menggunakan pendekatan **Positivist** (fenomena TI bisa diukur objektif melalui eksperimen terkontrol) diperkuat **Design Science Research** (artefak dibuat sebagai instrumen pengujian hipotesis, bukan tujuan akhir).

### Mode Berpikir Peneliti

**Curious** (mempertanyakan fenomena) → **Critical** (mengevaluasi klaim berdasarkan bukti) → **Systematic** (merancang investigasi terstruktur dan reproducible).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Membuat sistem yang bekerja | Menghasilkan pengetahuan yang valid |
| Pertanyaan khas | "Bagaimana membuatnya jalan?" | "Apakah klaim ini benar?" |
| Ukuran sukses | Sistem berfungsi, client puas | Hipotesis terjawab, temuan tervalidasi |
| Kegagalan | Harus dihindari | Harus dilaporkan (negative result = kontribusi) |

### Istilah Penting

- **Research Mindset** — Pola pikir yang menuntut bukti dan mempertanyakan asumsi
- **Research Ethics** — Prinsip perilaku: kejujuran, objektivitas, keterbukaan, akuntabilitas
- **HARKing** — Hypothesizing After Results are Known — merumuskan hipotesis setelah melihat data
- **Falsifiability** — Hipotesis harus bisa dibuktikan salah

---

## Template A.1 — Research Mindset Self-Assessment

```
Nama Peneliti    : Leila Aristawati
Tanggal          : Kamis, 4 April 2026

1. Ketika membaca klaim "metode X 95% akurat":
   - Pertanyaan pertama saya: 
   Data tersebut diperoleh dari mana dan bagaimana metode pengujiannya?
   - Data yang dibutuhkan untuk verifikasi:Dataset yang digunakan, ukuran sampel, metode evaluasi (misalnya akurasi, precision, recall), serta kondisi eksperimen

2. Posisi paradigma:
   - Pendekatan: [☑] Positivis  [ ] Interpretivis  [ ] Design Science  [ ] Mixed
   - Alasan: Karena penelitian menggunakan data kuantitatif dan pengujian hipotesis (SEM-PLS) untuk melihat hubungan antar variabel secara objektif, seperti pada jurnal UMKM yang dianalisis.

3. Identifikasi distorsi:
   - Asumsi tersembunyi: 
   Responden memahami semua pertanyaan kuesioner dengan benar
   - Sumber bias potensial: 
   Bias responden, sampling bias, serta kemungkinan kesalahan dalam pengisian kuesioner
   - Langkah mitigasi: 
   Menggunakan instrumen yang sudah tervalidasi, memperjelas pertanyaan, dan memastikan teknik sampling yang lebih representatif

4. Komitmen etika:
   - Data yang tidak akan dimanipulasi: Data hasil kuesioner dan hasil analisis statistik (SEM-PLS)
   - Batasan yang diakui sejak awal: Jumlah sampel terbatas (100 responden) dan hasil penelitian mungkin tidak sepenuhnya mewakili seluruh UMKM di Indonesia
```

---

## Latihan 1 — Identifikasi Distorsi

Pilih satu paper riset di bidang TI yang mengklaim "metode X meningkatkan performa." Telusuri setiap tahap Research Trust Model.

**Paper yang dipilih:**
> Judul: Perkembangan UMKM di Indonesia: Peran Pemahaman Akuntansi, Teknologi Informasi dan Sistem Informasi Akuntansi
> Penulis (Tahun): Fitriani Saragih dkk (2023)

| Tahap | Apa yang Dilakukan | Potensi Distorsi |
|-------|-------------------|-----------------|
| Reality → Data | Mengambil data dari UMKM melalui kuesioner (100 responden, random sampling) | Responden tidak jujur / tidak memahami pertanyaan |
| Data → Processing |Data diolah menggunakan SEM-PLS |Kesalahan input data atau preprocessing |
| Processing → Analysis |Analisis hubungan antar variabel (akuntansi, TI, SIA → UMKM) |Pemilihan model statistik bisa bias |
| Analysis → Inference |Menyimpulkan pengaruh signifikan/tidak signifikan |Overinterpretasi hasil |
| Inference → Knowledge |Menarik kesimpulan umum tentang perkembangan UMKM |Generalisasi berlebihan (sampel cuma 100 UMKM) |

**Distorsi paling besar di tahap:** Reality → Data

**Dua distorsi spesifik yang teridentifikasi:**
1. Bias responden (jawaban kuesioner tidak akurat)
2. Sampling bias (walaupun random, belum tentu representatif seluruh UMKM Indonesia)

---

## Latihan 2 — Analisis Kasus Etika

Skenario: Seorang peneliti menemukan bahwa jika 3 data point outlier dihapus, hasil eksperimennya menjadi signifikan. Dengan outlier, hasilnya tidak signifikan.

| Perspektif | Analisis |
|------------|---------|
| Kejujuran ilmiah | Harus melaporkan hasil dengan dan tanpa outlier |
| Transparansi |Jelaskan alasan penghapusan outlier (jika dilakukan) |
| Peer review |Reviewer bisa menilai apakah penghapusan outlier valid atau manipulasi |

**Keputusan akhir dan justifikasi:**
> Data outlier tidak boleh langsung dihapus hanya untuk membuat hasil signifikan. Peneliti harus melaporkan kedua kondisi (dengan dan tanpa outlier) dan memberikan justifikasi ilmiah. Ini sesuai prinsip research ethics dan menghindari manipulasi hasil.

---

## Latihan 3 — Posisi Paradigma

**Topik riset:** ________________________________________

| Kriteria | Positivis | Interpretivis | Design Science |
|----------|-----------|---------------|----------------|
| Kesesuaian dengan topik (1–5) | 5 | 2 | 3 |
| Jenis data yang dikumpulkan |Data kuantitatif (kuesioner, statistik) |Wawancara (tidak digunakan) |Artefak (tidak fokus) |
| Limitasi paradigma |Tidak menangkap konteks sosial mendalam |Subjektif |Tidak fokus ke pengujian hipotesis |

**Paradigma yang dipilih:** Positivis  
**Alasan:** Penelitian menggunakan pendekatan kuantitatif dengan pengujian hipotesis (SEM-PLS), sehingga sesuai dengan paradigma positivis yang menekankan pengukuran objektif dan hubungan kausal

---

## Refleksi

Sebelum membaca materi ini, apakah pernah mempertanyakan klaim "95% akurat"? Setelah memahami rantai distorsi, pertanyaan apa yang sekarang akan diajukan saat membaca paper?

**Jawaban:**
> Sebelum membaca materi, saya mungkin langsung percaya klaim “95% akurat”. Setelah memahami distorsi, saya akan bertanya:
>1. Data diambil dari mana?
2. Apakah sampelnya representatif?
3. Metode analisisnya valid atau tidak?
4. Apakah ada bias atau manipulasi data?
