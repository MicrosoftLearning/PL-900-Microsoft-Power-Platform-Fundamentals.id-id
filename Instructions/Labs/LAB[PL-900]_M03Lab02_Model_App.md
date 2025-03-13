---
lab:
  title: 'Lab 3: Cara membuat aplikasi berbasis model'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Lab 3: Cara membuat aplikasi berbasis model

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberikan penyewa sebagai bagian dari pengiriman pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa tersedia untuk tujuan mendukung lab langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk ekstensi. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa kampus dan program. Banyak instruktur dan administrator Bellow Colleges perlu menghadiri acara, dan membeli item. Secara historis, melacak pengeluaran ini merupakan sebuah tantangan.

Administrasi kampus ingin memodernisasi sistem pelaporan pengeluaran mereka dengan menyediakan cara digital kepada karyawan untuk melaporkan pengeluaran.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan karyawan Bellows College mengelola pengeluaran.

## Langkah-langkah lab tingkat tinggi

Sebagai bagian dari pembuatan aplikasi berbasis model, Anda akan menyelesaikan hal berikut:

- Buat aplikasi berbasis model baru bernama Bellows Expense Management.

- Edit navigasi aplikasi untuk mereferensikan tabel yang diperlukan.

- Kustomisasi formulir dan tampilan tabel yang diperlukan untuk aplikasi.

Kami akan bekerja dengan komponen berikut:

- **Tampilan**: Tampilan memungkinkan pengguna menampilkan data yang ada dalam tabel formulir.

- **Formulir**: Di sinilah pengguna membuat/memperbarui baris baru dalam tabel.

Keduanya akan diintegrasikan ke aplikasi berbasis model untuk pengalaman pengguna yang lebih baik.

### Prasyarat

- Penyelesaian **Modul 1 Lab 0 - Memvalidasi lingkungan lab**

**Hal-hal yang perlu dipertimbangkan sebelum Anda mulai**

- Perubahan apa yang harus kami lakukan untuk meningkatkan pengalaman pengguna?

- Apa yang harus kami sertakan dalam aplikasi berbasis model berdasarkan model data yang telah kami buat?

- Penyesuaian apa yang dapat dilakukan pada peta situs aplikasi berbasis model?

## Latihan 1: Menyesuaikan Tampilan serta Formulir

**Tujuan:** Dalam latihan ini, Anda akan menyesuaikan tampilan dan bentuk tabel yang dibuat khusus yang akan digunakan dalam aplikasi berbasis model.

### Tugas #1: Edit Formulir Laporan Pengeluaran

1. Jika Anda belum melakukannya, masuk ke https://make.powerapps.com

1. **Pilih lingkungan Dev One** di kanan atas jika belum dipilih.

1. Menggunakan navigasi di sebelah kiri, pilih **Tabel**, dan buka tabel **Laporan Pengeluaran**.

    >Jika Anda tidak melihat tabel Laporan pengeluaran, pastikan Anda berada di lingkungan yang benar (Langkah 2).

1. Pada bagian **Pengalaman data**, pilih **Formulir** dan buka formulir **Informasi** dengan tipe Formulir**Utama**. (**Penting:** Pastikan Anda memilih formulir dengan jenis formulir **Utama**.)

    >**PENTING:** Karena secara default semua formulir diberi nama Informasi, pastikan untuk memverifikasi bahwa formulir yang Anda pilih memiliki Jenis Formulir **Utama** dan bukan yang lain. Secara default, formulir memiliki dua bidang: Nama dan Pemilik.

1. Di sisi kanan layar pada panel **Properti**, pilih bidang **Nama Tampilan**, dan ubah menjadi Informasi Laporan

1. Pilih **kolom Tabel** dari panel navigasi kiri dan tambahkan bidang berikut di bawah bidang **Pemilik** dengan menyeret kolom ke formulir atau cukup mengeklik nama kolom:

    - **Keterangan**

    - **Tujuan Laporan**

    - **Tanggal jatuh tempo laporan**

    - **Laporkan Jumlah Total**

1. Seret kolom **Alasan Status** dan letakkan di header formulir.

    >Header adalah area kanan atas formulir. Anda mungkin perlu menciutkan panel Properti di sisi kanan layar untuk melihat bidang pada formulir.

1. Pilih bidang **Pemilik**. Di panel Properti, ubah Label** menjadi Pemohon**.

1. Pilih tombol **Simpan dan terbitkan** di kanan atas dan tunggu hingga penyimpanan dan penerbitan selesai.

1. Jika tampilan Edit dibuka di tab atau jendela browser baru, tutup tampilan tersebut. Jika tidak, pilih **🡠 Kembali** di kiri atas layar. Anda sekarang harus kembali ke **Laporan Pengeluaran** tabel Formulir.

1. Menggunakan breadcrumb di kiri atas (**Tabel** > **Laporan Pengeluaran** > **Formulir**). Pilih **Pengeluaran Laporan** untuk kembali ke layar properti Tabel **Pengeluaran Laporan**.

## Tugas #2: Mengedit tampilan Laporan Pengeluaran Aktif

Dalam tugas ini, kami akan memodifikasi tampilan Laporan Pengeluaran Aktif default dan membuat tampilan baru untuk laporan pengeluaran yang jatuh tempo hari ini.

1. Di bagian **Pengalaman data**, pilih **Tampilan** dan buka tampilan**Laporan Pengeluaran Aktif**Anda.

1. Tambahkan bidang berikut ke tampilan dengan mengklik atau menyeret dan menjatuhkan bidang:

    - **Tujuan Laporan**

    - **Tanggal jatuh tempo laporan**

    - **Laporkan Jumlah Total**

1. Pilih menu drop-down pada kolom **Dibuat Pada** dan pilih **Hapus**. Bidang **Dibuat Pada** sekarang akan dihapus dari tampilan.

1. Ubah ukuran lebar kolom individual agar sesuai dengan data.

1. Di bawah **Urutkan berdasarkan …** pilih X untuk menghapus **Nama** Laporan dan sebagai gantinya, pilih **Laporkan Jumlah** Total.

1. Pilih **Laporkan Jumlah** Total untuk mengubah urutan pengurutan menjadi **Lebih Besar menjadi lebih** kecil.

1. Pilih tombol **Simpan dan terbitkan** di kanan atas dan tunggu hingga penerbitan selesai.

### Tugas #3: Buat tampilan baru untuk Laporan yang jatuh tempo hari ini

Sekarang, kita akan mengkloning tampilan untuk membuat tampilan baru untuk laporan yang jatuh tempo hari ini.

>    **PENTING:** Pastikan Anda tidak menutup tampilan Laporan Pengeluaran Aktif, karena kami akan memanfaatkannya untuk membuat tampilan Laporan jatuh tempo hari ini.

1. Pilih **Simpan Sebagai**.

1. Ubah **Nama** menjadi Laporan Pengeluaran Jatuh Tempo Hari Ini dan pilih **Simpan**.

1. Pilih **Edit filter**, di panel Properti.

1. Pilih **+ Tambahkan**, pilih **Tambahkan baris**.

1. Pilih **Laporkan Tanggal Jatuh Tempo** sebagai bidang, lalu ubah **Sama dengan** menjadi **Hari Ini** sebagai kondisi di menu drop-down.

1. Pilih **…** **Perintah lainnya** pada baris **Status** dan pilih **Hapus** untuk menghapus kondisi filter tersebut.

1. Pilih **Oke** untuk menyimpan kondisi. Tampilan sekarang difilter untuk memperlihatkan hanya rekaman di mana **Laporkan Tanggal Jatuh Tempo** hari ini.

1. Tambahkan bidang **Jumlah Penggantian** ke tampilan.

1. Pilih tombol **Simpan dan terbitkan** di kanan atas dan tunggu hingga penerbitan selesai.

## Latihan 2: Membuat aplikasi berbasis model

**Tujuan:** Dalam latihan ini, Anda akan membuat aplikasi berbasis model, menyesuaikan peta situs, serta menguji aplikasi.

Demi kesederhanaan dan waktu, kami tidak akan membahas semua kolom Laporan Pengeluaran di lab ini.

### Tugas #1: Membuat aplikasi

1. Jika Anda belum melakukannya, masuk ke https://make.powerapps.com

1. Pilih lingkungan **Dev One** di kanan atas, jika belum dipilih.

1. Pilih **+ Buat** di navigasi kiri.

1. Buat aplikasi berbasis model:

    - Pilih **Aplikasi kosong** di bagian **Mulai dari** layar **Buat aplikasi Anda**.

    - Di bagian **Aplikasi kosong berdasarkan Dataverse**, pilih **Buat**.

    - Masukkan `Employee Expense Management` untuk **Nama** dan pilih **Buat**.

1. Setelah aplikasi berbasis model baru Anda dimuat, pilih tombol **+ Tambahkan halaman** .

1. **Pada layar Tambahkan halaman**, pilih **Tabel** dataverse.

1. Pilih tabel berikut:

    - Laporan Pengeluaran

    - Kontak

1. Setelah Anda memiliki kedua tabel, pilih **Tambahkan**.

1. Menggunakan ikon navigasi di sisi kiri layar, pilih **Navigasi**.

1. Pada Panel Navigasi, pilih **Grup Baru** di bawah tempatnya berbuah Navigasi. Anda mungkin perlu memperluas menu di sebelah kiri.

1. Di sisi kanan layar, di bagian Opsi** tampilan**, ubah **properti Judul** menjadi Laporan.

1. Klik **Simpan** dan tunggu hingga perubahan disimpan.

1. Setelah **Simpan** selesai, pilih tombol **Terbitkan** untuk menerbitkan perubahan Anda. Tunggu hingga penerbitan selesai.

## Tugas #2: Uji aplikasi

**Mulai aplikasi**

1. Pilih tombol **Putar**, aplikasi berbasis model akan dimuat di tab baru.

**Buat Kontak baru**

1. Aplikasi akan terbuka pada tampilan **Kontak Aktif Saya**. Jika tidak, pilih **Kontak** di navigasi kiri.

1. Pilih **+Baru** dari bilah perintah.

1. Masukkan **Nama** Depan sebagai `John` dan **Nama** Belakang sebagai `Doe`.

1. Berikan email pribadi Anda sebagai **Email**. Ini akan digunakan di lab mendatang, di mana Anda akan menerima email.

1. Pilih **Simpan &amp; Tutup**.

1. Anda kini akan melihat kontak yang dibuat pada tampilan **Kontak Aktif Saya**.

**Buat laporan pengeluaran baru**

1. Pilih **Laporan Pengeluaran** dari navigasi sebelah kiri (Juga dikenal sebagai peta situs.)

1. Pilih **+ Baru**.

1. Masukkan bidang sebagai berikut:

    - **Nama** Laporan: `New Test Report`

    - **Tujuan Laporan**: pilih **Konferensi**

    - **Tanggal jatuh tempo laporan**: Pilih Tanggal hari ini

1. Pilih **Simpan &amp; Tutup**. Ini akan membuat Laporan Pengujian baru dan Anda akan dapat melihatnya di tampilan **Laporan Pengeluaran Aktif**.

1. Ubah tampilan ke **Laporan Pengeluaran Jatuh Tempo Hari Ini** dengan menggunakan menu drop-down di samping **Laporan Pengeluaran Aktif**. 

1. Anda dapat menambahkan beberapa catatan pengujian lainnya.

Aplikasi berbasis model anda yang sedang berjalan akan terlihat seperti berikut ini:

![Cuplikan layar aplikasi berbasis model baru saja dibuat.](media/lab-3-create-a-model-app-01.png)

Selamat! Anda telah membuat dan mengonfigurasi aplikasi berbasis model pertama Anda.
