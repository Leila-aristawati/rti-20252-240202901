# WS-03: Literature Mapping & Gap

> **Bab 3 — Literature Review, Research Gap & Baseline**

---

## Ringkasan Materi

### Literature Review = Positioning, Bukan Ringkasan

Literature review bukan merangkum paper satu per satu. Pendekatan yang benar adalah **concept-centric** — organisasi berdasarkan tema, metode, atau variabel. Tujuan: menemukan **pola, kontradiksi, dan gap**.

### Empat Jenis Research Gap

| Jenis Gap | Deskripsi | Contoh |
|-----------|----------|--------|
| **Performance Gap** | Performa belum memadai | Akurasi deteksi hanya 78% pada kasus tertentu |
| **Method Gap** | Pendekatan belum diterapkan | Belum ada yang pakai transformer untuk task ini |
| **Data Gap** | Dataset terbatas/tidak representatif | Semua studi pakai dataset sintetis |
| **Context Gap** | Belum diuji pada konteks berbeda | Belum ada evaluasi di negara berkembang |

Gap terkuat = kombinasi 2+ jenis.

### Systematic Search Strategy

1. **Database**: IEEE Xplore, ACM DL, Scopus, Google Scholar
2. **Boolean query** yang terdokumentasi eksplisit
3. **Snowballing**: backward (telusuri referensi) + forward (cari yang mengutip)
4. Klaim "belum ada penelitian" harus didukung **bukti pencarian**

### Baseline Selection — 3 Kriteria

| Kriteria | Pertanyaan |
|----------|-----------|
| **Relevan** | Apakah menyelesaikan masalah yang sama? |
| **Representatif** | Apakah mewakili common practice? |
| **State-of-the-Art** | Apakah terbaru/terbaik? |

Membandingkan deep learning 2024 dengan decision tree sederhana tanpa justifikasi = **straw man comparison** (perbandingan tidak jujur).

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan baca literatur | Mencari solusi yang sudah ada | Memahami apa yang belum terjawab |
| Cara membaca paper | Tutorial, how-to | Metode, limitasi, gap |
| Baseline | Framework terpopuler | State-of-the-art yang rigorous |
| Dokumentasi pencarian | Tidak diperlukan | Wajib (reproducible) |

### Istilah Penting

- **Concept-centric** — Organisasi literatur berdasarkan konsep/metode, bukan per penulis
- **Snowballing** — Backward (telusuri referensi) + Forward (cari yang mengutip paper kunci)
- **Research Position** — Pernyataan eksplisit posisi riset terhadap studi sebelumnya
- **Straw man comparison** — Memilih baseline lemah agar metode sendiri terlihat lebih baik

---

## Template A.3 — Literature Mapping & Gap Identification

```
LITERATURE MAPPING

Topik      : Adopsi Teknologi Digital pada UMKM (Usaha Mikro, Kecil, dan Menengah)
Database   : 5 paper akademik dari Google Schoolar
Query      : UMKM + teknologi + adopsi + transformasi digital + inovasi + kinerja
Tahun      : 2018 - 2023
Hasil awal : 5 paper → Screening → 5 paper final

Literature Matrix (concept-centric):

| Study | Tahun | Method | Data | Result | Limitation |
|-------|-------|--------|------|--------|------------|
| 1 | Mustafa & Yaakub *(Innovation and Technology Adoption Challenges: Impact on SMEs' Company Performance)* | 2018 | Kuantitatif — survei + regresi sederhana (SPSS 24) | 152 perusahaan manufaktur Malaysia (SME Corp Malaysia) | Tantangan inovasi & adopsi teknologi berpengaruh **negatif signifikan** terhadap kinerja UKM (β = −0.185, p = .000) | Hanya sektor manufaktur; hanya Semenanjung Malaysia; satu variabel independen; R² hanya 8.1% |
| 2 | Cahyana *(Perancangan Sistem Informasi UMKM Berbasis Web di Desa Bojongsari)* | 2022 | Kualitatif-deskriptif + SDLC Waterfall; black box testing | UMKM Desa Bojongsari, Karawang (KKN 2021) | Sistem informasi berbasis web berhasil dirancang, mempercepat pendataan UMKM dan mendukung pengambilan keputusan | Ruang lingkup satu desa; tidak mengukur dampak kinerja bisnis secara kuantitatif; tidak ada evaluasi adopsi pengguna pasca-implementasi |
| 3 | Suwarni, Sedyastuti & Mirza *(Peluang dan Hambatan Pengembangan Usaha Mikro pada Era Ekonomi Digital)* | 2019 | Kualitatif-deskriptif + SWOT analysis; wawancara mendalam | Usaha mikro Kota Palembang; informan: dinas industri, perdagangan, koperasi, dan pelaku usaha | Peluang sangat besar (penetrasi internet tinggi, pasar luas); hambatan utama: **rendahnya literasi digital SDM** dan infrastruktur terbatas di pedesaan | Hanya kota Palembang; tidak menggunakan pengukuran kuantitatif; generalisasi terbatas |
| 4 | Puspitaningsih, Liana & Irianti *(Faktor yang Mempengaruhi UMKM dalam Mengadopsi Komputasi Awan di Kota Bandung)* | 2022 | Kuantitatif eksploratori — SEM-PLS; gabungan kerangka TOE + TRI | 50 UMKM Kota Bandung (stratified random sampling berdasarkan BPS 2018) | Hanya **complexity** dan **optimism** berpengaruh signifikan positif terhadap adopsi cloud computing (R² = 0.492) | Sampel kecil (50); satu kota; 11 dari 13 variabel ditolak; belum merepresentasikan seluruh Indonesia |
| 5 | Putri, Mulyadi, Fajarini & Eriyansyah *(Transformasi Digital UMKM Kota Palembang)* | 2023 | Kualitatif — wawancara mendalam, observasi, dokumentasi; analisis Miles & Huberman | Pelaku UMKM Kota Palembang; observasi Pasar 16 Ilir | Transformasi digital mulai berjalan (terutama sistem pembayaran); media sosial dan e-commerce terbukti membantu; namun **banyak UMKM masih mengandalkan pemasaran tradisional** | Tidak ada pengukuran kuantitatif; hanya satu kota; tidak mengukur tingkat adopsi secara terstruktur |

Pola yang ditemukan:
  Metode dominan     : Kualitatif-deskriptif (3 dari 5 paper); kuantitatif survei/SEM hanya 2 paper
  Dataset umum       : UMKM skala kota/kabupaten di Indonesia (Palembang, Bandung, Karawang); satu paper Malaysia
  Limitasi berulang  : (1) Ruang lingkup geografis sempit (satu kota/daerah); (2) Tidak mengukur dampak kinerja bisnis secara kuantitatif pasca adopsi; (3) Sampel kecil; (4) Rendahnya literasi digital UMKM disebut berulang sebagai hambatan namun tidak dimodelkan secara statistik
  
GAP IDENTIFICATION

Gap 1: [Jenis: performance / method / data / context]
  Deskripsi    : Mayoritas studi menggunakan pendekatan kualitatif yang tidak mampu mengukur seberapa besar dampak adopsi teknologi digital terhadap kinerja UMKM secara terukur. Studi kuantitatif yang ada (Mustafa & Yaakub, 2018; Puspitaningsih et al., 2022) memiliki R² rendah atau sampel kecil, sehingga model penjelasannya belum memadai. 
  Bukti        : Mustafa & Yaakub (2018): R² = 8.1% (hanya satu prediktor). Puspitaningsih et al. (2022): 50.8% varians kinerja adopsi belum dijelaskan. Tiga paper lain (Cahyana, Suwarni et al., Putri et al.) tidak mengukur kinerja sama sekali.
  Signifikansi : Tanpa model kuantitatif yang komprehensif, pembuat kebijakan dan pelaku UMKM tidak memiliki dasar empiris yang kuat untuk memprioritaskan intervensi teknologi mana yang paling berdampak pada kinerja bisnis nyata.

Gap 2: [Jenis: Context]
  Deskripsi    : Tidak ada studi di antara kelima paper ini yang membandingkan adopsi teknologi lintas sektor UMKM (misalnya: makanan & minuman vs fashion vs jasa) atau lintas tingkat kematangan digital. Seluruh studi memperlakukan UMKM sebagai kelompok homogen, padahal karakteristik bisnis, kapasitas SDM, dan kebutuhan teknologi sangat bervariasi antar sektor.
  Bukti        :Puspitaningsih et al. (2022): 42% responden dari sektor makanan, namun tidak dilakukan analisis per-sektor. Putri et al. (2023): observasi hanya di Pasar 16 Ilir tanpa segmentasi jenis usaha.
  Signifikansi : Program digitalisasi UMKM yang tidak mempertimbangkan heterogenitas sektor berpotensi tidak efektif karena kebutuhan dan hambatan adopsi berbeda-beda.

### Gap 3 — [Jenis: Data]
    Deskripsi    : Semua studi yang meneliti konteks Indonesia hanya mencakup satu kota atau satu desa, sehingga temuan sulit digeneralisasi ke konteks UMKM nasional yang lebih luas — termasuk daerah dengan infrastruktur digital terbatas seperti wilayah pedesaan Jawa Tengah atau Indonesia Timur.
    Bukti        : Suwarni et al. (2019): hanya Kota Palembang. Puspitaningsih et al. (2022): hanya Kota Bandung. Cahyana (2022): hanya Desa Bojongsari, Karawang.
    Signifikansi : Keragaman infrastruktur digital di Indonesia menuntut studi dengan cakupan geografis yang lebih luas agar rekomendasi kebijakan relevan untuk semua daerah, termasuk daerah 3T (terdepan, terluar, tertinggal).

Baseline Selection:
| Baseline | Relevansi | Representatif | Source |
|----------|-----------|---------------|--------|
| 1        | Regresi sederhana: Inovasi &Adopsi Teknologi → Kinerja UKM | Task sama: mengukur pengaruh adopsi teknologi terhadap kinerja UMKM; variabel dan konteks paling dekat dengan banyak penelitian lanjutan | Digunakan sebagai kerangka dasar penelitian UKM di Malaysia dan diacu oleh beberapa studi UMKM Asia | Bukan SOTA, tetapi merupakan *common baseline* di literatur UKM | Mustafa & Yaakub (2018) |
| 2        | SEM-PLS dengan kerangka TOE + TRI → Adopsi Cloud Computing | Task relevan: memodelkan faktor-faktor adopsi teknologi pada UMKM secara multivariat; metodologi lebih canggih dari regresi sederhana | Model TOE+TRI banyak digunakan di literatur adopsi teknologi organisasi skala kecil-menengah | Bukan SOTA, namun merupakan model paling komprehensif di antara kelima paper | Puspitaningsih et al. (2022) |

```

---

## Latihan 1 — Concept-Centric Literature Table

Gunakan topik riset dari WS-02. Cari minimal 5 paper relevan menggunakan Google Scholar atau database lain.

**Topik riset:** Faktor-faktor yang mempengaruhi adopsi teknologi digital pada UMKM dan dampaknya terhadap kinerja bisnis
**Query pencarian:** `UMKM AND "adopsi teknologi" AND kinerja` / `SME AND "technology adoption" AND performance AND digital`
**Database:** 5 paper akademik dari jurnal Google Schoolar

| # | Study | Tahun | Method | Dataset | Result | Limitasi |
|---|-------|-------|--------|---------|--------|----------|
| 1 | Mustafa & Yaakub | 2018 | Kuantitatif, survei, regresi sederhana | 152 UKM manufaktur Malaysia | Adopsi teknologi berpengaruh negatif signifikan terhadap kinerja (β=−0.185) | Satu sektor, satu wilayah, R²=8.1% |
| 2 | Cahyana | 2022 | SDLC Waterfall, kualitatif, black box testing | UMKM Desa Bojongsari, Karawang | Sistem informasi web berhasil dirancang dan mempercepat pendataan | Tidak mengukur dampak kinerja bisnis; satu desa |
| 3 | Suwarni, Sedyastuti & Mirza | 2019 | Kualitatif deskriptif, SWOT, wawancara | Usaha mikro Kota Palembang | Peluang besar; hambatan utama: literasi digital rendah | Satu kota; tidak ada pengukuran kuantitatif |
| 4 | Puspitaningsih, Liana & Irianti | 2022 | SEM-PLS, kuantitatif eksploratori, TOE+TRI | 50 UMKM Kota Bandung | Hanya complexity & optimism berpengaruh signifikan (R²=0.492) | Sampel kecil; satu kota; 11/13 variabel ditolak |
| 5 | Putri, Mulyadi, Fajarini & Eriyansyah | 2023 | Kualitatif, wawancara mendalam, observasi | UMKM Kota Palembang | Transformasi digital berjalan tapi banyak UMKM masih konvensional | Tidak ada pengukuran kuantitatif; satu kota |

**Pola yang terlihat — Metode dominan:** Kualitatif-deskriptif (3/5 paper); studi kuantitatif masih minoritas dan memiliki keterbatasan model
**Limitasi yang berulang:** Cakupan geografis sempit (satu kota/desa); tidak mengukur dampak kinerja secara kuantitatif; sampel kecil; literasi digital rendah disebutkan berulang tanpa dimodelkan secara empiris

---

## Latihan 2 — Gap Identification

Berdasarkan tabel di Latihan 1, identifikasi gap.

| Jenis Gap | Ditemukan? | Gap Statement |
|-----------|-----------|---------------|
| Performance Gap | ✅ Ya | Model penjelasan kinerja UMKM pasca adopsi teknologi masih sangat lemah — R² tertinggi hanya 49.2% (Puspitaningsih et al., 2022) dan hanya 8.1% untuk kinerja langsung (Mustafa & Yaakub, 2018). Mayoritas paper sama sekali tidak mengukur kinerja bisnis secara kuantitatif. |
| Method Gap | ✅ Ya | Dominasi metode kualitatif menyebabkan kurangnya bukti statistik yang dapat digeneralisasi. SEM-PLS yang digunakan Puspitaningsih et al. (2022) adalah yang paling canggih, namun sampelnya terlalu kecil (n=50) untuk representatif. |
| Data Gap | ✅ Ya | Seluruh studi Indonesia hanya mencakup satu kota atau satu desa. Tidak ada studi dengan sampel multi-kota atau multi-provinsi yang dapat mencerminkan heterogenitas kondisi digital UMKM Indonesia. |
| Context Gap | ✅ Ya | Tidak ada studi yang membedakan adopsi teknologi berdasarkan sektor usaha (makanan, fashion, jasa, perdagangan) atau tingkat kematangan digital UMKM. UMKM diperlakukan sebagai kelompok homogen. |

**Gap utama yang dipilih:** Minimnya studi kuantitatif multi-lokasi yang memodelkan faktor-faktor adopsi teknologi digital terhadap kinerja UMKM secara komprehensif dan dapat digeneralisasi di konteks Indone
**Mengapa gap ini penting (bukan sekadar "belum ada yang meneliti")?**
> Tanpa model kuantitatif yang valid dan berskala luas, rekomendasi kebijakan digitalisasi UMKM — seperti program Kemenkominfo atau Kemenkop-UKM — tidak memiliki landasan empiris yang cukup kuat untuk menentukan intervensi mana (pelatihan SDM, infrastruktur, subsidi perangkat) yang paling efektif meningkatkan kinerja nyata UMKM. Studi kualitatif yang ada hanya menggambarkan fenomena permukaan tanpa kemampuan prediksi atau generalisasi.

---

## Latihan 3 — Baseline Selection

Pilih 2 baseline dari literatur yang sudah dibaca.

| # | Baseline | Mengapa Relevan | Mengapa Representatif | Apakah SOTA? | Sumber |
|---|----------|----------------|----------------------|-------------|--------|
| 1 | Regresi sederhana: Adopsi Inovasi & Teknologi → Kinerja UKM | Task identik: mengukur pengaruh langsung adopsi teknologi terhadap kinerja perusahaan UMKM | Merupakan kerangka yang paling banyak dipakai di literatur UKM Asia Tenggara sebagai titik tolak pengukuran kinerja | Bukan SOTA, tetapi *common baseline* yang menjadi referensi banyak riset lanjutan | Mustafa & Yaakub (2018) |
| 2 | SEM-PLS dengan TOE + TRI Framework → Adopsi Cloud Computing UMKM | Task relevan: memodelkan determinan adopsi teknologi pada UMKM secara multivariat dengan kombinasi perspektif organisasi dan individu | Kerangka TOE diakui sebagai salah satu model adopsi teknologi organisasi yang paling banyak dikutip di literatur IS | Bukan SOTA, namun paling komprehensif di antara kelima paper; cocok sebagai pembanding model yang lebih sederhana | Puspitaningsih et al. (2022) |

**Apakah pemilihan baseline ini bisa dianggap straw man?** [ ] Ya / [❌ ] Tidak
> Justifikasi:Kedua baseline dipilih karena keduanya merupakan studi yang secara langsung mengukur adopsi teknologi dan/atau kinerja UMKM dengan metode yang berbeda (regresi vs SEM-PLS). Keduanya bukan dibuat lemah secara artifisial — justru merepresentasikan best practice yang tersedia dalam literatur. Penelitian lanjutan yang ingin melampaui keduanya harus secara eksplisit menunjukkan di mana celah metodologis atau kontekstual kedua baseline ini tidak mampu menjawab.

---

## Refleksi

> Apa perbedaan antara "belum ada yang meneliti ini" (klaim tanpa bukti) dengan research gap yang valid? Bagaimana cara membuktikan bahwa sebuah gap benar-benar ada?

**Jawaban:**
> **"Belum ada yang meneliti"** adalah klaim topografi semata — ia hanya menyatakan ketiadaan tanpa menjelaskan mengapa ketiadaan itu penting. Klaim ini mudah dibantah (mungkin memang tidak ada karena tidak relevan atau sudah implisit dijawab oleh studi lain).
>
> **Research gap yang valid** adalah argumentasi kausal: (1) ada pertanyaan penting yang belum terjawab secara memadai, (2) ketidakmampuan literatur sebelumnya dapat dibuktikan secara spesifik (misal: R² rendah, sampel tidak representatif, metode tidak sesuai pertanyaan), dan (3) menjawab gap ini akan menghasilkan kontribusi nyata — baik bagi ilmu pengetahuan maupun bagi praktisi.
>
> **Cara membuktikan gap benar-benar ada:**
> - Lakukan literature matrix secara sistematis dan tunjukkan pola limitasi yang berulang lintas studi
> - Tunjukkan secara kuantitatif kelemahan model (R² rendah, variabel penting tidak signifikan, sampel tidak representatif)
> - Bandingkan dengan kebutuhan empiris nyata (misalnya: kebijakan pemerintah membutuhkan data nasional, tapi semua studi hanya satu kota)
> - Pastikan gap yang ditemukan bukan karena peneliti tidak menemukan studi tersebut, melainkan karena studi tersebut memang belum dilakukan — ini membutuhkan pencarian sistematis yang dapat direproduksi (PRISMA, query terdokumentasi, database yang jelas)
