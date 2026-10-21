# Tugas 1: Eksplorasi dan Analisis Dataset Besar Indonesia

Template untuk Tugas 1 mata kuliah Analisis Big Data. Setelah repository GitHub Classroom dibuat, ubah nama repository menjadI `tugas1-[username_github]`.

## Milestone

| Tahap | Target | Bukti yang dikumpulkan |
|---|---|---|
| Milestone 1 | Pertemuan 3 | Dataset >= 500 MB atau > 1 juta baris, `data/README.md`, dan `notebooks/01_data_profiling.ipynb` |
| Milestone 2 | Pertemuan 5 | Cleaning dengan Polars dan profiling DuckDB `SUMMARIZE` |
| Milestone 3 | Pertemuan 8 | Analisis temporal/ruang dan minimal 6 visualisasi interaktif |
| Final | Pertemuan 10 | Minimal 5 insight, Dockerfile, dan dokumentasi akhir |

## Output yang Diharapkan.

Pada final submission, repository harus menghasilkan analisis yang dapat dijalankan ulang dari awal dan memuat:

- Dataset Indonesia yang terdokumentasi, berukuran minimal 500 MB atau lebih dari 1 juta baris, beserta instruksi unduhnya.
- Notebook profiling, cleaning, serta EDA yang dapat dieksekusi berurutan.
- Cleaning dan validasi data untuk missing values, duplikasi, outlier, serta aturan kualitas yang relevan dengan dataset.
- Analisis temporal atau spasial, minimal 6 visualisasi interaktif dengan Plotly atau Altair, dan minimal 5 insight analitik yang didukung hasil analisis.
- Environment yang dapat direproduksi melalui `Dockerfile`, `requirements.txt`, dan petunjuk eksekusi di README.
- Riwayat commit bertahap yang menunjukkan proses kerja pada setiap milestone.

## Kaitan dengan Materi Perkuliahan

| Materi | Pertemuan | Penerapan pada Tugas 1 |
|---|:---:|---|
| Polars dan lazy evaluation | 2 | Profiling dan transformasi dataset besar dengan `scan_*`, expressions, dan pipeline efisien. |
| DuckDB dan format data | 3 | Query analitik serta profiling dengan `SUMMARIZE`; gunakan Parquet bila sesuai. |
| Data quality dan cleaning | 4 | Tangani missing values, duplikasi, outlier, dan validasi data. |
| EDA dan visualisasi | 5 | Bangun visualisasi interaktif serta rumuskan insight analitik. |
| Time series | 6 | Terapkan analisis pola waktu atau pola spasial yang relevan dengan dataset. |
| Dask, NLP, dan ML | 7-9 | Opsional sebagai pengembangan jika relevan dengan skala dan pertanyaan analisis. |
| Streamlit dan Docker | 10-11 | Dokumentasikan environment Docker; dashboard Streamlit bersifat opsional untuk Tugas 1. |

## Ringkasan Penilaian

Nilai Tugas 1 berbobot 25% dari nilai akhir. Penilaian lengkap ada di dokumen spesifikasi tugas; ringkasannya sebagai berikut.

| Aspek | Bobot | Indikator utama |
|---|:---:|---|
| Konsistensi commit dan GitHub workflow | 20% | Commit bertahap, pesan deskriptif, struktur repository rapi, dan pemeriksaan otomatis lulus. |
| Data handling dengan Polars dan DuckDB | 25% | Pengolahan data besar efisien, memakai Polars dan DuckDB sesuai peran masing-masing. |
| Cleaning dan data quality | 15% | Profiling, validasi, serta penanganan null dan outlier terdokumentasi. |
| Visualisasi dan insight | 25% | Visualisasi interaktif informatif dan insight analitik yang didukung data. |
| Reproduktivitas dan Docker | 15% | Dockerfile, dependency, dan instruksi eksekusi memungkinkan proyek dijalankan ulang. |

Target kualitas tertinggi adalah analisis yang efisien, terdokumentasi, dapat direproduksi, dan memperlihatkan proses kerja konsisten sepanjang milestone; bukan hanya hasil akhir yang terlihat baik.

## Struktur Repository

```text
.
â”œâ”€â”€ .github/workflows/lint_check.yml
â”œâ”€â”€ data/README.md
â”œâ”€â”€ notebooks/
â”‚   â”œâ”€â”€ 01_data_profiling.ipynb
â”‚   â”œâ”€â”€ 02_data_cleaning.ipynb
â”‚   â””â”€â”€ 03_eda_and_insights.ipynb
â”œâ”€â”€ output/figures/
â”œâ”€â”€ src/
â”œâ”€â”€ Dockerfile
â”œâ”€â”€ requirements.txt
â””â”€â”€ README.md
```

# Tugas 1 Analisis Big Data 2026

## Persiapan GitHub

### 1. Fork Repository Tugas

Fork repository berikut ke akun GitHub masing-masing:

https://github.com/UMM-GURU/tugas1-abd-2026.git

Langkah-langkah:

1. Login ke GitHub.
2. Buka repository tugas.
3. Klik tombol **Fork** di pojok kanan atas.
4. Tunggu hingga GitHub membuat salinan repository ke akun Anda.

Setelah selesai, Anda akan memiliki repository dengan alamat seperti:

```text
https://github.com/USERNAME-ANDA/tugas1-abd-2026.git
```

---

### 2. Clone Repository Hasil Fork

Buka Terminal, Git Bash, atau Command Prompt lalu jalankan:

```bash
git clone https://github.com/USERNAME-ANDA/tugas1-abd-2026.git
cd tugas1-abd-2026
```

Ganti `USERNAME-ANDA` dengan username GitHub Anda.

---

## Menjalankan Project

Pastikan Docker sudah terpasang pada komputer Anda.

### Build Docker Image

```bash
docker build -t id-reg-kg-2511 .
```

### Jalankan Container

```bash
docker run --rm -p 8888:8888 -v "$(pwd)":/home/jovyan/work id-reg-kg-2511
```

### Membuka JupyterLab

Buka browser dan akses:

http://localhost:8888/lab

> **Catatan:** Konfigurasi Dockerfile menjalankan JupyterLab tanpa password atau token untuk penggunaan lokal. Jangan gunakan konfigurasi ini pada server atau jaringan publik.

---

## Menyiapkan Dataset

1. Letakkan dataset yang akan digunakan pada folder:

```text
data/raw/
```

2. Buka notebook profiling atau notebook yang digunakan.
3. Sesuaikan nilai variabel `DATA_PATH` agar mengarah ke file dataset yang Anda gunakan.

Contoh:

```python
DATA_PATH = "data/raw/nama_dataset.csv"
```

---

## Mengerjakan Tugas

1. Baca seluruh instruksi yang terdapat pada notebook.
2. Kerjakan setiap bagian sesuai perintah.
3. Simpan perubahan secara berkala.

---

## Commit Perubahan

Setelah tugas selesai dikerjakan, simpan hasil pekerjaan ke Git menggunakan perintah berikut:

```bash
git add .
git commit -m "Menyelesaikan Tugas 1 Analisis Big Data"
```

Anda dapat mengganti pesan commit sesuai kebutuhan.

---

## Push ke Repository GitHub

Kirim hasil pekerjaan ke repository GitHub milik Anda:

```bash
git push origin main
```

Apabila branch utama bernama `master`, gunakan:

```bash
git push origin master
```

---

## Verifikasi Pengumpulan

1. Buka repository GitHub milik Anda.
2. Pastikan file yang telah dikerjakan sudah muncul.
3. Pastikan terdapat minimal satu commit hasil pekerjaan Anda.
4. Salin URL repository Anda untuk keperluan penilaian jika diminta dosen.

Contoh URL repository:

```text
https://github.com/USERNAME-ANDA/tugas1-abd-2026
```

---

## Menjalankan Project

```bash
docker build -t id-reg-kg-2511 .
docker run --rm -p 8888:8888 -v "$(pwd)":/home/jovyan/work id-reg-kg-2511
```

Buka JupyterLab pada `http://localhost:8888/lab`. Konfigurasi Dockerfile menjalankan JupyterLab tanpa password atau token untuk penggunaan lokal. Jangan gunakan konfigurasi ini pada server atau jaringan publik. Letakkan dataset pada `data/raw/`, lalu sesuaikan `DATA_PATH` di notebook profiling.

## Aturan Teknis

- Gunakan Polars untuk manipulasi data dan DuckDB untuk analitik SQL.
- Dataset harus minimal 500 MB atau lebih dari 1 juta baris.
- Jangan commit file data besar; simpan instruksi unduhan dan sumber data pada `data/README.md`.
- Gunakan commit bertahap dan pesan yang jelas, misalnya `feat: add initial dataset profiling`.

## Integritas Akademik dan Penggunaan AI

- Dilarang menyalin kode, laporan, atau visualisasi mahasiswa lain maupun repository publik tanpa sitasi dan atribusi yang jelas.
- Dilarang menggunakan jasa joki atau menyerahkan pekerjaan yang tidak dapat dijelaskan sendiri.
- AI boleh digunakan untuk belajar, mencari rujukan, menjelaskan konsep, atau debugging. AI tidak menggantikan tanggung jawab mahasiswa atas kebenaran dan kualitas solusi.
- Mahasiswa wajib dapat menjelaskan setiap bagian kode, menjalankan serta memverifikasi ulang hasilnya, dan memastikan penggunaan Polars serta DuckDB sesuai standar kuliah.
- Setiap penggunaan AI harus dicantumkan pada bagian AI Disclosure Statement di bawah.
- Pelanggaran pertama bernilai 0 untuk tugas terkait; pelanggaran berikutnya dapat berakibat nilai E untuk mata kuliah sesuai ketentuan akademik.

## Ringkasan Milestone 1 dan 2

### Milestone 1: Data Profiling

- Dataset regulasi mencakup 748.558 baris pada hasil pemeriksaan.
- Profiling meliputi struktur kolom, tipe data, nilai kosong, keunikan `global_id`, validitas tahun, tanggal berlaku, dan indikasi masalah encoding.
- Notebook profiling: `notebooks/01_data_profiling.ipynb`.

### Milestone 2: Data Cleaning dan Validasi

- Proses cleaning dan validasi didokumentasikan dalam `notebooks/02_data_cleaning.ipynb`.
- Validasi akhir mencatat 748.558 baris dan 748.558 `global_id` unik, tanpa `global_id` null maupun duplikat.
- Sebanyak 567 nilai tahun 0000 dan 2 nilai tahun masa depan ditandai untuk pemeriksaan.
- Sebanyak 259.467 baris memiliki `effective_date` kosong.
- Sebanyak 61 baris ditandai memiliki indikasi masalah encoding pada `enacting_body`.
- Hasil validasi tersedia di `output/data_quality_report.json`.
- Ringkasan milestone tersedia di `docs/milestone_summary.md`.

### Validasi Docker

- Docker image berhasil dibangun dengan nama `id-reg-kg-2511`.
- Container berhasil berjalan dengan status `healthy`.
- JupyterLab berhasil diakses melalui `http://localhost:8888`.
- Dataset Parquet besar dikecualikan dari Git dan Docker build context. Petunjuk penyediaan dataset tersedia di `data/README.md`.

## AI Disclosure Statement

> **Alat AI yang digunakan:** ChatGPT (OpenAI).
>
> **Bagian yang dibantu:** Penjelasan konsep, debugging Git dan Docker, serta penyusunan dokumentasi proyek.
>
> **Verifikasi yang dilakukan:** Memeriksa hasil profiling dan cleaning, meninjau laporan kualitas data, membangun Docker image, menjalankan container hingga berstatus healthy, dan memastikan JupyterLab dapat diakses secara lokal. Hasil pekerjaan diperiksa kembali sebelum pengumpulan.
