---
lab:
  title: 'Lab 1: Pemodelan Data'
  module: 'Module 2: Identify foundational components of Microsoft Power Platform'
---

# Lab 1: Pemodelan Data

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberi penyewa sebagai bagian dari penyediaan pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa disediakan untuk tujuan mendukung lab praktik langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk ekstensi. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa kampus dan program. Banyak instruktur dan administrator Bellow Colleges perlu menghadiri acara, dan membeli item. Secara historis, melacak pengeluaran ini merupakan sebuah tantangan. 

Administrasi kampus ingin memodernisasi sistem pelaporan pengeluaran mereka dengan menyediakan cara digital kepada karyawan untuk melaporkan pengeluaran. 

Selama kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi agar karyawan Bellows College dapat mengelola pengeluaran.

Terakhir, Anda akan mengimpor data sampel ke Microsoft Dataverse.

## Langkah-langkah lab tingkat tinggi

Untuk mempersiapkan lingkungan belajar Anda, Anda akan:

- Lihat [dokumen model data](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus Management.png) untuk deskripsi metadata (tabel dan hubungan). Anda bisa menahan ctrl + klik kiri atau klik kanan tautan untuk membuka dokumen model data di jendela baru.

- Buat tabel Pengeluaran

- Tambahkan beberapa data sampel. 

### Prasyarat

- Penyelesaian **Modul 1 Lab 0 - Memvalidasi lingkungan lab**

Hal-hal yang perlu dipertimbangkan sebelum memulai

- Konvensi penamaan - masukkan nama dengan hati-hati.

## Latihan 1: Buat Tabel Baru

**Tujuan:** Dalam latihan ini, Anda akan membuat tabel kustom baru untuk Pengeluaran.

### Tugas 1: Membuat Tabel dan Kolom Pengeluaran

Tabel **Pengeluaran** akan berisi informasi tentang pengeluaran individu yang dapat dikirimkan karyawan termasuk alasan, jenis, tanggal, dan jumlah.

1. Jika Anda belum masuk, masuk ke https://make.powerapps.com

1. Dari menu **Lingkungan** di kanan atas, pastikan lingkungan **Dev One** dipilih.

1. Menggunakan navigasi di sebelah kiri, pilih **Tabel**.

1. Pilih **+ Tabel baru** dan pilih **Atur properti tingkat lanjut**.

1. Untuk **Nama tampilan**, masukkan Pengeluaran

1. Pilih **Simpan**.

1. Di bawah bagian **Skema**, harap pilih **Kolom**.

### Buat kolom Tanggal Pengeluaran

1. Pilih **+ Kolom baru**.

1. Masukkan Tanggal Pengeluaran untuk **Nama tampilan**.

1. Pilih tanggal **hanya** untuk **Jenis data**.

1. Ubah **Diperlukan**, ke **Business diperlukan**.

1. Luaskan **Opsi Tingkat Lanjut**.

1. Di **Penyesuaian zona waktu**, pilih **Hanya Tanggal**.

    >**Catatan:** Kami menggunakan **Tanggal hanya** perilaku untuk merekam informasi tanggal, karena tanggal pengeluaran tidak boleh berubah saat dilihat dari zona waktu yang berbeda.

1. Pilih **Simpan**.

### Buat Kolom Tipe Pengeluaran

1. Pilih **+ Kolom baru**.

1. Masukkan Jenis Pengeluaran untuk **Nama tampilan**.

1. Pilih **Pilihan** untuk **Jenis data**.

1. Di **Diperlukan**, pilih **Opsional**.

1. Atur **sinkronisasi dengan** Pilihan global ke **Ya (disarankan)**

1. Di **Sinkronkan pilihan ini dengan** bidang, pilih **Jenis Pengeluaran**.

1. Atur bidang **pilihan Default** ke **Tidak Ada**.

1. Pilih **Simpan**.

### Buat Kolom Tujuan Pengeluaran

1. Pilih **+ Kolom baru**.

1. Masukkan Tujuan Pengeluaran untuk **Nama tampilan**.

1. Pilih **Pilihan** untuk **Jenis data**.

1. Di **Diperlukan**, pilih **Opsional**.

1. Atur **sinkronisasi dengan** Pilihan global ke **Ya (disarankan)**

1. Di **Sinkronkan pilihan ini dengan**bidang, pilih **Tujuan Pengeluaran**.

1. Atur bidang **Default** ke **Tidak Ada**.

1. Pilih **Simpan**.

### Buat kolom Deskripsi Item

1. Pilih **+ Kolom baru**.

1. Masukkan Deskripsi Item untuk **Nama tampilan**.

1. Pilih **Beberapa Baris teks &gt; Teks Biasa** untuk **Tipe data**.

1. Pilih **Simpan**.

### Buat kolom Jumlah Pengeluaran

1. Pilih **+ Kolom baru**.

1. Masukkan Jumlah Pengeluaran untuk **Nama tampilan**.

1. Pilih **Mata Uang** untuk **Jenis data**.

1. Pilih **Simpan**.

 
## Latihan 2: Masukkan data

**Tujuan:** Dalam latihan ini, Anda memasukkan beberapa data sampel secara manual ke dalam tabel baru Anda. 

### Tugas 1: Mengubah kolom yang ditampilkan

1. Jika belum masuk, masuk ke https://make.powerapps.com

1. Pilih lingkungan **Dev One** di kanan atas jika belum dipilih.

1. Menggunakan navigasi di sebelah kiri, pilih **Tabel**.

1. Buka tabel **Pengeluaran** yang dibuat di latihan sebelumnya.

1. Di samping kolom **Nama**, pilih **+26 lainnya**.

1. Dari menu yang muncul, pilih kolom berikut.

    1. Tanggal Pengeluaran

    2. Tujuan Pengeluaran 

    3. Jenis Pengeluaran

    4. Jumlah Pengeluaran

    5. Deskripsi Item

1. Pilih tombol **Simpan**.

## Tugas #2: Tambahkan rekaman sampel.

1. Pilih **Panah** di samping **Edit**. Dari menu yang muncul, pilih **Edit di tab baru**.

1. Di kolom **Nama**, masukkan **John Doe**.

1. Di kolom **Tanggal Pengeluaran**, masukkan **xxx**.

1. Di **Tujuan Pengeluaran**, pilih **konferensi**.

1. Di kolom **Jenis Pengeluaran**, pilih **Travel**.

1. Di kolom **Jumlah Pengeluaran**, masukkan **750,00**.

1. Di **Deskripsi Item**, masukkan deskripsi singkat.

1. Tekan tombol Tab untuk melanjutkan ke baris berikutnya dan **menyimpan** rekaman.

Selamat, Anda telah berhasil membuat tabel baru dan menambahkan data.


