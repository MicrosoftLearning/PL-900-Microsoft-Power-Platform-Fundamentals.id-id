---
lab:
  title: 'Lab 1: Pemodelan Data'
  module: 'Module 2: Introduction to Microsoft Dataverse'
ms.openlocfilehash: 05d0f0656ae0d93f5666f7c14602c3976a9a9ac9
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898890"
---
# <a name="module-2-introduction-to-microsoft-dataverse"></a>Modul 2: Pengenalan Microsoft Dataverse

# <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Kunjungan kampus saat ini dicatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus. 

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus. 

Di lab ini Anda akan mengakses lingkungan Anda, membuat database Microsoft Dataverse, dan membuat solusi untuk melacak perubahan Anda. Anda juga akan membuat model data untuk mendukung persyaratan berikut:

-   R1 – Melacak lokasi (gedung) kunjungan kampus
-   R2 – Mencatat informasi dasar untuk mengidentifikasi dan melacak pengunjung 
-   R3 – Menjadwalkan, mencatat, dan mengelola kunjungan 

Terakhir, Anda akan mengimpor data sampel ke Microsoft Dataverse.

# <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Untuk mempersiapkan lingkungan belajar Anda, Anda akan:

* membuat solusi dan penerbit
* menambahkan komponen baru dan yang sudah ada yang diperlukan untuk memenuhi persyaratan aplikasi. Lihat [dokumen model data](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/Campus%20Management.png) untuk deskripsi metadata (tabel dan hubungan). Anda dapat menahan CTRL+klik atau klik kanan tautan untuk membuka dokumen model data di jendela baru.

Solusi Anda akan berisi beberapa tabel setelah menyelesaikan semua penyesuaian:

-   Kontak
-   Gedung
-   Kunjungan

## <a name="prerequisites"></a>Prasyarat:

* Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai:

* Konvensi penamaan

* Tipe data, batasan (mis. panjang maksimum nama)

* Pemformatan tanggalwaktu untuk mendukung pelokalan yang mudah

# <a name="exercise-1-create-solution"></a>Latihan \#1: Membuat Solusi

## <a name="task-1-create-solution-and-publisher"></a>Tugas \#1: Membuat Solusi dan Penerbit

1.  Membuat Solusi

    -   Navigasikan ke <https://make.powerapps.com>. Anda mungkin perlu mengautentikasi ulang - klik **Masuk** dan ikuti petunjuk jika diperlukan.

    -   Pilih lingkungan Anda dengan mengklik **Lingkungan** di sudut kanan atas layar dan pilih lingkungan Anda dari menu dropdown.

    -   Pilih **Solusi** dari menu sebelah kiri dan klik **Solusi Baru**.

    -   Masukkan **[Nama Belakang Anda] Manajemen Kampus** untuk **Nama Tampilan**.

2.  Membuat Penerbit

    -   Di bagian **Penerbit**, pilih **+ Penerbit**

    -   Di jendela yang muncul, masukkan **Bellows College** untuk **Nama Tampilan**. 

    -   Masukkan **BellowsCollege** untuk **Nama**.
    
    -   Masukkan **bc** untuk **Awalan**

    -   Klik **Simpan**
    
    -   Klik **Selesai** di jendela sembul.

3.  Selesaikan pembuatan solusi.

    -   Sekarang, klik dropdown **Penerbit** dan pilih penerbit **Bellows College** yang baru saja Anda buat.

    -   Validasi bahwa **Versi** diatur ke **1.0.0.0** 
    
    -   Klik **Buat**.

# <a name="exercise-2-add-existing-and-create-new-tables"></a>Latihan \#2: Tambahkan yang Ada dan Buat Tabel Baru

**Tujuan:** Dalam latihan ini, Anda akan menambahkan tabel Kontak standar dan membuat tabel kustom baru untuk Gedung dan Kunjungan dalam solusi. 

## <a name="task-1-add-existing-table"></a>Tugas \#1: Tambahkan Tabel yang Ada

1.  Klik untuk membuka solusi **Manajemen Kampus** yang baru saja Anda buat.

2.  Klik **Tambahkan yang Ada** dan pilih **Tabel**.

3.  Temukan **Kontak** dan pilih.

4.  Klik **Berikutnya**.

5.  Klik **Pilih Komponen** di bawah Kontak.

6.  Pilih tab **Tampilan** dan pilih tampilan **Kontak Aktif**. Klik **Tambahkan**.
    
7.  Klik **Pilih Komponen** lagi.

8.  Pilih tab **Formulir** dan pilih formulir **Kontak**.
    
9.  Klik **Tambahkan**.

    > Anda harus memilih **1 Tampilan** dan **1 Formulir**. 
    
10.  Klik **Tambahkan** lagi. Ini akan menambahkan tabel Kontak dengan Tampilan dan Formulir yang dipilih ke solusi yang baru dibuat.

> Solusi Anda sekarang akan memiliki satu tabel: Kontak.
    
## <a name="task-2-create-building-table"></a>Tugas #2: Membuat Tabel Gedung

1.  Anda harus tetap membuka browser untuk solusi Manajemen Kampus Anda. Jika tidak, buka solusi Manajemen Kampus dengan mengikuti langkah-langkah berikut:

    * Masuk ke <https://make.powerapps.com> (jika Anda belum masuk)
    
    * Pilih **Solusi** dan klik untuk membuka solusi **[Nama Belakang Anda] Manajemen Kampus** yang baru saja Anda buat.
          
2.  Membuat tabel Gedung

    -   Klik **Baru** dan pilih **Tabel**.
    
    -   Masukkan **Gedung** untuk **Nama Tampilan** 
    
    -   Klik **Simpan**. Tindakan ini akan mulai menyediakan tabel di latar belakang sementara Anda dapat mulai menambahkan tabel dan kolom lainnya.

## <a name="task-3-create-visit-table-and-columns"></a>Tugas #3: Membuat Tabel dan Kolom Kunjungan

Tabel **Kunjungan** akan berisi informasi tentang kunjungan kampus termasuk gedung, pengunjung, waktu terjadwal dan waktu sebenarnya dari setiap kunjungan. 

Kami ingin memberikan setiap kunjungan nomor unik yang dapat dengan mudah dimasukkan dan ditafsirkan oleh pengunjung ketika ditanya selama proses check-in kunjungan.

> Kami menggunakan perilaku **Zona waktu independen** untuk mencatat informasi tanggal dan waktu, karena waktu kunjungan selalu lokal ke lokasi gedung dan tidak boleh berubah jika dilihat dari zona waktu yang berbeda. 

1.  Anda harus tetap membuka browser untuk solusi Manajemen Kampus Anda. Jika tidak, buka solusi Manajemen Kampus dengan mengikuti langkah-langkah berikut:

    * Masuk ke <https://make.powerapps.com> (jika Anda belum masuk)
    
    * Pilih **Solusi** dan klik untuk membuka solusi **[Nama Belakang Anda] Manajemen Kampus** yang baru saja Anda buat.

2. Buat tabel Kunjungan

   * Klik **Baru** dan pilih **Tabel**.
   
   * Masukkan **Kunjungi** untuk **Nama Tampilan** 
   
   * Klik **Simpan**. Tindakan ini akan mulai menyediakan tabel di latar belakang sementara Anda dapat mulai menambahkan kolom lain.

3. Membuat kolom Mulai Terjadwal

   * Pilih tabel **Kunjungi**

   * Pastikan Anda telah memilih tab **Kolom** dan klik **Tambahkan kolom**.
   
   * Masukkan **Mulai Terjadwal** untuk **Nama Tampilan**.
   
   * Pilih **Tanggal dan Waktu** untuk **Jenis Data**.
   
   * Di **Diperlukan**, pilih **Diperlukan**.
   
   * Luaskan bagian **Opsi tingkat lanjut**.
   
   * Di **Perilaku**, pilih **Zona waktu independen**.
   
   * Klik **Selesai**.

4.  Membuat kolom Waktu Selesai yang Dijadwalkan

    * Klik **Tambahkan kolom**.
    
    * Masukkan **Waktu Selesai yang Dijadwalkan** untuk **Nama Tampilan**.
    
    * Pilih **Tanggal dan Waktu** untuk **Jenis Data**.
    
    * Di **Diperlukan**, pilih **Diperlukan**.
    
    * Luaskan bagian **Opsi tingkat lanjut**.
    
    * Di **Perilaku**, pilih **Zona waktu independen**.
    
    * Klik **Selesai**.
    
5.  Membuat kolom Waktu Mulai Aktual

    * Klik **Tambahkan kolom**.
    
    * Masukkan **Waktu Mulai Aktual** untuk **Nama Tampilan**.
    
    * Pilih **Tanggal dan Waktu** untuk **Jenis Data**.
    
    * Di **Diperlukan**, biarkan ini sebagai **Opsional**.
    
    * Luaskan bagian **Opsi tingkat lanjut**.
    
    * Di **Perilaku**, pilih **Zona waktu independen**.
    
    * Klik **Selesai**.
    
6.  Buat kolom Akhir Aktual

    * Klik **Tambahkan kolom**.
    
    * Masukkan **Waktu Selesai Aktual** untuk **Nama Tampilan**.
    
    * Pilih **Tanggal dan Waktu** untuk **Jenis Data**.
    
    * Di **Diperlukan**, biarkan ini sebagai **Opsional**.
    
    * Luaskan bagian **Opsi tingkat lanjut**.
    
    * Di **Perilaku**, pilih **Zona waktu independen**.
    
    * Klik **Selesai**.
    
7.  Buat kolom Kode

    * Klik **Tambahkan kolom**.
    
    * Masukkan **Kode** untuk **Nama Tampilan**.
    
    * Pilih **Autonumber** untuk **Jenis Data**.
    
    * Pilih **Nomor awalan tanggal** untuk **Jenis nomor otomatis**.
    
    * Klik **Selesai**.
    
8.  Klik **Simpan Tabel**

# <a name="exercise-3-create-relationships"></a>Latihan \#3: Membuat Hubungan

**Tujuan:** Dalam latihan ini, Anda akan menambahkan hubungan antar tabel.

## <a name="task-1-create-relationships"></a>Tugas 1: Membuat Hubungan

1.  Pastikan Anda masih melihat tabel **Kunjungi** solusi **Manajemen Kampus** Anda. Jika tidak, navigasikan ke sana.

2.  Membuat hubungan Kunjungan ke Kontak

    * Pilih tab **Hubungan**.
    
    * Klik **Tambahkan Hubungan** dan pilih **Banyak-ke-satu**
    
    * Pilih **Kontak** untuk **Terkait (Satu)** 
    
    * Masukkan **Pengunjung** untuk **Nama tampilan kolom pencarian** 
    
    * Klik **Selesai**.
    
3.  Membuat Kunjungan untuk Membangun hubungan

    * Klik **Tambahkan Hubungan** dan pilih **Banyak-ke-satu**
    
    * Pilih **Gedung** untuk **Terkait (Satu)** 
    
    * Klik **Selesai**.
    
4.  Klik **Simpan Tabel**.

5.  Pilih **Kembali ke solusi** di kiri atas.

6.  Pilih **Terbitkan semua penyesuaian.**

# <a name="exercise-4-import-data"></a>Latihan \#4: Mengimpor Data

**Tujuan:** Dalam latihan ini Anda akan mengimpor data sampel ke dalam database Dataverse.

## <a name="task-1-import-solution"></a>Tugas 1: Mengimpor solusi

Dalam tugas ini, Anda akan mengimpor solusi yang berisi alur Power Automate yang diperlukan untuk menyelesaikan impor data.

1. Anda harus menyimpan file **DataImport_managed.zip** di Desktop. Unduh [Solusi Impor Data](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Allfiles/DataImport_managed.zip?raw=true) jika tidak.

2. Masuk ke <https://make.powerapps.com>.

3. Pilih lingkungan Latihan **[inisial saya]** Anda di kanan atas, jika belum dipilih.

4. Pilih **Solusi** di panel navigasi kiri.

5. Klik **Impor**, lalu klik **Jelajahi**. Jelajahi dan pilih **DataImport_managed.zip** dari Desktop Anda, lalu tekan **Berikutnya**.

>   Anda akan menerima pesan berikut:
>
>   Ada dependensi yang hilang. Instal solusi berikut sebelum menginstal yang ini...
>
>   Pesan tersebut menunjukkan bahwa model data tidak lengkap, awalan penerbit bukan **bc**, atau nama tabel **Gedung** dan **Kunjungi** berbeda dari nama yang tercantum di langkah-langkah di atas.

6. Tekan **Berikutnya**. Anda akan diminta untuk membangun kembali koneksi. 

7. Luaskan dropdown **Pilih koneksi** dan pilih **+ Koneksi Baru**.

8. Jendela atau tab browser baru akan terbuka. Pilih **Buat** saat diminta untuk menghubungkan. Masuk jika diperlukan untuk menyelesaikan pembuatan koneksi.

9. Tutup tab saat ini sehingga Anda sekarang kembali ke tab **Impor Solusi** sebelumnya.

10. Pastikan koneksi yang baru saja Anda buat dipilih. Jika Anda tidak melihat koneksi Anda, klik **Refresh** untuk merefresh daftar koneksi. 

11. Tekan **Impor.**

12. Tunggu sampai impor selesai.

## <a name="task-2-import-data"></a>Tugas #2: Mengimpor Data  

1. Buka solusi **Impor Data**.

2. Periksa **Status** alur **Impor Data**.

3. Jika **Status** **Nonaktif**, pilih **...** di samping **Impor Data** lalu pilih **Aktifkan**.

   > **Penting:** Jika Anda menerima pesan kesalahan, pastikan tabel dan kolom yang Anda buat sesuai dengan petunjuk di atas.

4. Buka komponen **Impor Data**. Tab baru akan membuka Power Automate. 

5. Klik **Memulai** jika jendela sembul muncul. 

6. Klik **Jalankan** lalu klik **Jalankan alur** saat diminta.

7. Klik **Selesai**.

8. Tunggu hingga instans alur menyelesaikan proses. Anda dapat merefresh tabel **riwayat proses 28 hari** untuk melihat kapan alur berjalan. 

    > Tujuan dari alur ini adalah membuat contoh data untuk lab yang akan datang. Di tugas berikutnya, Anda akan memverifikasi bahwa impor data berhasil. 

## <a name="task-3-verify-data-import"></a>Tugas #3: Memverifikasi Impor Data

1. Navigasikan kembali ke tab Power Apps sebelumnya. Klik **Selesai** pada jendela sembul. 

2. Pilih **Solusi** di bilah navigasi kiri dan buka solusi **Manajemen Kampus** Anda.

2. Klik untuk membuka tabel **Kunjungi**, lalu pilih tab **Data**.

3. Klik **Kunjungan Aktif** di sudut kanan atas untuk menampilkan pemilih tampilan, lalu pilih **Semua kolom**. Ini akan mengubah tampilan yang digunakan untuk menampilkan data Kunjungan. 

    > Jika Anda tidak melihat **Kunjungan Aktif** karena resolusi yang lebih kecil, Anda akan melihat ikon mata di lokasi yang sama.

    > Jika impor berhasil, Anda akan melihat daftar baris kunjungan.

4. Klik nilai mana pun di kolom **Gedung**, konfirmasikan bahwa formulir Gedung terbuka di jendela terpisah. 

5. Tutup jendela yang baru saja diluncurkan.

6. Klik pada nilai apa pun di kolom **Pengunjung** (Anda mungkin perlu menggulir tampilan ke kanan), konfirmasikan bahwa formulir Kontak terbuka di jendela terpisah.

7. Tutup jendela yang baru saja diluncurkan.

# <a name="challenges"></a>Tantangan

* Apakah Anda mempertimbangkan untuk menggunakan aktivitas *janji temu* sebagai bagian dari solusi? Apa yang akan berubah?
* Bagaimana Anda bisa memberlakukan akhir yang dijadwalkan setelah awal yang dijadwalkan? 
* Bagaimana Anda bisa menambahkan dukungan untuk beberapa pertemuan selama satu kunjungan?
* Bagaimana Anda bisa mengamankan akses gedung tidak hanya untuk kontak eksternal tetapi juga untuk anggota staf internal?
* Bagaimana Anda bisa melakukan kunjungan ke gedung-gedung tertentu yang memerlukan persetujuan manajemen? Apa yang akan diubah oleh proses persetujuan dalam model data?

