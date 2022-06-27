---
lab:
  title: 'Lab 1: Pemodelan Data'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: 9edefbdf214d5a0f2e0693ffdf024dfc05c032c5
ms.sourcegitcommit: dbffa13e13419f5b9aadc894eb95fd16215b2ebf
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 06/17/2022
ms.locfileid: "146458362"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>Modul 2: Pengenalan Microsoft Dataverse

# <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Kunjungan kampus saat ini dicatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab ini Anda akan mengakses lingkungan Anda, membuat database Microsoft Dataverse, dan membuat solusi untuk melacak perubahan Anda. Anda juga akan membuat model data untuk mendukung persyaratan berikut:

-   R1 – Melacak informasi untuk kunjungan kampus terjadwal

-   R2 – Mencatat informasi dasar untuk mengidentifikasi dan melacak pengunjung

-   R3 – Menjadwalkan, mencatat, dan mengelola kunjungan

Terakhir, Anda akan mengimpor data sampel ke Microsoft Dataverse.

# <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Untuk mempersiapkan lingkungan belajar Anda, Anda akan:

* membuat solusi dan penerbit
* menambahkan komponen baru dan yang sudah ada yang diperlukan untuk memenuhi persyaratan aplikasi. Lihat [dokumen model data](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) untuk deskripsi metadata (tabel dan hubungan). Anda dapat menahan CTRL+klik atau klik kanan tautan untuk membuka dokumen model data di jendela baru.
* Buat tabel Kunjungan
* impor data Kunjungan menggunakan spreadsheet Excel

## <a name="prerequisites"></a>Prasyarat:

-   Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai:

-   Konvensi penamaan - ketik nama dengan teliti.

# <a name="exercise-1-create-new-table"></a>Latihan \#1: Buat Tabel Baru

**Tujuan:** Dalam latihan ini, Anda akan membuat tabel kustom baru untuk Kunjungan. 

## <a name="task--1-create-visit-table-and-columns"></a>Tugas \# 1: Membuat Tabel dan Kolom Kunjungan

Tabel **Kunjungan** akan berisi informasi tentang kunjungan kampus, seperti pengunjung, waktu terjadwal, dan waktu sebenarnya dari setiap kunjungan.

Kami ingin memberikan setiap kunjungan nomor unik yang dapat dengan mudah dimasukkan dan ditafsirkan oleh pengunjung ketika ditanya selama proses check-in kunjungan.

>   Kami menggunakan perilaku **tidak bergantung pada zona waktu** untuk mencatat informasi tanggal dan waktu, karena waktu kunjungan ke lokasi gedung selalu dalam waktu lokal dan tidak boleh berubah jika dilihat dari zona waktu yang berbeda.

1. Masuk ke [https://make.powerapps.com](https://make.powerapps.com/) (jika Anda belum masuk)

2. Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

3. Di menu navigasi sebelah kiri, perluas Dataverse, dan pilih Tabel.

4. Klik **Tabel baru**.

5. Masukkan **Kunjungan** untuk **Nama Tampilan**.

6. Klik **Simpan**. Tindakan ini akan mulai menyediakan tabel di latar belakang sementara Anda dapat mulai menambahkan kolom lain.

7. Setelah tabel dibuat, pada bagian **Skema**, pilih **Kolom.** 

8. Pilih **Kolom baru** dan konfigurasikan sebagai berikut: 

    - Masukkan **Jadwal Mulai** untuk **Nama tampilan**.

    - Pilih **Tanggal dan Waktu** untuk **Jenis data**.

    - Di **Diperlukan**, pilih **Bisnis diperlukan**.

    - Luaskan bagian **Opsi tingkat lanjut**.

    - Di **Perilaku**, pilih **Zona waktu independen**.

    - Klik **Simpan**.

9. Membuat kolom Waktu Selesai yang Dijadwalkan 

    - Klik **Tambahkan kolom**.

    - Masukkan **Jadwal Selesai** untuk **Nama tampilan**.

    - Pilih **Tanggal dan Waktu** untuk **Jenis data**.

    - Di **Diperlukan**, pilih **Bisnis diperlukan**.

    - Luaskan bagian **Opsi tingkat lanjut**.

    - Di **Perilaku**, pilih **Zona waktu independen**.

    - Klik **Simpan**.

10. Membuat kolom Waktu Mulai Aktual

    - Klik **Tambahkan kolom**.

    - Masukkan **Waktu Mulai Sebenarnya** untuk **Nama tampilan**.

    - Pilih **Tanggal dan Waktu** untuk **Jenis data**.

    - Di **Diperlukan**, biarkan bagian ini sebagai **Opsional.**

    - Luaskan bagian **Opsi tingkat lanjut**.

    - Di **Perilaku**, pilih **Zona waktu independen**.

    - Klik **Simpan**.

11. Buat kolom Akhir Aktual

    - Klik **Tambahkan kolom**.

    - Masukkan **Waktu Selesai Sebenarnya** untuk **Nama tampilan**.

    - Pilih **Tanggal dan Waktu** untuk **Jenis data**.

    - Di **Diperlukan**, biarkan ini sebagai **Opsional**.

    - Luaskan bagian **Opsi tingkat lanjut**.

    - Di **Perilaku**, pilih **Zona waktu independen**.

    - Klik **Simpan**.

12. Buat kolom Kode

    - Klik **Tambahkan kolom**.

    - Masukkan **Kode** untuk **Nama tampilan**.

    - Pilih **Nomor Otomatis** untuk **Jenis data**.

    - Pilih **Nomor awalan tanggal** untuk **Jenis nomor otomatis**.

    - Klik **Simpan**.

13. Buat kolom pencarian Pengunjung

    - Klik **Tambahkan kolom**.

    - Masukkan **Pengunjung** untuk **Nama tampilan**.

    - Pilih **Pencarian** untuk **Jenis data**.

    - Pilih **Kontak** untuk **Tabel Terkait.**

    - Luaskan bagian **Opsi tingkat lanjut**.

    - Masukkan **visitor_id** untuk **Nama hubungan**.

    - Klik **Simpan**.

 

Latihan #2: Mengimpor Data

**Tujuan:** Dalam latihan ini Anda akan mengimpor data sampel ke dalam database Dataverse.

Tugas 1: Impor file Visits.xls.

Dalam tugas ini Anda akan mengimpor data Kunjungan dari file Excel.

1. Anda harus menyimpan file **Visits.xls** di Desktop. Unduh [Visits.xls](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/Visits.xlsx) jika belum.

2. Jika belum masuk, masuk ke [https://make.powerapps.com](https://make.powerapps.com/).

3. Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

4. Di menu navigasi sebelah kiri, luaskan **Dataverse**, dan pilih tabel.

Anda mungkin melihat ini sebagai Data > Tabel di layar Anda.

5. Cari dan buka tabel **Kunjungan**, yang Anda buat di latihan sebelumnya.

6. Dengan menggunakan menu di bagian atas, pilih panah drop-down di samping **Impor**, pilih **Impor data dari Excel**.

7. Dari menu yang muncul, pilih tombol **Unggah**.

8. Cari dan pilih file **Visits.xls** yang Anda unduh sebelumnya. (Perlu diketahui bahwa perlu satu atau dua menit untuk mengunggah file. Jangan khawatir jika Anda mendapatkan pesan bahwa ada kesalahan pemetaan, kita akan memperbaiki kesalahan tersebut selanjutnya.)

9. Pilih **Kolom peta.**

10. Petakan Kolom seperti yang tercantum di bawah ini:

| Kunjungi kolom Db| Nilai Sumber |
| - |
| Akhir Aktual| Waktu selesai sebenarnya |
| Mulai Aktual| Waktu mulai sebenarnya |
| Kode| Kode |
| Nama| Nama |
| Waktu Selesai yang Dijadwalkan| Jadwal Selesai |
| Waktu Mulai yang Dijadwalkan| Jadwal mulai |


11. Biarkan semua bidang lainnya diatur ke **Tidak Diatur**.

12. Di pojok kanan atas layar, pilih **Simpan perubahan**.

13. Pada layar **Impor data**, verifikasi bahwa status pemetaan menyatakan “Pemetaan berhasil”.

14. Pilih **Impor** di sudut kanan atas untuk menyelesaikan impor data.

**Catatan:** Diperlukan beberapa menit agar data Anda diimpor ke tabel Anda. Jangan khawatir jika Anda mendapatkan beberapa kesalahan, kesalahan tersebut normal, dan tidak akan memengaruhi kursus lainnya.

Tugas #2: Memverifikasi Impor Data

1. Setelah data Anda diimpor, gunakan menu navigasi di sebelah kiri layar untuk memilih tabel **Kunjungan** lagi.

2. Pastikan Anda melihat data yang diimpor pada bagian **Kolom dan data kunjungan**. 

Selamat, Anda telah berhasil membuat sebuah tabel baru dan mengimpor data.
