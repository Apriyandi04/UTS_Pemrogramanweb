# 🎓 Sistem Rekap & Manajemen Nilai Mahasiswa
### 📌 Tugas Project UTS Pemrograman Web

[![PHP Version](https://img.shields.io/badge/PHP-8.x-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)](https://getbootstrap.com/)
[![AdminLTE](https://img.shields.io/badge/AdminLTE-v4-0073B7?style=for-the-badge&logo=adminlte&logoColor=white)](https://adminlte.io/)
[![XAMPP](https://img.shields.io/badge/XAMPP-Supported-FB7A24?style=for-the-badge&logo=xampp&logoColor=white)](https://www.apachefriends.org/)

Aplikasi berbasis web untuk mengelola dan merekap data nilai mahasiswa secara terstruktur, interaktif, dan efisien. Sistem ini dibangun menggunakan **PHP Native** yang terhubung ke basis data **MySQL**, dengan tampilan antarmuka modern responsif berbasis template **AdminLTE 4** dan **Bootstrap 5**.

---

## 📑 Daftar Isi

- [Tentang Proyek](#-tentang-proyek)
- [Fitur Utama](#-fitur-utama)
- [Kriteria & Sistem Penilaian](#-kriteria--sistem-penilaian)
- [Teknologi yang Digunakan](#-teknologi-yang-digunakan)
- [Struktur Direktori Proyek](#-struktur-direktori-proyek)
- [Struktur Database](#-struktur-database)
- [Panduan Instalasi & Menjalankan](#-panduan-instalasi--menjalankan)
- [Panduan Penggunaan](#-panduan-penggunaan)
- [Pengembang](#-pengembang)

---

## 💡 Tentang Proyek

Proyek ini dikembangkan sebagai pemenuhan **Ujian Tengah Semester (UTS) Mata Kuliah Pemrograman Web**. Aplikasi ini menyediakan solusi komprehensif bagi dosen atau administrator akademik untuk mencatat, memperbarui, mencari, mengurutkan, dan mengarsipkan data nilai mahasiswa beserta foto profil masing-masing mahasiswa secara aman dan praktis.

Sistem dilengkapi fungsi logika otomatis yang mampu mengonversi nilai angka akhir ke dalam nilai grade huruf (A, B, C, D, E) dan predikat kelulusan tanpa perlu input manual.

---

## ✨ Fitur Utama

- 🔄 **CRUD Nilai Mahasiswa Lengkap**:
  - **Create**: Menambahkan data nilai mahasiswa baru beserta upload foto profil.
  - **Read**: Menampilkan data nilai mahasiswa dalam bentuk tabel yang rapi.
  - **Update**: Memperbarui informasi mahasiswa, nilai akhir, serta foto mahasiswa.
  - **Delete**: Menghapus data mahasiswa dari database dengan konfirmasi interaktif.
- 🧮 **Otomatisasi Hitung Nilai & Predikat**: Nilai huruf dan predikat dihitung secara instan oleh backend berdasarkan fungsi modular (`hitungNilai()`) saat data disimpan atau diubah.
- 🖼️ **Upload & Manajemen Foto Profil**: Mendukung unggah foto (JPG, JPEG, PNG, GIF, WEBP) dengan penamaan otomatis berbasis timestamp unik untuk mencegah file tertimpa.
- 🔍 **Live Search Realtime**: Pencarian instan berdasarkan Nama Mahasiswa maupun Predikat tanpa reload halaman.
- 🏷️ **Filter Berdasarkan Predikat**: Menyaring data berdasarkan kategori predikat (*Sangat Memuaskan, Memuaskan, Cukup, Kurang, Tidak Lulus*).
- ↕️ **Live Sorting Nilai Akhir**: Fitur pengurutan baris data berdasarkan nilai tertinggi (*Descending*) atau terendah (*Ascending*).
- 📄 **Dynamic Client-side Pagination**: Pengaturan pembagian data per halaman (pilihan 5, 10, atau 15 data) dilengkapi navigasi *First, Prev, Nomor Halaman, Next, dan Last*.
- 🪟 **Modal Dialog Interaktif**: Tambah, edit, dan hapus data menggunakan modal Bootstrap 5 sehingga alur kerja pengguna tetap berada di satu halaman.
- 🌓 **Tema Terang & Gelap (Light / Dark Mode)**: Terintegrasi dengan fitur beralih mode warna bawaan AdminLTE 4.

---

## 📊 Kriteria & Sistem Penilaian

Logika konversi nilai diimplementasikan pada file `latihan.php` menggunakan fungsi `hitungNilai($nilai_akhir)` dengan skala acuan berikut:

| Rentang Nilai Akhir | Nilai Huruf | Predikat | Keterangan |
| :---: | :---: | :---: | :--- |
| **80.51 – 100.00** | **A** | **Sangat Memuaskan** | Lulus dengan predikat istimewa |
| **60.51 – 80.50** | **B** | **Memuaskan** | Lulus dengan hasil baik |
| **50.51 – 60.50** | **C** | **Cukup** | Lulus standar minimal kelulusan |
| **34.51 – 50.50** | **D** | **Kurang** | Tidak memenuhi batas standar kelulusan |
| **00.00 – 34.50** | **E** | **Tidak Lulus** | Gagal memenuhi capaian pembelajaran |
| *Nilai Lain / Invalid* | *Invalid* | *Invalid* | Nilai di luar batas 0 – 100 |

---

## 🛠️ Teknologi yang Digunakan

| Komponen | Teknologi | Keterangan |
| :--- | :--- | :--- |
| **Bahasa Pemrograman** | PHP 8.x | Pemrosesan backend, logika validasi, manipulasi file, dan query database |
| **Database** | MySQL / MariaDB | Penyimpanan tabel data nilai dan riwayat timestamp |
| **UI Framework** | AdminLTE v4 & Bootstrap 5.3 | Desain dasbor administratif modern, responsif, dan ramah pengguna |
| **Icons & Font** | Bootstrap Icons & Source Sans 3 | Ikonografi antarmuka dan tipografi modern |
| **Frontend Scripting** | Vanilla JavaScript | Operasi DOM, filter data, live search, sorting, dan paginasi client-side |
| **Web Server Environment** | Apache (XAMPP) | Lingkungan pengembangan web lokal |

---

## 📁 Struktur Direktori Proyek

```text
UTS/
├── css/                     # Berkas CSS dan stylesheet tema AdminLTE 4
│   ├── adminlte.css
│   ├── adminlte.min.css
│   └── ...
├── uploads/                 # Direktori penyimpanan berkas foto mahasiswa yang diunggah
│   ├── 1792950649_seolinah.jpg
│   └── ...
├── connect.php              # Inisialisasi koneksi PHP ke basis data MySQL (db5a)
├── latihan.php              # Modul fungsi logika konversi hitungNilai()
├── viewdata.php             # Halaman utama dasbor data nilai mahasiswa (tampilan bersih)
├── datatable.php            # Halaman data nilai mahasiswa alternatif dengan sidebar navigasi
├── insertnilai.php          # Pemrosesan form tambah data mahasiswa (metode POST)
├── updatenilai.php          # Pemrosesan form edit/update data mahasiswa (metode POST)
├── deletenilai.php          # Pemrosesan aksi hapus data mahasiswa (metode POST/GET)
├── nilaimhsw.sql            # Skema tabel database dan data awal (database dump)
└── README.md                # Dokumentasi lengkap proyek
```

---

## 🗄️ Struktur Database

Database default yang digunakan adalah **`db5a`** dengan tabel **`nilaimhsw`**.

### Skema Tabel `nilaimhsw`

```sql
CREATE TABLE `nilaimhsw` (
  `nim` varchar(10) NOT NULL,
  `namamhsw` varchar(30) NOT NULL,
  `nilaiakhir` float NOT NULL,
  `nilaihuruf` varchar(5) DEFAULT NULL,
  `predikat` varchar(20) DEFAULT NULL,
  `create_date` timestamp NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  `modified_date` timestamp NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  `file_path` varchar(100) DEFAULT NULL,
  PRIMARY KEY (`nim`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```

### Rincian Kolom

| Nama Kolom | Tipe Data | Keterangan |
| :--- | :--- | :--- |
| `nim` | `VARCHAR(10)` | **Primary Key**: Nomor Induk Mahasiswa (unik) |
| `namamhsw` | `VARCHAR(30)` | Nama lengkap mahasiswa |
| `nilaiakhir` | `FLOAT` | Nilai akhir angka mahasiswa (skala 0 - 100) |
| `nilaihuruf` | `VARCHAR(5)` | Grade nilai (A / B / C / D / E) |
| `predikat` | `VARCHAR(20)` | Predikat kelulusan sesuai skala penilaian |
| `create_date` | `TIMESTAMP` | Waktu pencatatan data pertama kali |
| `modified_date` | `TIMESTAMP` | Waktu terakhir data diperbarui |
| `file_path` | `VARCHAR(100)` | Lokasi path foto mahasiswa (contoh: `uploads/nama_file.jpg`) |

---

## 🚀 Panduan Instalasi & Menjalankan

Ikuti langkah-langkah berikut untuk menjalankan proyek ini di komputer lokal Anda:

### 1. Prasyarat
- Pastikan aplikasi **XAMPP** (dengan PHP 8.x dan MySQL) sudah terpasang di komputer Anda.
- Web Browser modern (Google Chrome, Mozilla Firefox, Microsoft Edge, dll).

### 2. Penempatan File Proyek
Pastikan folder proyek ini berada di dalam direktori `htdocs` XAMPP:
```bash
# Path standar Windows:
C:\xampp\htdocs\UTS
```

### 3. Menjalankan Web Server & Database
1. Buka aplikasi **XAMPP Control Panel**.
2. Klik tombol **Start** pada modul **Apache**.
3. Klik tombol **Start** pada modul **MySQL**.

### 4. Konfigurasi Basis Data
1. Buka web browser dan akses [http://localhost/phpmyadmin](http://localhost/phpmyadmin).
2. Buat database baru dengan nama:
   ```sql
   db5a
   ```
3. Pilih database `db5a`, kemudian buka menu **Import**.
4. Klik **Choose File** dan pilih file `nilaimhsw.sql` yang berada di dalam folder proyek ini.
5. Klik tombol **Import** (atau **Go**) di bagian bawah untuk mengeksekusi dump SQL.

### 5. Konfigurasi Koneksi (`connect.php`)
Secara default, file [connect.php](connect.php) menggunakan konfigurasi standar XAMPP:
```php
$servername = "localhost";
$username   = "root";
$password   = "";
$dbname     = "db5a";
```
*Jika Anda menggunakan port khusus atau password MySQL yang berbeda, sesuaikan nilai variabel di atas.*

### 6. Mengakses Aplikasi
Buka browser dan kunjungi salah satu URL berikut:
- **Tampilan Utama (Dashboard Bersih)**:  
  [http://localhost/UTS/viewdata.php](http://localhost/UTS/viewdata.php)
- **Tampilan Alternatif (Dengan Sidebar AdminLTE)**:  
  [http://localhost/UTS/datatable.php](http://localhost/UTS/datatable.php)

---

## 📖 Panduan Penggunaan

1. **Melihat Data**:
   - Seluruh data mahasiswa akan ditampilkan dalam tabel utama lengkap dengan foto profil, NIM, nama, nilai akhir, nilai huruf, predikat, dan tanggal perubahan.
2. **Menambahkan Data Baru**:
   - Klik tombol **Tambah Data Nilai** berwarna biru di pojok kanan atas tabel.
   - Isi NIM, Nama Mahasiswa, Nilai Akhir (angka), dan pilih file foto (opsional).
   - Klik **Simpan Data**. Nilai huruf dan predikat akan otomatis terhitung.
3. **Mengedit Data**:
   - Klik tombol **Edit** (ikon pensil kuning) pada baris data mahasiswa yang ingin diperbarui.
   - Ubah data yang diinginkan (Nama, Nilai Akhir, atau ganti Foto).
   - Klik **Simpan Perubahan**.
4. **Menghapus Data**:
   - Klik tombol **Hapus** (ikon tempat sampah merah) pada baris data mahasiswa.
   - Konfirmasi dialog penghapusan pada modal yang muncul.
5. **Pencarian & Filter**:
   - Ketikkan nama atau predikat di kolom input pencarian (*live filter* tanpa reload).
   - Gunakan drop-down *Semua Predikat* untuk memfilter mahasiswa berdasarkan predikat tertentu.
6. **Pengurutan (Sort)**:
   - Klik ikon panah di samping judul kolom **Nilai Akhir** untuk mengurutkan nilai dari yang tertinggi ke terendah atau sebaliknya.
7. **Paginasi**:
   - Pilih opsi jumlah baris (5, 10, atau 15) pada menu drop-down di pojok kiri bawah tabel untuk menyesuaikan kenyamanan tampilan.

---

## 👨‍💻 Pengembang

- **Nama**: [Apriyandi04](https://github.com/Apriyandi04)
- **Repositori**: [UTS_Pemrogramanweb](https://github.com/Apriyandi04/UTS_Pemrogramanweb)
- **Program Studi**: Teknik Informatika / Pemrograman Web

---
*Dibuat untuk keperluan akademik - Ujian Tengah Semester (UTS) Pemrograman Web.*
