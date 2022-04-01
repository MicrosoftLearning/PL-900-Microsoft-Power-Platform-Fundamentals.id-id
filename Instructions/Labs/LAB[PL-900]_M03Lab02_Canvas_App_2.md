---
lab:
  title: 'Lab 3: Cara membuat aplikasi kanvas, bagian 2'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: c26f032744e228dc6632d254ad127f39cdbdef02
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898958"
---
# <a name="module-3-get-started-with-power-apps"></a>Modul 3: Mulai dengan Power Apps
## <a name="lab-2-how-to-build-a-canvas-app-part-2"></a>Lab 2: Cara membuat aplikasi kanvas, bagian 2

# <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Kunjungan kampus saat ini dicatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus. 

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus. 

Di bagian 2 lab ini, Anda akan membuat desain dan membangun aplikasi kanvas Power Apps yang akan digunakan personel keamanan di pintu masuk gedung untuk mengonfirmasi dan mendaftarkan pengunjung dengan cepat.

# <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Anda akan mengikuti garis besar di bawah ini untuk mendesain aplikasi kanvas:

-   Membuat aplikasi menggunakan faktor bentuk ponsel
-   Menghubungkan ke Dataverse sebagai sumber data
-   Menangkap input (kode pengunjung) dan menemukan baris pengunjung
-   Mengonfigurasi kontrol penampil formulir untuk menampilkan informasi pengunjung
-   Menggunakan tampilan Dataverse untuk mengisi galeri
-   Menangani proses check-in dan check-out pengunjung

## <a name="prerequisites"></a>Prasyarat

* Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**
* Penyelesaian **Modul 2 Lab 1 - Pengantar Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai

-   Informasi apa yang dibutuhkan petugas keamanan untuk diakses dengan cepat?
-   Apa yang akan terjadi jika kode pengunjung tidak valid?
-   Apa yang akan terjadi jika pengunjung tiba di luar jam yang dijadwalkan?

# <a name="exercise-1-create-security-canvas-app"></a>Latihan \#1: Membuat Aplikasi Kanvas Keamanan

**Tujuan:** Dalam latihan ini, Anda akan membuat aplikasi kanvas.

## <a name="task-1-create-canvas-app"></a>Tugas \#1: Membuat Aplikasi Kanvas

1.  Buka solusi Manajemen Kampus Anda.

    -   Masuk ke <https://make.powerapps.com>

    -   Jika Lingkungan yang ditampilkan di kanan atas bukan lingkungan Latihan Anda, pilih **Lingkungan** Anda. 

    -   Pilih **Solusi**.

    -   Klik untuk membuka solusi **Manajemen Kampus** Anda.
    
2.  Membuat aplikasi kanvas baru

    -   Klik **Baru** dan pilih **Aplikasi \| Aplikasi Kanvas**.

    -   Di aplikasi Kanvas dari jendela kosong, masukkan **[Nama Belakang Anda] Keamanan Kampus** di bidang Nama aplikasi.

    -   Pilih **Ponsel** di bidang Format.

    -   Klik **Buat**.
        Ini akan membuka Editor Aplikasi di jendela Baru. Klik **Lewati** jika dialog Selamat Datang di Power Apps Studio muncul.
    
3.  Menyimpan aplikasi kanvas

    -   Klik **File** dan pilih **Simpan Sebagai**.
    
    -   Periksa apakah **Cloud** dipilih, klik **Simpan**.

    - Verifikasi **[Nama Belakang Anda] Keamanan Kampus** untuk Nama dan klik **Simpan**.
        
    -   Klik panah **Kembali** di kiri atas (di bawah Power Apps) untuk kembali ke aplikasi.

3.  Menghubungkan ke sumber data (Kunjungan)

    -   Klik **Lihat \| Sumber data**
    
    -   Klik **+ Tambahkan Data**

    -   Klik **Lihat semua tabel**
    
    -   Pilih **Kunjungan** dan tunggu hingga tabel Kunjungan ditampilkan di tab Data.
    
4.  Untuk menyimpan pekerjaan yang sedang dikerjakan, klik **File** lalu klik **Simpan**. Gunakan panah kembali untuk kembali ke aplikasi.

## <a name="task-2-display-visitor-information"></a>Tugas \#2: Menampilkan informasi Pengunjung

1.  Menambahkan kotak pencarian

    -   Pilih tab **Tampilan Pohon** di bilah navigasi kiri.
    
    -   Pilih **Screen1**.
    
    -   Buka tab **Sisipkan**.
    
    -   Klik **Teks** dan pilih **Masukan teks**.
    
2.  Mengedit objek input teks

    -   Saat masih memilih objek Input teks, pilih teks di properti **Default** dan kosongkan nilainya.
    
    -   Pilih properti **Teks Petunjuk** dan masukkan `"Enter visitor code"` sebagai nilainya (termasuk tanda kutip ganda)
    
    -   Klik **...** di sebelah nama kontrol dalam tampilan hierarki (TextInput1), pilih **Ganti nama**, ubah namanya menjadi `textCode`
    
3.  Menambahkan tampilan formulir

    -   Pada tab **Sisipkan** klik **Formulir** lalu pilih **Tampilan** (Anda mungkin perlu mengklik panah bawah di sisi kanan pita untuk melihat Formulir)
   
    -   Seret untuk memposisikan formulir dan sejajarkan dengan bagian bawah layar
   
    -   Saat masih memilih formulir baru, pilih properti **DataSource** dan pilih **Kunjungan**
   
    -   Di panel properti pilih **Horizontal** sebagai **Tata letak**

4.  Mengedit tampilan formulir

    -   Saat masih memilih formulir baru, klik **Edit bidang**

    -   Hapus bidang **Nama** dan **Dibuat Pada**

    -   Klik **Tambahkan bidang** dan pilih bidang berikut: **Waktu Selesai Aktual**, **Waktu Mulai Aktual**, **Gedung**, **Waktu Selesai yang Dijadwalkan**, **Waktu Mulai yang Dijadwalkan**, **Pengunjung**
   
    -   Tekan **Tambahkan**
   
    -   Ubah urutan bidang yang dipilih dengan menyeret kartu bidang dalam daftar. Urutan yang direkomendasikan adalah: Pengunjung, Gedung, Waktu Mulai yang Dijadwalkan, Waktu Selesai yang Dijadwalkan, Waktu Mulai Aktual, Waktu Selesai Aktual (Anda dapat menciutkan bidang agar lebih mudah diseret)
   
    -   Klik **X** untuk menutup panel Bidang
   
5.  Saat masih memilih tampilan formulir, pilih tab Tingkat Lanjut pada panel Properti. Pilih properti **Item** dan masukkan `LookUp(Visits, Code = textCode.Text)` 

6.  Untuk menyimpan pekerjaan yang sedang dikerjakan, klik **File** lalu klik **Simpan**. Gunakan panah kembali untuk kembali ke aplikasi.

7.  Bersiaplah untuk menguji aplikasi

    -   Beralih ke tab browser yang berisi solusi

    -   Klik **Selesai** di jendela sembul
   
    -   Pilih tabel **Kunjungi**
   
    -   Pilih tab **Data**
   
    -   Buka Pemilih Tampilan di kanan atas dengan mengklik nama Tampilan saat ini, **Kunjungan Aktif**
   
    -   Mengubah Tampilan menjadi **Semua kolom**
   
    -   Cari baris Kunjungan yang tidak memiliki nilai Waktu Mulai Aktual atau Waktu Selesai Aktual (yaitu, kedua kolom kosong). Pilih dan salin **Kode** untuk Kunjungan ini.

8.  Menguji aplikasi

    -   Beralih ke tab browser dengan aplikasi, tekan **F5** atau klik ikon **Putar** di sudut kanan atas untuk melihat pratinjau aplikasi.
   
    -   Rekatkan nilai yang disalin ke dalam kotak teks pencarian, verifikasi bahwa catatan ditampilkan dalam formulir
   
9.  Kosongkan konten kotak teks pencarian.
   
10.  Tekan **ESC** untuk keluar dari aplikasi yang sedang berjalan.

## <a name="task-3-add-check-in-and-check-out-buttons"></a>Tugas \#3: Menambahkan Tombol Check In dan Check Out

Dalam tugas ini, kami akan membuat tombol bagi pengguna untuk check in dan check out dari Kunjungan mereka. 

1. Simpan hasil pencarian dalam variabel untuk digunakan kembali di seluruh kontrol

    * Pilih kontrol **textCode**
   
    * Di panel properti, pilih tab **Tingkat Lanjut** dan pilih properti **OnChange**
   
    * Masukkan ekspresi berikut `Set(Visit, LookUp(Visits, Code = textCode.Text))`
    
    > Ekspresi ini akan menyimpan kunjungan dalam variabel global ketika pengguna mencari di kotak pencarian kode teks. Ekspresi ini memungkinkan kami menggunakan variabel *Kunjungan* di seluruh aplikasi tanpa perlu memasukkan kembali seluruh ekspresi pencarian.

2. Menambahkan Tombol Check In

   * Pilih tab **Sisipkan**
   
   * Klik **Tombol**
   
   * Di panel properti, ubah properti tombol **Teks** menjadi "`Check In`" (Anda dapat mengetik di dalam tanda kutip yang ada)
   
   * Klik **...** di samping nama tombol dalam tampilan hierarki (Button1), pilih **Ganti nama**, ubah namanya menjadi `CheckInButton`

3. Menambahkan Tombol Check Out   

   * Klik **Tombol** pada tab Sisipkan untuk menyisipkan tombol lain
   
   * Di panel properti, ubah properti tombol **Teks** menjadi "`Check Out`" (Anda dapat mengetik di dalam tanda kutip yang ada)
   
   * Ganti nama tombol menjadi `CheckOutButton`
   
   * Posisikan tombol di bawah kotak pencarian, dengan **Check In** di atas **Check Out** 
   
## <a name="task-4-enable-and-disable-buttons-depending-on-visit-data"></a>Tugas \#4: Aktifkan dan nonaktifkan tombol tergantung pada data kunjungan

Setelah pengguna melihat kunjungan, kami ingin mereka menggunakan tombol Check In untuk check in di kunjungan tersebut. Kami ingin mengaktifkan tombol **Check In** jika catatan kunjungan telah ditemukan (tidak kosong), status catatan aktif, dan kunjungan belum dimulai, yaitu nilai mulai aktual kosong.

1. Pilih **tombol Check In** dan klik properti **Mode Tampilan** tombol di tab Properti

2. Masukkan ekspresi di bawah ini di bilah fungsi:

      ```
      If(!IsBlank(Visit) 
      && Visit.Status = 'Status (Visits)'.Active
      && IsBlank(Visit.'Actual Start'),
          DisplayMode.Edit,
          DisplayMode.Disabled
      )
      ```

   Ekspresi dapat dipecah sebagai berikut:

   * **!IsBlank(Kunjungan)** - catatan kunjungan ditemukan
   * **&&** - operator logika AND
   * **Visit.Status = 'Status (Kunjungan)'.Status aktif** catatan adalah *Aktif*
   * **IsBlank(Visit.'Actual Start')** - Bidang Waktu Mulai Aktual tidak memiliki data apa pun di dalamnya
   * **DisplayMode.Edit, DisplayMode.Disabled** - Jika kondisi di atas terpenuhi, tombol akan dapat diedit. Jika tidak, tombol akan tetap dinonaktifkan.

Kami ingin mengaktifkan tombol **Check Out** ketika catatan kunjungan telah ditemukan (tidak kosong), status catatan aktif, dan kunjungan telah dimulai, yaitu nilai awal yang sebenarnya tidak kosong.

3. Pilih tombol Check Out dan klik properti **Mode Tampilan** dari tombol di tab Properti

4. Masukkan ekspresi di bawah ini di bilah fungsi:

     ```
     If(!IsBlank(Visit) 
     && Visit.Status = 'Status (Visits)'.Active
     && !IsBlank(Visit.'Actual Start'),
         DisplayMode.Edit,
         DisplayMode.Disabled
     )
     ```

5. Untuk menyimpan pekerjaan yang sedang dikerjakan, klik **File** lalu klik **Simpan**. Gunakan panah kembali untuk kembali ke aplikasi.

6. Tekan **F5** untuk menjalankan aplikasi. 

7. Kedua tombol harus dinonaktifkan. Masukkan nilai kode yang Anda salin sebelumnya dan tekan **Tab** untuk mengalihkan fokus dari kotak teks (atau klik di luar kotak teks). Tombol **Check In** harus diaktifkan. 

8. Kosongkan isi kotak pencarian.

9. Tekan **ESC** untuk keluar dari aplikasi yang sedang berjalan.

## <a name="task-5-complete-check-in-and-check-out-process"></a>Tugas \#5: Menyelesaikan Proses Check In dan Check Out

Untuk melakukan proses check in dan check out kita perlu memperbarui data kunjungan Dataverse sebagai berikut:

* Saat pengunjung check in, atur bidang *Waktu Mulai Aktual* ke tanggal dan waktu saat ini
* Saat pengunjung check out, atur bidang *Waktu Selesai Aktual* ke tanggal dan waktu saat ini. 
* Setelah check out, atur status catatan menjadi tidak aktif, yang menunjukkan bahwa kunjungan telah selesai

1. Pilih tombol **Check In**.

2. Atur properti **OnSelect** pada tab Tingkat Lanjut ke ekspresi berikut.

   ```
   Patch(
       Visits,
       Visit,
       {'Actual Start': Now()}
   );
   Refresh([@Visits]);
   Set(Visit, LookUp(Visits, Code = textCode.Text));
   ```

   Ekspresi ini berisi bagian-bagian berikut:

   * **Patch(Kunjungan, Kunjungan, {'Waktu Mulai Aktual': Sekarang()});** . Metode *Patch* memperbarui tabel **Kunjungan**, baris yang diidentifikasi oleh variabel **Kunjungan** (yang merupakan kunjungan saat ini). Ekspresi mengatur nilai kolom *Waktu Mulai Aktual* ke tanggal dan waktu saat ini (metode *Sekarang()* ).
   * **Refresh([@Visits]);** . Ekspresi ini merefresh baris kunjungan, karena nilai yang mendasarinya telah berubah
   * **Set(Visit, LookUp(Visits, Code = textCode.Text));** Ekspresi ini memperbarui variabel *Kunjungan* dengan data baru dari Dataverse.
   
   > Ketika pengguna mengklik tombol ini, Waktu Mulai Aktual akan diatur ke tanggal dan waktu saat ini dan data akan diperbarui.

3. Pilih tombol **Check Out**.

4. Atur properti **OnSelect** pada tab Tingkat Lanjut ke ekspresi berikut:

   ```
   Patch(
       [@Visits],
       Visit,
       {
           'Actual End': Now(),
           Status: 'Status (Visits)'.Inactive
       }
   );
   Refresh([@Visits]);
   Set(Visit, LookUp(Visits, Code = textCode.Text));
   ```

   Ketika pengguna mengklik tombol ini, Akhir Aktual akan diatur ke tanggal dan waktu saat ini, Status Kunjungan akan diatur ke Tidak Aktif, dan data akan direferesh.

5. Untuk menyimpan pekerjaan yang sedang dikerjakan, klik **File** lalu klik **Simpan**. Gunakan panah **Kembali** untuk kembali ke aplikasi.

6. Tekan **F5** atau klik tombol Putar untuk menjalankan aplikasi. Masukkan nilai kode yang Anda salin sebelumnya dan tekan **Tab** untuk mengalihkan fokus dari kotak teks. Tombol **Check In** harus diaktifkan.

7. Tekan tombol **Check In**. Hal berikut akan terjadi:

   * **Waktu Mulai Aktual** diatur ke tanggal dan waktu saat ini
   
   * Tombol **Check In** dinonaktifkan
   
   * Tombol **Check Out** diaktifkan

8. Tekan tombol **Check Out**.

   * **Waktu Selesai Aktual** diatur ke tanggal dan waktu saat ini
   
   * Kedua tombol dinonaktifkan

9. Kosongkan isi kotak pencarian.

10. Tekan **ESC** untuk keluar dari aplikasi yang sedang berjalan.

## <a name="task-6-add-visual-indicators"></a>Tugas \#6: Menambahkan indikator visual

Kegunaan aplikasi seluler meningkat secara signifikan ketika indikator visual disediakan. Dalam tugas ini, kami akan menambahkan ikon yang menunjukkan apakah pengunjung dapat check in atau check out.

1. Pilih tab **Sisipkan**

2. Pilih **Ikon \| Tambahkan**. Pilih Ikon. Pada titik ini tidak masalah ikon mana yang kita pilih karena kita ingin nilainya menjadi dinamis.

3. Mengubah ukuran dan menempatkan ikon di sebelah kiri tombol

4. Di tab Tingkat Lanjut untuk Ikon, pilih properti **Ikon** (di bagian Desain) dan masukkan ekspresi berikut

   ```
   If(
      CheckInButton.DisplayMode = DisplayMode.Disabled 
   && CheckOutButton.DisplayMode = DisplayMode.Disabled,
       Icon.EmojiFrown,
       Icon.EmojiSmile
   )
   ```

5. Untuk menyimpan pekerjaan yang sedang dikerjakan, klik **File** lalu klik **Simpan**. Gunakan panah **Kembali** untuk kembali ke aplikasi.

6. Tekan **F5** untuk menjalankan aplikasi. Masukkan nilai kode yang Anda salin sebelumnya dan tekan **Tab** untuk mengalihkan fokus dari kotak teks. Pastikan ikon menampilkan emoji cemberut.

7. Temukan nilai kode lain yang belum pernah digunakan sebelumnya (seharusnya tidak memiliki nilai Waktu Mulai Aktual atau Waktu Selesai Aktual). 

    > Anda dapat menavigasi ke tab sebelumnya untuk menyalin Kode lain dari salah satu Kunjungan yang telah Anda buat. Anda juga memiliki opsi untuk menjalankan aplikasi **Staf Kampus** yang dibuat sebelumnya untuk membuat catatan kunjungan baru. Pastikan ikon menampilkan emoji senyum untuk kode ini.

Aplikasi Anda yang sedang berjalan akan terlihat kira-kira seperti berikut:

![Kanvas menjalankan aplikasi keamanan](media/3-canvas-app-running.png)

8. Tekan **ESC** untuk keluar dari aplikasi yang sedang berjalan.

## <a name="task-7-publish-the-app"></a>Tugas #7: Menerbitkan aplikasi

1. Anda harus tetap membuka aplikasi Keamanan Kampus di browser Anda. Jika tidak, pilih aplikasi **Keamanan Kampus** dan klik **Edit**.

2. Pilih **File\| Terbitkan** 

3. Pilih **Terbitkan versi ini**

# <a name="challenges"></a>Tantangan

* Menghindari memasukkan kode kunjungan secara manual
* Menambahkan validasi bangunan untuk kunjungan
* Menambahkan validasi waktu aktual kunjungan vs waktu kunjungan yang dijadwalkan (terlalu dini, terlambat, dll)
* Tambahkan detail status kunjungan, misalnya tampilan email dan validasi untuk pengunjung, alasan penolakan akses gedung, dll
* Beberapa gedung/rapat/pemeriksaan selama satu kunjungan kampus. Misalnya, seseorang mungkin mengunjungi kampus selama sehari dan pada hari itu mereka akan bertemu dengan anggota staf di beberapa gedung pada waktu yang berbeda dalam sehari. Apakah Anda mempertimbangkan untuk membawa entitas *janji temu* ke dalam solusi?
