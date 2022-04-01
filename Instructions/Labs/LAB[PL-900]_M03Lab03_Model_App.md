---
lab:
  title: 'Lab 4: Cara membuat aplikasi berbasis model'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: e0fcc3a12bb54b7fca08e41599d999b3e38eee23
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898982"
---
# <a name="module-3-get-started-with-power-apps"></a>Modul 3: Mulai dengan Power Apps
## <a name="lab-3-how-to-build-a-model-driven-app"></a>Lab 3: Cara membuat aplikasi berbasis model

# <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus. 

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus. 

Di lab ini, Anda akan membuat aplikasi berbasis model Power Apps untuk memungkinkan staf kampus backoffice mengelola catatan kunjungan di seluruh kampus.

# <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Sebagai bagian dari pembuatan aplikasi berbasis model, Anda akan menyelesaikan hal berikut:

-   Membuat aplikasi berbasis model baru bernama Manajemen Kampus

-   Mengedit navigasi aplikasi untuk merujuk tabel yang diperlukan

-   Menyesuaikan bentuk dan tampilan tabel yang diperlukan untuk aplikasi

Kami akan bekerja dengan komponen berikut:

- **Tampilan**: Tampilan memungkinkan pengguna menampilkan data yang ada dalam tabel formulir.

- **Formulir**: Di sinilah pengguna membuat/memperbarui baris baru dalam tabel.

Keduanya akan diintegrasikan ke aplikasi berbasis model untuk pengalaman pengguna yang lebih baik.

## <a name="prerequisites"></a>Prasyarat

* Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**
* Penyelesaian **Modul 2 Lab 1 - Pengantar Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai

-   Perubahan apa yang harus kami lakukan untuk meningkatkan pengalaman pengguna?

-   Apa yang harus kami sertakan dalam aplikasi berbasis model berdasarkan model data yang telah kami buat?
    
-   Penyesuaian apa yang dapat dilakukan pada peta situs aplikasi berbasis model?


# <a name="exercise-1-customize-views-and-forms"></a>Latihan \#1: Menyesuaikan Tampilan dan Formulir

**Tujuan:** Dalam latihan ini, Anda akan menyesuaikan tampilan dan bentuk tabel yang dibuat khusus yang akan digunakan dalam aplikasi berbasis model.

## <a name="task-1-edit-visit-form"></a>Tugas \#1: Mengedit Formulir Kunjungan

1.  Masuk ke <https://make.powerapps.com> jika Anda belum masuk.

2.  Pilih **lingkungan** Anda.

3.  Pilih **Solusi**.

4.  Klik untuk membuka solusi **Manajemen Kampus** Anda.

5.  Klik untuk membuka entitas **Kunjungan**.

6.  Pilih tab **Formulir** dan pilih jenis formulir **Utama** dan klik **Edit formulir**.

    > Secara default, formulir memiliki dua bidang: Nama (Bidang Utama) dan Pemilik.
    
7.  Pilih **+ Bidang formulir** dan tambahkan bidang berikut di bawah bidang **Pemilik** dengan menyeret kolom ke formulir atau cukup mengklik nama kolom:

    * **Bangunan**
    * **Pengunjung**
    * **Waktu Mulai yang Dijadwalkan**
    * **Waktu Selesai yang Dijadwalkan**
    * **Mulai Aktual**
    * **Akhir Aktual** 
    
8.  Seret kolom **Kode** dan letakkan di header formulir. 

    > Header adalah area kanan atas formulir. Anda mungkin perlu meminimalkan panel Properti di sisi kanan layar untuk melihat bidang pada formulir.

9.  Dengan bidang **Kode** masih dipilih, centang kotak **Baca-saja** di panel Properti.

10.  Pilih bidang **Pemilik**. Di panel Properti, ubah **Label bidang** menjadi **Host**

11.  Klik **Simpan** di kanan atas dan tunggu hingga penyimpanan selesai.

12.  Klik **Terbitkan** di kanan atas dan tunggu hingga penerbitan selesai.

13.  Jika tampilan edit dibuka di tab baru, tutup tab tersebut. Jika tidak, klik **Kembali** di kiri atas layar. Anda sekarang harus kembali ke Tab Formulir entitas Kunjungan.

## <a name="task-2-edit-visit-views"></a>Tugas \#2: Mengedit Tampilan Kunjungan

Dalam tugas ini, kami akan mengubah tampilan Kunjungan Aktif default dan membuat tampilan baru untuk kunjungan hari ini.

1.  Pilih tab **Tampilan** dan klik untuk membuka tampilan **Kunjungan Aktif**.

2.  Tambahkan bidang berikut ke tampilan dengan mengklik atau menyeret dan menjatuhkan bidang:

    *  **Kode**
    *  **Pengunjung**
    *  **Bangunan**
    *  **Waktu Mulai yang Dijadwalkan** 
    *  **Waktu Selesai yang Dijadwalkan**
    
3.  Klik kolom **Dibuat Pada** dan pilih **Hapus**. Bidang **Dibuat Pada** sekarang akan dihapus dari tampilan.

4.  Klik kolom **Nama** dan pilih **Hapus**. Bidang **Nama** sekarang akan dihapus dari tampilan.

5.  Di panel Properti di sebelah kanan, klik **Urutkan menurut ...** dan pilih **Waktu Mulai yang Dijadwalkan**. Klik **Waktu Mulai yang Dijadwalkan** lagi untuk mengubah urutan menjadi menurun.

6.  Ubah ukuran lebar kolom masing-masing agar sesuai dengan data.

7.  Klik **Simpan** dan tunggu hingga perubahan disimpan.

8.  Klik **Terbitkan** dan tunggu hingga penerbitan selesai.

Sekarang, kami akan mengkloning tampilan untuk membuat tampilan baru untuk kunjungan hari ini.

9.  Tekan tautan **Edit filter** di panel Properti.

10.  Klik **Tambahkan**, pilih **Tambahkan baris**.

11.  Pilih **Waktu Mulai yang Dijadwalkan** sebagai bidang, lalu pilih **Hari ini** sebagai ketentuan di dropdown. 

12.  Klik **...** pada baris **Status** dan klik **Hapus**. 

13.  Tekan **Oke** untuk menyimpan kondisi. Tampilan sekarang difilter untuk menampilkan hanya catatan dengan tanggal Mulai Terjadwal adalah hari ini.

14.  Tambahkan bidang **Waktu Mulai Aktual** dan **Waktu Selesai Aktual** ke tampilan. 

    > **Catatan:** Karena kami tidak lagi memfilter status tampilan, kami akan mendapatkan semua kunjungan hari ini termasuk yang sudah selesai. Kolom ini akan membantu membedakan kunjungan yang telah selesai dan kunjungan yang sedang berlangsung.

15.  Klik **panah dropdown** di sebelah tombol Simpan (hati-hati jangan sampai tidak sengaja menekan tombol itu) dan pilih **Simpan Sebagai**.

16.  Ubah nama menjadi **Kunjungan Hari Ini** dan tekan **Simpan**.

17.  Klik **Terbitkan** dan tunggu hingga penerbitan selesai.

# <a name="exercise-2-create-model-driven-application"></a>Latihan \#2: Membuat Aplikasi Berbasis Model

**Tujuan:** Dalam latihan ini, Anda akan membuat aplikasi berbasis model, menyesuaikan peta situs, dan menguji aplikasi.

> Anda akan melihat beberapa bidang tidak ditangani saat Anda membangun aplikasi Anda, terutama pada langkah-langkah peta situs. Kami telah mengambil beberapa jalan pintas untuk kepentingan melakukan lab. Dalam implementasi nyata, Anda akan memberi nama item ini dengan nama yang logis.

## <a name="task-1-create-application"></a>Tugas \#1: Membuat Aplikasi

1.  Buka solusi Manajemen Kampus Anda jika Anda belum melakukannya.

    -   Masuk ke <https://make.powerapps.com>

    -   Saat berada di lingkungan Anda, klik untuk membuka solusi **Manajemen Kampus** Anda.
    
2.  Membuat Aplikasi Berbasis Model

    -   Klik **Baru** dan pilih **Aplikasi** lalu **Aplikasi berbasis model**.
    
    -   Di aplikasi berbasis model dari layar kosong, klik **Buat**.
    
    -   Masukkan **[Nama Belakang Anda] Manajemen Kampus** untuk Nama.

    -   Pilih kotak centang **Gunakan solusi yang ada untuk membuat Aplikasi**

    -   Pilih **Selanjutnya**

    -   Pilih solusi **Manajemen Kampus** Anda
    
    -   Klik **Selesai**
    
3.  Klik ikon pensil di samping **Peta Situs.**

4.  Mengedit judul default

    -   Pilih **Area Baru**.

    -   Ubah Judul Area Baru menjadi **Kampus** di panel properti di sebelah kanan.

    -   Pilih **Grup Baru**.

    -   Ubah Judul Grup Baru menjadi **Keamanan** di panel properti di sebelah kanan.
    
5.  Menambahkan tabel Kontak ke peta situs

    -   Pilih **Subarea Baru**.

    -   Di panel **Properti**, pilih **Entitas** dari dropdown untuk **Jenis**.

    -   Cari tabel **Kontak** dari dropdown untuk **Entitas**.
    
6.  Menambahkan tabel Kunjungan ke peta situs

    -   Pilih grup **Keamanan** dan klik **Tambahkan**.

    -   Pilih **Subarea**.

    -   Buka panel **Properti**.

    -   Pilih **Entitas** dari dropdown untuk **Jenis** dan cari tabel **Kunjungan** dari dropdown untuk **Entitas**.
    
7.  Menambahkan tabel Gedung ke peta situs

    -   Pilih area **Kampus** dan klik **Tambahkan**.
    
    -   Pilih **Grup**.
    
    -   Masukkan **Pengaturan** untuk **Judul** di panel **Properti**.
    
    -   Dengan grup **Pengaturan** masih dipilih, klik **Tambahkan**.
    
    -   Pilih **Subarea**.
    
    -   Buka panel **Properti**.
    
    -   Pilih **Entitas** dari dropdown untuk **Jenis** dan cari tabel **Gedung** dari dropdown untuk **Entitas**.

8.  Klik **Simpan**. Ini akan menampilkan layar pemuatan saat perubahan disimpan.

9.  Klik **Terbitkan** untuk menerbitkan peta situs dan tunggu hingga penerbitan selesai.

10.  Klik **Simpan dan Tutup** untuk menutup editor peta situs. 

    > Anda akan melihat aset untuk entitas yang ditambahkan ke peta situs sekarang ada di aplikasi.
     
11.  Klik **Simpan** pada Perancang Aplikasi.

12.  Klik **Validasi** untuk memvalidasi perubahan yang dilakukan dalam aplikasi. 

    >  Ini akan menampilkan beberapa peringatan tetapi kami dapat mengabaikannya, karena kami belum mereferensikan Tampilan dan Formulir tertentu untuk entitas dan pengguna akan memiliki akses ke semua Tampilan dan Formulir untuk entitas **Kunjungan** dan **Gedung**.
     
13. Klik **Terbitkan**

14.  Klik **Simpan dan Tutup** untuk menutup perancang aplikasi.

15.  Klik **Selesai**.

16.  Pilih **Solusi** dan pilih **Terbitkan semua Penyesuaian.**

17.  Pilih **Aplikasi** dan aplikasi Anda sekarang akan terdaftar.

## <a name="task-2-test-application"></a>Tugas \#2: Menguji Aplikasi

1.  Mulai aplikasi

    -   Pilih **Aplikasi** dan klik aplikasi **Manajemen Kampus** Anda. (Jika Anda tidak melihat aplikasi Anda pada awalnya, Anda mungkin perlu merefresh browser Anda.)

    -   Aplikasi aksn terbuka di jendela baru.
    
2.  Membuat Kontak baru

    -   Aplikasi akan terbuka ke tampilan **Kontak Aktif**

    -   Klik **Baru** dari menu atas.

    -   Berikan **Nama Depan** sebagai `John` dan **Nama Belakang** sebagai `Doe`.

    -   Berikan email pribadi Anda sebagai **Email**. Ini akan digunakan di lab masa depan. 
    
    -   Klik **Simpan dan Tutup**.

    -   Anda sekarang akan melihat kontak yang dibuat pada tampilan **Kontak Aktif**.
    
3.  Membuat Gedung baru

    -   Pilih **Gedung** dari peta situs.

    -   Klik **Baru**.

    -   Masukkan **Nama** sebagai `Microsoft Building`
        
    -   Klik **Simpan dan Tutup**. Ini akan menampilkan catatan yang baru dibuat pada Tampilan Gedung Aktif.
    
4.  Membuat Kunjungan baru

    -   Pilih **Kunjungan** dari peta situs.
    
    -   Klik **Baru**.
    
    -   Masukkan bidang sebagai berikut 
    
        -   **Nama**: `New test visit`
        -   **Gedung**: Rumah Alpine Ski
        -   **Pengunjung**: pilih John Doe
        -   **Waktu Mulai yang Dijadwalkan**: pilih tanggal besok dan 14.00 sebagai waktu mulai
        -   **Waktu Selesai yang Dijadwalkan**: pilih tanggal besok dan 15.30 sebagai waktu berakhir
        
    -   Klik **Simpan dan Tutup**. Ini akan membuat Kunjungan dan Anda akan dapat melihatnya di Tampilan Kunjungan Aktif.
        
    -   Ubah tampilan menjadi **Kunjungan Hari Ini**. Anda sekarang tidak akan melihat kunjungan baru lagi dalam tampilan, karena dijadwalkan untuk besok.
    
5. Anda dapat menambahkan lebih banyak catatan pengujian.

   Aplikasi Anda yang sedang berjalan akan terlihat kira-kira seperti berikut:

![Aplikasi berbasis model sampel](media/3-model-app.png)

# <a name="challenges"></a>Tantangan

* Pilih tampilan dan formulir khusus untuk Kunjungan dan Gedung
* Personil keamanan biasanya bekerja di satu gedung. Bagaimana Anda menyediakan cara mudah bagi mereka untuk menampilkan kunjungan hanya untuk bangunan yang dipilih?
* Membatasi akses ke entitas tertentu, misalnya Gedung harus diatur ke baca-saja untuk semua anggota staf kecuali administrator
* Dasbor apa yang akan Anda pertimbangkan untuk ditambahkan ke aplikasi?
