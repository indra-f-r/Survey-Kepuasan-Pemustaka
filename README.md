# Library Survey Plugin for SLiMS

Plugin **Survey Kepuasan Pemustaka** untuk **SLiMS (Senayan Library Management System)**.

Plugin ini memungkinkan perpustakaan mengumpulkan **survey kepuasan pengguna** secara digital melalui OPAC maupun perangkat mobile.

Plugin dirancang khusus untuk **perpustakaan sekolah**, namun tetap fleksibel untuk digunakan pada berbagai jenis perpustakaan.

---

# ✨ Features

## Survey Kepuasan Pemustaka

Plugin menyediakan **15 pertanyaan survey** menggunakan skala Likert:

- Sangat Tidak Setuju
- Tidak Setuju
- Netral
- Setuju
- Sangat Setuju

Kategori survey:

| Kategori | Jumlah Pertanyaan |
|--------|--------|
| Fasilitas Perpustakaan | 3 |
| Layanan Perpustakaan | 3 |
| Koleksi Perpustakaan | 3 |
| Sistem Perpustakaan | 3 |
| Kenyamanan Perpustakaan | 3 |

---

## Autocomplete Anggota

Pengguna dapat mencari anggota dengan mengetik:

```
nama anggota
```

Setelah dipilih akan otomatis mengisi:

```
member_id
kelas / rombel
```

---

## Validasi Pengisian

Fitur validasi:

- Semua pertanyaan wajib dijawab
- Math challenge anti spam
- 1 anggota hanya dapat mengisi survey **1 kali per hari**

---

## Dashboard Laporan Survey

Plugin menyediakan halaman laporan yang menampilkan:

- Total responden
- Nilai rata-rata
- Nilai tertinggi
- Nilai terendah
- Grafik kepuasan
- Responden per kelas
- Saran pemustaka

---

## Filter Periode

Laporan dapat difilter berdasarkan tanggal.

Periode otomatis ditampilkan sebagai:

```
Bulan Maret 2026
Triwulan I Tahun 2026
Semester I Tahun 2026
Tahun 2026
```

---

## Grafik Statistik

Plugin menggunakan library:

```
Chart.js
```

Untuk menampilkan grafik kepuasan layanan.

---

## Responsive Design

Survey dirancang agar nyaman digunakan pada:

- Desktop
- Tablet
- Smartphone

Optimasi mobile:

- radio button besar
- teks pertanyaan besar
- layout full width
- tampilan mudah dibaca

---

# 📱 Mobile Friendly

Survey dioptimalkan untuk pengisian melalui smartphone.

Keuntungan:

- siswa dapat mengisi survey dengan mudah
- tampilan sederhana
- navigasi cepat
- tidak perlu zoom manual

---

# 🗂 Folder Structure

```
plugins/
library_survey/
│
├── library_survey.plugin.php
├── survey.php
├── submit.php
├── index.php
├── search_member.php
└── README.md
```

---

# ⚙️ Installation

## 1. Download Plugin

Clone repository:

```bash
git clone https://github.com/indra-f-r/library_survey
```

---

## 2. Copy Plugin ke Folder SLiMS

Salin folder plugin ke:

```
slims/plugins/library_survey/
```

---

## 3. Aktifkan Plugin

Login ke **Admin SLiMS**

Masuk ke:

```
Admin → System → Plugin
```

Aktifkan plugin:

```
Library Survey
```

---

## 4. Database Otomatis Dibuat

Saat plugin aktif, sistem akan membuat tabel:

```
library_survey
```

Struktur tabel:

| Field | Keterangan |
|------|------|
| id | ID survey |
| member_id | ID anggota |
| member_name | Nama anggota |
| member_class | Kelas / rombel |
| survey_date | Tanggal survey |
| q1 - q15 | Jawaban survey |
| saran | Saran pengguna |
| created_at | Timestamp |

---

# 🌐 Access Survey

Survey dapat diakses melalui URL:

```
plugins/library_survey/survey.php
```

Contoh:

```
https://domainanda/plugins/library_survey/survey.php
```

---

# 🔗 Friendly URL Routing (Optional)

Agar URL lebih rapi dapat menggunakan `.htaccess`.

Contoh URL:

```
https://domainanda/survey
```

Tambahkan di `.htaccess`:

```apache
RewriteRule ^survey/?$ plugins/library_survey/survey.php [L]
RewriteRule ^survey/submit/?$ plugins/library_survey/submit.php [L]
RewriteRule ^survey/report/?$ plugins/library_survey/index.php [L]
```

URL menjadi:

```
/survey
/survey/report
```

---

# 📊 Dashboard Report

Laporan survey dapat diakses dari:

```
Admin → Reporting → Library Survey
```

Dashboard menampilkan:

- Total responden
- Nilai rata-rata
- Nilai tertinggi
- Nilai terendah
- Grafik kepuasan
- Responden per kelas
- Saran pemustaka

---

# 🧠 Calculation Method

Nilai kategori dihitung dari rata-rata pertanyaan.

Contoh:

```
Fasilitas = (Q1 + Q2 + Q3) / 3
```

Nilai keseluruhan:

```
Rata-rata semua kategori
```

---

# 🛡 Security

Plugin memiliki beberapa mekanisme keamanan.

### Math Challenge

Contoh:

```
7 + 5 = ?
```

Digunakan untuk mencegah spam bot.

---

### Input Validation

- Semua pertanyaan wajib dijawab
- Saran dibatasi maksimal **255 karakter**

---

### Survey Limit

Setiap anggota hanya dapat mengisi survey:

```
1 kali per hari
```

---

# 🧩 Integration with SLiMS

Plugin menggunakan:

```
SLiMS Plugin API
```

Menu otomatis muncul pada modul:

```
Reporting
```

---

# 🖥 Technology Stack

Plugin menggunakan teknologi:

- PHP
- MySQL
- JavaScript
- Chart.js
- HTML5
- CSS3

---

# 🚀 Roadmap

Pengembangan berikutnya:

- Export Excel laporan
- Export PDF laporan
- Grafik kepuasan per kelas
- Grafik tren bulanan
- Survey anonim
- Dashboard statistik lanjutan

---

# 🤝 Contributing

Kontribusi sangat terbuka.

Langkah kontribusi:

1. Fork repository
2. Buat branch baru
3. Commit perubahan
4. Submit pull request

---

# 👨‍💻 Author

**Indra Febriana Rulliawan**

GitHub:

```
https://github.com/indra-f-r
```

---

# 📄 License

GPL v3

Plugin ini bebas digunakan dan dimodifikasi sesuai kebutuhan perpustakaan.

---

# ❤️ Support

Jika plugin ini membantu perpustakaan Anda, silakan beri ⭐ pada repository GitHub.

---

# SLiMS Community

Plugin ini dibuat untuk mendukung ekosistem:

```
SLiMS - Senayan Library Management System
```

Website resmi:

```
https://slims.web.id
```
