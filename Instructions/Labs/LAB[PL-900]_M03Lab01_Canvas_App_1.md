---
lab:
  title: 'Lab 2: Cara membuat aplikasi kanvas, Bagian 1'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: ac6cec75309098dae7715c0bdf42db75c9b80429
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898893"
---
# <a name="module-3-get-started-with-power-apps"></a>Modul 3: Mulai dengan Power Apps

## <a name="lab-how-to-build-a-canvas-app-part-1"></a>Lab: Cara membuat aplikasi kanvas, Bagian 1

# <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Kunjungan kampus saat ini dicatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus. 

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.  

Di bagian 1 lab ini, Anda akan mendesain aplikasi kanvas Power Apps yang dapat digunakan staf perguruan tinggi untuk mengelola kunjungan tamu mereka.

# <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Kami akan mengikuti garis besar di bawah ini untuk mendesain aplikasi kanvas:

-   Membuat aplikasi dari data menggunakan template faktor bentuk ponsel
-   Mengonfigurasi halaman detail dengan info kunjungan
-   Mengonfigurasi halaman edit untuk membuat kunjungan
-   Mengonfigurasi kontrol galeri untuk menampilkan kunjungan
-   Menambahkan pemfilteran pada sumber data galeri untuk hanya menampilkan kunjungan mendatang

## <a name="prerequisites"></a>Prasyarat

* Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**
* Penyelesaian **Modul 2 Lab 1 - Pengantar Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai

-   Apa faktor bentuk yang paling umum untuk audiens target?
-   Memperkirakan jumlah catatan dalam sistem 
-   Cara mempersempit catatan yang dipilih untuk meningkatkan performa aplikasi dan adopsi pengguna

# <a name="exercise-1-create-staff-canvas-app"></a>Latihan \#1: Membuat Aplikasi Kanvas Staf

**Tujuan:** Dalam latihan ini, Anda akan membuat aplikasi kanvas dari template dan kemudian memodifikasinya untuk menyertakan data yang diperlukan.

## <a name="task-1-create-canvas-app"></a>Tugas \#1: Membuat Aplikasi Kanvas

Dalam tugas ini, Anda akan membuat aplikasi kanvas menggunakan template tata letak ponsel berdasarkan Microsoft Dataverse. Menggunakan Kunjungan sebagai tabel yang dipilih dari Dataverse, template akan menghasilkan Galeri - Lihat - Edit aplikasi untuk mengelola kunjungan kampus.

1.  Mulai membuat aplikasi dari data

    -   Masuk ke <https://make.powerapps.com>

    -   Pilih **lingkungan** Anda di kanan atas jika belum diatur ke lingkungan Latihan Anda.

    -   Pilih ikon **Dataverse** dalam **Mulai dari data** di layar Utama.

2.  Menghubungkan ke tabel Kunjungan Anda
    
    -   Pilih **+ Koneksi baru**

    -   Pilih **Microsoft Dataverse** dan klik **Buat**

    -   Cari dan pilih tabel **Kunjungan** Anda

    -   Pilih **Sambungkan**

3.  Jendela **Selamat datang di Power Apps Studio** mungkin muncul. Klik **Lewati**.

4.  Simpan aplikasi

    -   Klik **File\> Simpan**.

    -   Masukkan Staf Kampus [Nama Belakang Anda] sebagai **Nama aplikasi**.

    -   Tekan **Simpan**.

## <a name="task-2-configure-visits-detail-form"></a>Tugas \#2: Mengonfigurasi Formulir Detail Kunjungan

Dalam tugas ini, Anda akan mengonfigurasi formulir Detail untuk melihat informasi tentang catatan kunjungan individu.

1. Pilih panah **Kembali** di kiri atas untuk kembali ke definisi aplikasi.

2. Luaskan **DetailScreen1** di bagian **Tampilan pohon**

3.  Pilih **DetailForm1**

4.  Pilih **Edit bidang** di samping **Bidang** di panel sebelah kanan.

5.  Klik **Tambahkan bidang**

6.  Pilih bidang berikut:

    * Akhir Aktual
    
    * Mulai Aktual
    
    * Gedung 
    
    * Kode
    
    * Waktu Selesai yang Dijadwalkan
    
    * Waktu Mulai yang Dijadwalkan
    
    * Pengunjung
    
7.  Klik **Tambahkan**

8.  Susun ulang bidang di panel **Bidang** dengan menyeret dan menjatuhkan nama bidang ke atas atau ke bawah. Urutan yang direkomendasikan adalah:
    * Kode, Nama, Gedung, Pengunjung, Waktu Mulai yang Dijadwalkan, Waktu Selesai yang Dijadwalkan, Waktu Mulai Aktual, Waktu Selesai Aktual
    >**Tips:** Anda dapat menutup setiap bidang dengan mengklik panah bawah di samping nama bidang.

9.  Hapus bidang **Dibuat Pada** dengan mengklik elipsis ( **...** ) di samping nama bidang dan pilih **Hapus**. 

10.  Tutup panel **Bidang**.
 
11.  Untuk menyimpan pekerjaan yang sedang dikerjakan, klik **File** lalu klik **Simpan**. Gunakan panah kembali untuk kembali ke aplikasi.

## <a name="task-3-configure-visits-edit-form"></a>Tugas \#3: Mengonfigurasi Formulir Edit Kunjungan

Dalam tugas ini, Anda akan mengonfigurasi formulir untuk mengedit informasi tentang baris kunjungan individual.

1.  Luaskan **EditScreen1** di bagian **Tampilan pohon**

2.  Pilih **EditForm1**

3.  Pilih bidang **Dibuat Pada** dan tekan tombol **Del** untuk menghapus bidang

4.  Pilih **Edit bidang** di panel properti

5.  Klik **Tambahkan bidang**

6.  Pilih bidang berikut:

    * Gedung 
    
    * Waktu Selesai yang Dijadwalkan
    
    * Waktu Mulai yang Dijadwalkan
    
    * Pengunjung
    
7.  Klik **Tambahkan**

8.  Susun ulang bidang di panel **Bidang** dengan menyeret dan menjatuhkan nama bidang ke atas atau ke bawah. Urutan yang direkomendasikan adalah:
    
    * Nama, Gedung, Pengunjung, Awal Terjadwal, Akhir Terjadwal
    >**Tips:** Anda dapat menutup setiap bidang dengan mengklik panah bawah di samping nama bidang. 

9.  Tutup panel **Bidang**.

10.  Untuk menyimpan pekerjaan yang sedang dikerjakan, klik **File** lalu klik **Simpan**. Gunakan panah kembali untuk kembali ke aplikasi.

Layar Anda akan terlihat kira-kira seperti berikut:

![Formulir edit kanvas](media/2-canvas-edit-form.png)

## <a name="task-4-configure-visits-gallery"></a>Tugas \#4: Mengonfigurasi galeri Kunjungan

Dalam tugas ini, Anda akan mengonfigurasi galeri yang dibuat sebelumnya untuk menampilkan judul, tanggal mulai, dan tanggal akhir kunjungan. 

1.  Luaskan **BrowseScreen1** di bagian **Tampilan pohon**

2.  Pilih **BrowseGallery1**

3.  Pilih properti **TemplateSize** dari panel Properti Tingkat Lanjut di sebelah kanan

4.  Ganti ekspresi dengan `Min(150, BrowseGallery1.Height - 60)` berikut. Tindakan ini akan memastikan ruang yang cukup untuk informasi tambahan.

5.  Di pratinjau aplikasi, pilih bidang Tanggal Waktu pertama di galeri.

6.  Pada bilah rumus di bagian atas, ubah **ThisItem.'Dibuat Di'** menjadi `ThisItem.'Scheduled Start'`

7.  Pilih bidang lagi

8.  Tekan **CTRL-C** lalu **CTRL-V** untuk membuat salinan bidang.

9.  Dengan mouse atau keyboard, pindahkan kontrol yang disalin ke bawah dan sejajarkan dengan kontrol lain di galeri, di bawah bidang Tanggal Waktu lainnya.

10.  Pada bilah rumus di bagian atas, ubah **ThisItem.'Waktu Mulai yang Dijadwalkan'** menjadi `ThisItem.'Scheduled End'`

11.  Untuk menyimpan pekerjaan yang sedang dikerjakan, klik **File** lalu klik **Simpan**. Gunakan panah kembali untuk kembali ke aplikasi.

## <a name="task-5-add-date-filter"></a>Tugas #5: Menambahkan filter tanggal

Karena jumlah kunjungan terus bertambah, pengguna memerlukan fitur untuk memfilter galeri kunjungan. Misalnya, pengguna mungkin hanya ingin melihat kunjungan berikutnya. Dalam tugas ini, Anda akan menambahkan kemampuan untuk menampilkan kunjungan hanya setelah tanggal yang dipilih oleh pengguna.

1. Pilih **BrowseScreen1**

2. Pilih menu **Sisipkan** di bagian atas.

3. Klik **Masukkan** dan pilih **Pemilih tanggal**.

4. Dengan keyboard atau mouse, posisikan kontrol di bawah kotak pencarian.

5. Pilih **BrowseGallery1** 

6. Ubah ukuran dan pindahkan kontrol galeri sehingga terletak di bawah pemilih tanggal dan menutupi layar. Anda dapat melakukannya dengan mengklik ikon ubah ukuran di bagian tengah atas kontrol galeri dan mengubah ukuran kontrol untuk memulai setelah pemilih tanggal.

7. Dengan **BrowseGallery1** dipilih, klik tab **Tingkat Lanjut** pada panel Properti.

8. Cari properti **Item** dan klik di kotak teks.

9. Dalam ekspresi, cari **[@Visits]** dan ganti dengan `Filter(Visits,'Scheduled End' >= DatePicker1.SelectedDate)`. Ekspresi penuh akan terlihat seperti berikut:

   ```
   SortByColumns(
    Search(
        Filter(
            Visits,
            'Scheduled End' >= DatePicker1.SelectedDate
           ),
           TextSearchBox1.Text,
        "bc_code","bc_name"
       ),
     "bc_scheduledstart",
     If(SortDescending1, Descending, Ascending)
   )
   ```
   
10. Untuk menyimpan pekerjaan yang sedang dikerjakan, klik **File** lalu klik **Simpan**. Gunakan panah kembali untuk kembali ke aplikasi.

Layar Anda akan terlihat kira-kira seperti berikut:

![Galeri pemfilteran kanvas](media/2-canvas-browse.png)

# <a name="exercise-2-complete-the-app"></a>Latihan #2: Melengkapi Aplikasi

Dalam latihan ini Anda akan menguji aplikasi dan, setelah berhasil, Anda akan menambahkannya ke solusi Anda.

## <a name="task-1-test-app"></a>Tugas \#1: Menguji Aplikasi

1.  Mulai aplikasi

    -   Pilih **BrowseScreen1** dan tekan Fungsi **F5**, atau klik ikon **Putar** di sudut kanan atas untuk melihat pratinjau aplikasi.
    
    -   Aplikasi akan memuat dan menampilkan daftar kunjungan. 
    
    -   Menguji filter dengan memilih tanggal yang berbeda di kontrol pemilih tanggal
    
    -   Memilih kunjungan dan memverifikasi bahwa formulir tampilan berfungsi dengan baik
    
    -   Kembali ke galeri dan tekan **+** untuk membuat kunjungan baru. Verifikasi bahwa formulir edit berisi kolom yang diperlukan termasuk pengunjung, gedung, dan tanggal mulai dan berakhir yang dijadwalkan.
    
    -   Isi informasi dan kirimkan. Verifikasi bahwa catatan baru muncul di galeri.
    
    -   Buat setidaknya 2 kunjungan lagi.
    
    -   Tekan tombol **ESC** atau klik ikon **X** untuk menutup mode pratinjau.

2.  Simpan dan terbitkan aplikasi

    -   Klik **File** dan, jika tombol Simpan ditampilkan, klik **Simpan**.

    -   Klik **Terbitkan**.

    -   Klik **Terbitkan Versi ini**.

    -   Klik panah **Kembali** untuk menavigasi kembali ke aplikasi.

    -   Tutup jendela atau tab browser **Perancang**.

    -   Klik **Tinggalkan** jika diminta saat mencoba menutup jendela browser.

## <a name="task-2-add-app-to-solution-and-publish"></a>Tugas #2: Menambahkan Aplikasi ke Solusi dan menerbitkan 

1. Membuka solusi Manajemen Kampus.

   * Masuk ke <https://make.powerapps.com>
   
   * Jika Lingkungan yang ditampilkan di kanan atas bukan lingkungan Latihan Anda, pilih **Lingkungan** Anda. 
   
   * Pilih **Solusi**.
   
   * Klik untuk membuka solusi **Manajemen Kampus** Anda.
   
2. Pilih **Tambahkan yang ada**, lalu klik **Aplikasi**, lalu klik **Aplikasi kanvas**.

3. Pilih tab **Di luar Dataverse**.

4. Pilih aplikasi **Staf Kampus** Anda, klik **Tambahkan**.

5. Pilih **Terbitkan semua penyesuaian**.

# <a name="challenges"></a>Tantangan

* Tampilan kalender dari semua kunjungan dan pemfilteran menurut rentang tanggal
* Kemampuan untuk membuat dan mengelola kontak sebagai bagian dari aplikasi
* Cara menampilkan beberapa pertemuan selama satu kunjungan

