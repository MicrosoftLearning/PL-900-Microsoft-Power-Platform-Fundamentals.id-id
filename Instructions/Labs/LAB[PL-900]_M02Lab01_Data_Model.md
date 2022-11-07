---
lab:
  title: 'Lab 1: Pemodelan Data'
  module: 'Module 2: Introduction to Microsoft Dataverse'
---

# <a name="lab-1-data-modeling"></a>Lab 1: Pemodelan Data

## <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Kunjungan kampus saat ini dicatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab ini Anda akan mengakses lingkungan Anda, membuat database Microsoft Dataverse, dan membuat solusi untuk melacak perubahan Anda. Anda juga akan membuat model data untuk mendukung persyaratan berikut:

- R1 – Melacak informasi untuk kunjungan kampus terjadwal

- R2 – Mencatat informasi dasar untuk mengidentifikasi dan melacak pengunjung

- R3 – Menjadwalkan, mencatat, dan mengelola kunjungan

Terakhir, Anda akan mengimpor data sampel ke Microsoft Dataverse.

## <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Untuk mempersiapkan lingkungan belajar Anda, Anda akan:

- Lihat [dokumen model data](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) untuk deskripsi metadata (tabel dan hubungan). Anda dapat menahan CTRL+klik atau klik kanan tautan untuk membuka dokumen model data di jendela baru.
- Buat tabel Kunjungan
- impor data Kunjungan menggunakan spreadsheet Excel

## <a name="prerequisites"></a>Prasyarat

- Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai

- Konvensi penamaan - ketik nama dengan teliti.

## <a name="exercise-1-create-new-table"></a>Latihan 1: Buat Tabel Baru

**Tujuan:** Dalam latihan ini, Anda akan membuat tabel kustom baru untuk Kunjungan.

### <a name="task-1-create-visit-table-and-columns"></a>Tugas \#1: Membuat Tabel dan Kolom Kunjungan

Tabel **Kunjungan** akan berisi informasi tentang kunjungan kampus, seperti pengunjung, waktu terjadwal, dan waktu sebenarnya dari setiap kunjungan.

Kami ingin memberikan setiap kunjungan nomor unik yang dapat dengan mudah dimasukkan dan ditafsirkan oleh pengunjung ketika ditanya selama proses check-in kunjungan.

> Kami menggunakan perilaku **Tidak bergantung pada zona waktu** untuk mencatat informasi tanggal dan waktu, karena waktu kunjungan ke lokasi gedung selalu dicatat dalam waktu lokal dan tidak boleh berubah jika dilihat dari zona waktu yang berbeda.

1. Masuk ke [https://make.powerapps.com](https://make.powerapps.com/) (jika Anda belum masuk)

1. Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

1. Di menu navigasi sebelah kiri, perluas **Dataverse**, dan pilih **Tabel**.

1. Klik **+Tabel baru**.

1. Masukkan **Kunjungan** untuk **Nama Tampilan**.

1. Klik **Simpan**.

1. Di bawah bagian **Skema**, harap pilih **Kolom**.

1. Membuat kolom Jadwal Mulai

    - Pilih **+ Kolom baru**.

    - Masukkan **Jadwal Mulai** untuk **Nama tampilan**.

    - Pilih **Tanggal dan Waktu** untuk **Jenis data**.

    - Di **Diperlukan**, pilih **Bisnis diperlukan**.

    - Luaskan **Opsi Tingkat Lanjut**.

    - Di **Penyesuaian zona waktu**, pilih **Tidak tergantung zona waktu**.

    - Klik **Simpan**.

1. Membuat kolom Waktu Selesai yang Dijadwalkan

    - Klik **+ Kolom baru**.

    - Masukkan **Jadwal Selesai** untuk **Nama tampilan**.

    - Pilih **Tanggal dan Waktu** untuk **Jenis data**.

    - Di **Diperlukan**, pilih **Bisnis diperlukan**.

    - Luaskan **Opsi Tingkat Lanjut**.

    - Di **Penyesuaian zona waktu**, pilih **Tidak tergantung zona waktu**.

    - Klik **Simpan**.

1. Membuat kolom Waktu Mulai Aktual

    - Klik **+ Kolom baru**.

    - Masukkan **Waktu Mulai Sebenarnya** untuk **Nama tampilan**.

    - Pilih **Tanggal dan Waktu** untuk **Jenis data**.

    - Di **Diperlukan**, biarkan bagian ini sebagai **Opsional.**

    - Luaskan **Opsi Tingkat Lanjut**.

    - Di **Penyesuaian zona waktu**, pilih **Tidak tergantung zona waktu**.

    - Klik **Simpan**.

1. Buat kolom Akhir Aktual

    - Klik **+ Kolom baru**.

    - Masukkan **Waktu Selesai Sebenarnya** untuk **Nama tampilan**.

    - Pilih **Tanggal dan Waktu** untuk **Jenis data**.

    - Di **Diperlukan**, biarkan ini sebagai **Opsional**.

    - Luaskan **Opsi Tingkat Lanjut**.

    - Di **Penyesuaian zona waktu**, pilih **Tidak tergantung zona waktu**.

    - Klik **Simpan**.

1. Buat kolom Kode

    - Klik **+ Kolom baru**.

    - Masukkan **Kode** untuk **Nama tampilan**.

    - Pilih **Nomor Otomatis** untuk **Jenis data**.

    - Pilih **Nomor awalan tanggal** untuk **Jenis nomor otomatis**.

    - Klik **Simpan**.

1. Buat kolom pencarian Pengunjung

    - Klik **+ Kolom baru**.

    - Masukkan **Pengunjung** untuk **Nama tampilan**.

    - Pilih **Pencarian** untuk **Jenis data**.

    - Pilih **Kontak** untuk **Tabel Terkait**.

    - Luaskan **Opsi Tingkat Lanjut**.

    - Masukkan **visitor_id** untuk **Nama hubungan**.

    - Klik **Simpan**.

## <a name="exercise-2-import-data"></a>Latihan 2: Mengimpor Data

**Tujuan:** Dalam latihan ini Anda akan mengimpor data sampel ke dalam database Dataverse.

### <a name="task-11-load-excel-file-to-onedrive"></a>Tugas \#1.1: Memuat file Excel ke OneDrive

1. Anda harus menyimpan file **Visits.xlsx** di komputer virtual Anda di **C:/LabFiles**. Unduh [Visits.xlsx](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) jika belum.

2. Jika belum masuk, masuk ke [https://make.powerapps.com](https://make.powerapps.com/).

3. Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

4. Klik tombol Waffle di sudut kiri atas untuk mengubah aplikasi dan pilih **OneDrive**. (Mungkin perlu beberapa saat hingga OneDrive Anda siap. Klik OneDrive Anda siap saat melihatnya di layar.)

5. Klik **Unggah** dari menu bagian atas dan pilih **File**.

6. Cari dan pilih file **Visits.xlsx**, kemudian klik **Buka**.

 **Catatan:** File ini terletak di folder **Semua File** pada komputer Anda.
 
### <a name="task-12-create-a-dataflow"></a>Tugas \#1.2: Membuat aliran data

1. Jika belum masuk, masuk ke [https://make.powerapps.com](https://make.powerapps.com/).

2. Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

3. Di menu navigasi sebelah kiri, perluas **Dataverse**, dan pilih **Tabel**.

4. Cari dan buka tabel **Kunjungan**, yang Anda buat di latihan sebelumnya.

5. Di menu di bagian atas, pilih panah dropdown di samping **Impor**, kemudian pilih **Impor data**.

6. Dalam dialog **Pilih sumber data**, pilih **buku kerja Excel**.

7. Pilih opsi **Tautkan ke File**. Klik **Telusuri OneDrive**. Jika diminta, masuk dengan kredensial Microsoft 365 Anda.

8. Pilih file **Visits.xlsx** yang telah diunggah di OneDrive dan klik **Pilih**.

9. Klik **Berikutnya**.

10. Pada bagian **Pilih Data** centang kotak di samping buku kerja Excel **Kunjungan**.

11. Klik **Berikutnya**. Jangan keluar dari jendela browser ini.

12. Klik **Berikutnya**.

13. Pada bagian **Tabel peta**, pilih **Muat ke tabel yang sudah ada** di bagian **pengaturan Pemuatan**.

14. Pada menu dropdown **Tabel tujuan**, Pilih nama tabel berawalan **crXXX_visit** (dengan XXX adalah sekumpulan huruf dan angka acak)

15. Pada **Pemetaan Kolom**. Petakan Kolom ke kolom tujuan terkait.

| Kolom tujuan| Nilai sumber |
| - | - |
| crxxx_ActualEnd| waktu selesai sebenarnya |
| crxxx_ActualStart| waktu mulai sebenarnya |
| crxxx_Code| kode |
| crxxx_Name| nama |
| crxxx_ScheduledEnd| jadwal selesai |
| crxxx_ScheduledStart| jadwal mulai |

16. Klik **Berikutnya**.

17. Pilih **Refresh secara manual**.

18. Klik **Terbitkan**.

**Catatan:** Diperlukan beberapa menit agar data Anda diimpor ke tabel Anda. Jangan khawatir jika Anda mendapatkan beberapa kesalahan, kesalahan tersebut normal, dan tidak akan memengaruhi kursus lainnya.

### <a name="task-3-verify-data-import"></a>Tugas \#3: Memverifikasi Impor Data

1. Setelah data Anda diimpor, gunakan menu navigasi di sebelah kiri layar untuk memilih tabel **Kunjungan** lagi.

2. Pastikan Anda melihat data yang diimpor pada bagian **Kolom dan data kunjungan**.

Selamat, Anda telah berhasil membuat sebuah tabel baru dan mengimpor data.
