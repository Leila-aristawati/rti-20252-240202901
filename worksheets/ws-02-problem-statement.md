# WS-02: Problem Statement

> **Bab 2 — Problem Formulation & System Context**

---

## Ringkasan Materi

### Problem Formation Model

Masalah riset melewati 5 tahap transformasi. Melompat langsung dari Reality ke Variable adalah kesalahan paling umum.

```
Reality → Observed Issue (Symptom) → Diagnosed Problem (Root Cause)
→ Researchable Problem (Scoped) → Measurable Variable (Operationalized)
```

### Topic ≠ Problem ≠ Research Problem

| Level | Contoh | Status |
|-------|--------|--------|
| **Topik** | Keamanan IoT | Terlalu luas, tidak bisa diuji |
| **Problem** | MQTT tidak terenkripsi | Spesifik tapi belum riset |
| **Research Problem** | Belum ada studi membandingkan overhead TLS 1.3 vs DTLS pada MQTT di IoT RAM < 64KB | Bisa dirancang eksperimennya |

### Symptom vs Root Cause

Apa yang diamati (gejala) ≠ mengapa terjadi (akar masalah). Gunakan **5 Whys** atau **Fishbone Diagram** untuk menggali.

Contoh: "User meninggalkan checkout" (symptom) → "Waktu loading > 8 detik karena API call sequential" (root cause).

### System Thinking

Setiap masalah riset TI harus terikat pada komponen sistem: **Input → Process → Output → Outcome → Constraints → Stakeholders**.

### Problem Quality Check

Masalah riset yang layak harus memenuhi 5 kriteria:
- **Clarity** — Satu orang membaca akan paham
- **Measurability** — Ada metrik kuantitatif
- **Relevance** — Penting untuk domain
- **Testability** — Bisa gagal (falsifiable)
- **Impact** — Ada kontribusi jika terjawab

### Research vs Engineering

| Aspek | Engineering | Research |
|-------|------------|----------|
| Tujuan | Menyelesaikan masalah (*solve*) | Memahami dan membuktikan (*understand & prove*) |
| Masalah | Bug, error, fitur belum ada | Gap dalam pengetahuan |
| Scope | Selesaikan semua yang perlu | Batasi agar bisa dibuktikan |
| Output | Working system | Evidence, paper, replicable findings |

### Istilah Penting

- **Problem Statement** — Formulasi tertulis: konteks sistem + gap + dampak + justifikasi
- **System Context** — Deskripsi lengkap: input, proses, output, outcome, constraints, stakeholders
- **Problem Drift** — Masalah "bermutasi" dari pendahuluan ke metodologi karena statement awal tidak presisi
- **Solution-First Thinking** — Memulai dari solusi tanpa masalah yang jelas — berbahaya dalam riset
- **Operational Definition** — Definisi variabel yang cukup jelas agar peneliti lain bisa mengukur hal yang sama

---

## Template A.2 — Problem Statement Builder

```
PROBLEM STATEMENT BUILDER

Domain & Konteks
  Domain   : Sistem Informasi / Teknologi Informasi
  Konteks  : Penggunaan teknologi informasi pada UMKM di Indonesia

System Context
  Input       : Data operasional UMKM dan penggunaan teknologi
  Process     : Pemanfaatan teknologi informasi dalam aktivitas bisnis
  Output      : Informasi bisnis seperti laporan dan transaksi
  Outcome     : Kinerja UMKM (efisiensi, produktivitas, pendapatan)
  Constraints : Keterbatasan SDM, biaya, dan pemahaman teknologi
  Stakeholders: Pemilik UMKM, karyawan, pelanggan

Fenomena → Problem
  Fenomena yang diamati             : Meningkatnya penggunaan teknologi pada UMKM
  Gejala (symptom) yang terukur     : Tidak semua UMKM mengalami peningkatan kinerja
  Masalah yang didiagnosis          : Pemanfaatan teknologi belum optimal
  Masalah riset (researchable)      : Belum jelas pengaruh tingkat penggunaan TI terhadap kinerja UMKM
  Variabel yang terukur             : Tingkat penggunaan TI, kinerja UMKM

Problem Quality Check
  [✔] Clarity — Apakah satu orang membaca akan paham?
  [✔] Measurability — Apakah ada metrik kuantitatif?
  [✔] Relevance — Apakah penting untuk domain?
  [✔] Testability — Apakah bisa gagal?
  [✔] Impact — Apakah ada kontribusi jika terjawab?

Problem Statement (1 paragraf):
  Penggunaan teknologi informasi pada UMKM semakin meningkat, namun tidak semua pelaku usaha mengalami peningkatan kinerja yang signifikan. Hal ini menunjukkan adanya perbedaan dalam tingkat pemanfaatan teknologi yang digunakan. Oleh karena itu, diperlukan penelitian untuk menganalisis pengaruh tingkat penggunaan teknologi informasi terhadap kinerja UMKM secara terukur guna mengetahui sejauh mana teknologi dapat meningkatkan efisiensi dan produktivitas usaha.
```

---

## Latihan 1 — Dari Topik ke Masalah Riset

Pilih satu topik di bidang TI yang diminati. Transformasikan melalui 5 tahap Problem Formation Model.

**Topik awal:** Pengaruh penggunaan teknologi informasi terhadap kinerja UMKM

| Tahap | Hasil |
|-------|-------|
| Reality | Banyak UMKM mulai menggunakan teknologi informasi dalam operasional bisnis |
| Observed Issue (Symptom) | Tidak semua UMKM mengalami peningkatan kinerja meskipun sudah menggunakan teknologi |
| Diagnosed Problem (Root Cause) |Kurangnya pemahaman dan pemanfaatan teknologi informasi secara optimal |
| Researchable Problem |Belum jelas bagaimana pengaruh tingkat penggunaan teknologi informasi terhadap kinerja UMKM secara terukur |
| Measurable Variable |Tingkat penggunaan TI, kinerja UMKM (pendapatan, efisiensi, produktivitas) |

**Apakah terjebak solution-first thinking?** [ ] Ya / [✔] Tidak
> Jika ya, kembali ke tahap mana? ________________________

---

## Latihan 2 — System Context Decomposition

Gambarkan konteks sistem dari masalah riset di Latihan 1.

| Komponen | Deskripsi |
|----------|----------|
| Input | Data operasional UMKM, penggunaan aplikasi/teknologi |
| Process |Pengolahan data dan aktivitas bisnis menggunakan teknologi informasi |
| Output |Informasi bisnis (laporan, transaksi, data pelanggan) |
| Outcome |Peningkatan kinerja UMKM (efisiensi, pendapatan) |
| Constraints |Keterbatasan SDM, biaya, pemahaman teknologi |
| Stakeholders |Pemilik UMKM, karyawan, pelanggan |

**Komponen mana yang paling relevan dengan masalah riset?**  
Process (cara penggunaan teknologi informasi)

---

## Latihan 3 — Problem Quality Check

Evaluasi problem statement yang sudah dibuat menggunakan 5 kriteria.

| Kriteria | Skor (1-5) | Justifikasi |
|----------|-----------|-------------|
| Clarity | 4 |Sudah jelas, tapi bisa lebih spesifik pada jenis UMKM |
| Measurability | 5 |Ada variabel kuantitatif (kinerja, penggunaan TI) |
| Relevance | 5 |Penting untuk perkembangan UMKM |
| Testability | 5 |Bisa diuji dengan data |
| Impact | 4 |Berdampak pada peningkatan bisnis UMKM |

**Skor total:** 23 / 25

**Problem statement versi final (1 paragraf):**
> Penggunaan teknologi informasi pada UMKM semakin meningkat, namun tidak semua pelaku usaha mengalami peningkatan kinerja yang signifikan. Hal ini menunjukkan adanya perbedaan dalam tingkat pemanfaatan teknologi yang digunakan. Oleh karena itu, diperlukan penelitian untuk menganalisis pengaruh tingkat penggunaan teknologi informasi terhadap kinerja UMKM secara terukur, guna mengetahui sejauh mana teknologi dapat meningkatkan efisiensi dan produktivitas usaha.
> 

---

## Refleksi

Bandingkan "masalah" yang biasa ditemui saat coding (bug, error) dengan masalah riset. Apa perbedaan fundamental dalam cara mendefinisikan dan mendekati keduanya?

**Jawaban:**
> Masalah dalam coding biasanya bersifat teknis dan langsung terlihat seperti error atau bug yang harus segera diperbaiki. Sedangkan masalah riset lebih kompleks karena membutuhkan identifikasi akar masalah, pembuktian dengan data, serta perumusan yang sistematis agar dapat diuji secara ilmiah.
> 
