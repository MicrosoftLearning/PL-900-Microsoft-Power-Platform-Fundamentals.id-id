---
lab:
  title: 'Lab 1: Pemodelan Data'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# Lab 1: Pemodelan Data

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberikan penyewa sebagai bagian dari pengiriman pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa tersedia untuk tujuan mendukung lab langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab langsung. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk ekstensi. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak untuk mendapatkan akses dan repositori kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Kunjungan kampus saat ini dicatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab ini Anda akan membuat model data untuk mendukung persyaratan berikut:

- R1 – Lacak informasi untuk kunjungan kampus terjadwal.

- R2 – Rekam informasi dasar untuk mengidentifikasi dan melacak pengunjung.

- R3 – Menjadwalkan, merekam, dan mengelola kunjungan.

Terakhir, Anda akan mengimpor data sampel ke Microsoft Dataverse.

Langkah-langkah lab tingkat tinggi

Untuk mempersiapkan lingkungan belajar Anda, Anda akan:

- Lihat [dokumen model data](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) untuk deskripsi metadata (tabel dan hubungan). Anda bisa menahan ctrl + klik kiri atau klik kanan tautan untuk membuka dokumen model data di jendela baru.
- Buat tabel Kunjungan
- Mengimpor data Kunjungan menggunakan lembar bentang Excel


## Prasyarat

- Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**

Hal-hal yang perlu dipertimbangkan sebelum memulai

- Konvensi penamaan - ketik nama dengan teliti.

Latihan 1: Buat Tabel Baru

**Tujuan:** Dalam latihan ini, Anda akan membuat tabel kustom baru untuk Kunjungan.

Tugas #1: Buat Kunjungi Tabel dan Kolom

Tabel **Kunjungan** akan berisi informasi tentang kunjungan kampus, seperti pengunjung, waktu terjadwal, dan waktu sebenarnya dari setiap kunjungan.

Kami ingin memberikan setiap kunjungan nomor unik yang dapat dengan mudah dimasukkan dan ditafsirkan oleh pengunjung ketika ditanya selama proses check-in kunjungan.

1.  Jika Anda belum masuk, masuk <https://make.powerapps.com> 

1.  Dari menu **Lingkungan** di kanan atas, pastikan lingkungan **Praktik** Anda dipilih. 

1.  Menggunakan navigasi di sebelah kiri, pilih **Tabel**.

1.  Pilih **+ Tabel baru** dan pilih **+ Tabel baru**. 

1.  Untuk **Nama tampilan**, masukkan `Visit`

1.  Pilih **Simpan**. 

1.  Di bawah bagian **Skema**, harap pilih **Kolom**. 

# Membuat kolom Mulai Terjadwal

1.  Pilih **+ Kolom baru**. 

1.  Masukkan `Scheduled Start` untuk **Nama tampilan**. 

1.  Pilih **Tanggal dan waktu** untuk **Jenis data**. 

1.  Perubahan **Diperlukan**, ke **Bisnis diperlukan**. 

1.  Luaskan **Opsi Tingkat Lanjut**. 

1.  Di **Penyesuaian zona waktu**, pilih **Tidak tergantung zona waktu**. 

    > **Catatan:** Kami menggunakan perilaku **independen Zona waktu** untuk merekam informasi tanggal dan waktu, karena waktu kunjungan selalu lokal ke lokasi bangunan dan tidak boleh berubah ketika dilihat dari zona waktu yang berbeda. 

1.  Pilih **Simpan**. 

# Membuat kolom Waktu Selesai yang Dijadwalkan

1.  Pilih **+ Kolom baru**. 

1.  Masukkan `Scheduled End` untuk **Nama tampilan**.

1.  Pilih **Tanggal dan waktu** untuk **Jenis data**.

1.  Di **Diperlukan**, pilih **Bisnis diperlukan**.

1.  Luaskan **Opsi Tingkat Lanjut**.

1.  Di **Penyesuaian zona waktu**, pilih **Tidak tergantung zona waktu**.

1.  Pilih **Simpan**. 

# Membuat kolom Waktu Mulai Aktual

1.  Pilih **+ Kolom baru**. 

1.  Masukkan `Actual Start` untuk **Nama tampilan**.

1.  Pilih **Tanggal dan Waktu** untuk **Jenis data**.

1.  Di **Diperlukan**, biarkan ini sebagai **Opsional**.

1.  Luaskan **Opsi Tingkat Lanjut**.

1.  Di **Penyesuaian zona waktu**, pilih **Tidak tergantung zona waktu**. 

1.  Pilih **Simpan**. 

# Buat kolom Akhir Aktual

1.  Pilih **+ Kolom baru**.

1.  Masukkan **Waktu Selesai Sebenarnya** untuk **Nama tampilan**.

1.  Pilih **Tanggal dan Waktu** untuk **Jenis data**.

1.  Di **Diperlukan**, biarkan ini sebagai **Opsional**.

1.  Luaskan **Opsi Tingkat Lanjut**.

1.  Di **Penyesuaian zona waktu**, pilih **Tidak tergantung zona waktu**.

1.  Pilih **Simpan**.

# Buat kolom Kode

1.  Pilih **+ Kolom baru**.

1.  Masukkan `Code` untuk **Nama tampilan**.

1.  Pilih **Nomor Otomatis** untuk **Jenis data**.

1.  Pilih **Nomor awalan tanggal** untuk **Jenis nomor otomatis**.

1.  Pilih **Simpan**. 

# Buat kolom pencarian Pengunjung

1.  Pilih **+ Kolom baru**.

1.  Masukkan `Visitor` untuk **Nama tampilan**.

1.  Pilih **Pencarian** untuk **Jenis data**. 

1.  Pilih **Kontak** untuk **Tabel Terkait**. 

1.  Luaskan **Opsi Tingkat Lanjut**. 

1.  Masukkan `visitor_id` untuk **Nama hubungan**. 

1.  Pilih **Simpan**.


Latihan 2: Mengimpor Data

**Tujuan:** Dalam latihan ini Anda akan mengimpor data sampel ke dalam database Dataverse.

### Tugas \#1: Muat file Excel ke OneDrive

1.  Anda harus menyimpan file **Visits.xlsx** di komputer virtual Anda di **C:/LabFiles**. Unduh [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) jika belum.

2.  Jika belum masuk, masuk ke [https://make.powerapps.com](https://make.powerapps.com/). 

3.  Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

4.  Pilih tombol Wafel di sudut kiri atas untuk mengubah aplikasi dan pilih **OneDrive**. (Mungkin perlu beberapa saat hingga OneDrive Anda siap. Pilih **OneDrive Anda siap** saat Anda melihatnya di layar.)

5.  Pilih **Unggah** dari menu atas dan pilih **File**.

6.  Temukan dan pilih file **Visits.xlsx** dan pilih **Buka**.

    > **Catatan:** File ini terletak di folder **Semua File** pada komputer Anda.


### Tugas \#2: Membuat aliran data

1.  Jika Anda belum masuk, masuk <https://make.powerapps.com> 

2.  Dari menu **Lingkungan** di kanan atas, pastikan lingkungan **Praktik** Anda dipilih. 

3.  Menggunakan navigasi di sebelah kiri, pilih **Tabel**. 

4.  Buka tabel **Kunjungi** yang dibuat di latihan sebelumnya. 

5.  Menggunakan menu di bagian atas, pilih**Impor data Impor****** > .

6.  Dalam dialog **Pilih sumber data**, pilih **buku kerja Excel**.

7.  Pilih opsi **Tautkan ke File**. Pilih **Telusuri OneDrive**. Jika diminta, masuk dengan kredensial Microsoft 365 Anda. Konfigurasikan browser untuk selalu mengizinkan pop-up. 

8.  Pilih file **Visits.xlsx** yang diunggah ke OneDrive di tugas sebelumnya. 

9.  Pilih **Selanjutnya**. 

10. Pada layar**Pilih data** **Power query** > , periksa buku kerja **Excel Kunjungan**. 

11. Pilih **Selanjutnya**. Jangan keluar dari jendela browser ini.

12. Pilih **Selanjutnya**. 

13. Pada bagian **Tabel peta** , di bawah **Muat pengaturan**, pilih **Muat ke tabel yang sudah ada**. 

14. Pada menu drop-down **Tabel tujuan** , pilih tabel **crXXX_Visit** (Di mana XXX adalah sekumpulan huruf dan angka acak)

15. Pada bagian **Pemetaan Kolom** , petakan Kolom ke kolom tujuan terkait:

    | Kolom tujuan  | Nilai sumber   |
    |:---------------------|:----------------|
    | crxxx_ActualEnd      | waktu selesai sebenarnya      |
    | crxxx_ActualStart    | waktu mulai sebenarnya    |
    | crxxx_Code           | kode            |
    | crxxx_Name           | nama            |
    | crxxx_ScheduledEnd   | jadwal selesai   |
    | crxxx_ScheduledStart | jadwal mulai |

16. Pilih **Selanjutnya**. 

17. Pilih **Refresh secara manual**. 

18. Pilih **Terbitkan**. 

    > **Catatan:** Diperlukan beberapa menit agar data Anda diimpor ke tabel Anda. Jangan khawatir jika Anda mendapatkan beberapa kesalahan, kesalahan tersebut normal, dan tidak akan memengaruhi kursus lainnya.


Tugas #3: Memverifikasi Impor Data

1.  Setelah data Anda diimpor, gunakan navigasi di sebelah kiri layar untuk memilih **Tabel** dan buka tabel **Kunjungi** .

2.  Pastikan Anda melihat data yang diimpor pada bagian **Kolom dan data kunjungan**.

Selamat, Anda telah berhasil membuat sebuah tabel baru dan mengimpor data.

