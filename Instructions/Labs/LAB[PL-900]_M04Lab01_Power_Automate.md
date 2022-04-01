---
lab:
  title: 'Lab 6: Cara membangun solusi otomatis'
  module: 'Module 4: Get Started with Power Automate'
ms.openlocfilehash: 9b26af0345e67d338409a3712fd77e581721ab29
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898998"
---
# <a name="module-4-get-started-with-power-automate"></a>Modul 4: Memulai dengan Power Automate
## <a name="lab-how-to-build-an-automated-solution"></a>Lab: Cara membangun solusi otomatis

## <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus. 

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus. 

Di lab ini, Anda akan membuat alur Power Automate untuk mengotomatiskan berbagai bagian manajemen kampus. 

# <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Berikut ini telah diidentifikasi sebagai persyaratan yang harus Anda terapkan untuk menyelesaikan proyek:

* Kode unik yang diberikan kepada setiap pengunjung harus tersedia bagi mereka sebelum kunjungan mereka.
* Personel keamanan perlu menerima pemberitahuan tentang pengunjung yang melebihi batas waktu yang dijadwalkan.

## <a name="prerequisites"></a>Prasyarat

* Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**
* Penyelesaian **Modul 2 Lab 1 - Pengantar Microsoft Dataverse**
* Aplikasi Staf Kampus dibuat di **Modul 3 Lab 2 – Cara membuat aplikasi kanvas, bagian 2** (untuk pengujian)
* Kontak John Doe dibuat dengan alamat email pribadi di **Modul 3 Lab 4 - Cara membuat aplikasi berbasis model** (untuk pengujian)

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai

-   Apa mekanisme distribusi yang paling tepat untuk kode pengunjung?
-   Bagaimana perpanjangan dapat diukur dan kebijakan yang ketat dapat ditegakkan?

# <a name="exercise-1-create-visit-notification-flow"></a>Latihan \#1: Membuat alur Pemberitahuan Kunjungan

**Tujuan:** Dalam latihan ini, Anda akan membuat alur Power Automate yang mengimplementasikan persyaratan. Pengunjung harus dikirimi email yang menyertakan kode unik yang ditetapkan untuk kunjungan.

## <a name="task-1-create-flow"></a>Tugas \#1: Membuat alur

1.  Buka solusi Manajemen Kampus Anda.

    -   Masuk ke <https://make.powerapps.com>

    -   Pilih **lingkungan** Anda.

    -   Pilih **Solusi**.

    -   Klik untuk membuka solusi **Manajemen Kampus** Anda.

2.  Klik **Baru** dan pilih **Otomatis**, **Alur cloud**, lalu **Otomatis**. Tindakan ini akan membuka editor alur Power Automate di jendela baru.

3. Di **Pilih pemicu alur Anda**, cari **Microsoft Dataverse**.

4. Pilih pemicu **Bila baris ditambahkan, diubah, atau dihapus**, lalu klik **Buat**.

   * Pilih **Ditambahkan** untuk **Ubah jenis**
   
   * Pilih **Kunjungan** untuk **Nama tabel**
   
   * Pilih **Organisasi** untuk **Cakupan**
   
   * Pada langkah pemicu, klik elipsis ( **...** ) dan klik **Ganti nama**. Ganti nama pemicu ini **"Saat kunjungan ditambahkan"** . Ini adalah praktik yang baik, sehingga Anda dan editor alur lainnya dapat memahami tujuan dari langkah tersebut tanpa harus menyelami detailnya.

5. Pilih **Langkah Baru**. Langkah ini diperlukan untuk mengambil informasi pengunjung, termasuk alamat email.

6. Cari **Microsoft Dataverse**.

7. Pilih tindakan **Dapatkan baris menurut ID**. 

   * Pilih **Kontak** sebagai **Nama tabel**
   
   * Di bidang **ID Baris**, pilih **Pengunjung (Nilai)** dari daftar konten Dinamis.
   
   * Pada tindakan ini, klik elipsis ( **...** ) dan klik **Ganti nama**. Ganti nama tindakan ini **"Dapatkan Pengunjung"** . Ini adalah praktik yang baik, sehingga Anda dan editor alur lainnya dapat memahami tujuan dari langkah tersebut tanpa harus menyelami detailnya.

8. Klik **Langkah Baru**. Ini adalah langkah yang akan membuat dan mengirim email ke pengunjung.

9. Cari *email*, pilih konektor **Office 365 Outlook** dan tindakan **Kirim email (V2)** .

   * Jika diminta untuk Menerima persyaratan dan ketentuan untuk menggunakan tindakan ini, klik **Terima**.
   
   * Pilih bidang **Ke**, pilih **Email** dari daftar konten Dinamis. Perhatikan bahwa ini berada di bawah header **Dapatkan Pengunjung**. Ini berarti Anda memilih Email yang terkait dengan Pengunjung yang Anda cari di langkah sebelumnya. 

   * Masukkan **Kunjungan terjadwal Anda ke Bellows College** di bidang **Subjek**.

   * Masukkan teks berikut di **Isi Email**:  
        
        > Konten dinamis perlu ditempatkan di tempat bidang diberi nama dalam tanda kurung. Disarankan untuk menyalin & menempel semua teks terlebih dahulu dan kemudian menambahkan konten dinamis di tempat yang benar.
   
        ```
        Dear {First Name},

        You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

        Your security code is {Code}, please do not share it. You will be required to produce this code during your visit.

        Best regards,

        Campus Administration
        Bellows College
        ```
   
10.  Pilih nama alur **Tanpa Judul** di bagian atas dan ganti namanya menjadi `Visit notification`

11. Tekan **Simpan**

    Biarkan tab alur ini terbuka untuk tugas berikutnya. Alur Anda akan terlihat kira-kira seperti berikut:

![gambar](https://user-images.githubusercontent.com/78555251/118340724-ccb13300-b4d9-11eb-96c2-c7b005bb9ac0.png)

## <a name="task-2-validate-and-test-the-flow"></a>Tugas \#2: Memvalidasi dan menguji alurnya

1.  Buka tab baru di browser Anda dan navigasikan ke <https://make.powerapps.com>

2.  Klik **Aplikasi** dan pilih aplikasi **Staf Kampus** yang Anda buat

3.  Dengan membiarkan tab ini terbuka, navigasikan kembali ke tab sebelumnya dengan alur Anda. 

4.  Pada bilah perintah, klik **Uji**. Pilih **Secara Manual** lalu **Simpan & Uji**.

5.  Dengan membiarkan tab alur terbuka, navigasikan kembali ke tab sebelumnya dengan aplikasi **Staf Kampus**.

6.  Tekan **+** untuk menambahkan catatan Kunjungan baru

7.  Masukkan **John Doe** sebagai **Nama** dan pilih **Gedung**

8.  Pilih **John Doe** sebagai **Pengunjung**

9.  Pilih **Waktu Mulai yang Dijadwalkan** dan **Waktu Selesai yang Dijadwalkan** untuk tanggal mana pun di masa mendatang.

10.  Tekan ikon **Tanda Centang** untuk menyimpan kunjungan baru

11.  Navigasikan kembali ke tab sebelumnya dengan alur yang sedang diuji. Perhatikan saat alur dijalankan. Jika ada kesalahan, kembali dan bandingkan alur Anda dengan contoh di atas. Jika email berhasil dikirim, Anda akan menerimanya di kotak masuk Anda. 

12.  Klik panah kembali pada bilah perintah

13.  Di bagian **Detail**, perhatikan bahwa **Status** diatur ke **Aktif**. Ini berarti alur Anda akan berjalan setiap kali Kunjungan baru dibuat, sampai Anda mematikannya. Setiap kali alur berjalan, Anda akan melihatnya ditambahkan ke daftar **riwayat proses 28 hari**.

14.  Matikan alur dengan mengklik **Matikan** pada bilah perintah. Anda mungkin perlu menekan elipsis ( **...** ) untuk melihat opsi ini.

15.  Tutup jendela ini.

# <a name="exercise-2-create-security-sweep-flow"></a>Latihan #2: Membuat alur Pembersihan Keamanan

**Tujuan:** Dalam latihan ini, Anda akan membuat alur Power Automate yang mengimplementasikan persyaratan. Pembersihan keamanan perlu dilakukan setiap 15 menit, dan keamanan harus diberitahu jika ada pengunjung yang melebihi waktu yang dijadwalkan.

## <a name="task-1-create-flow-to-retrieve-records"></a>Tugas 1: Membuat alur untuk mengambil catatan

1. Buka solusi Manajemen Kampus Anda.

   -   Masuk ke <https://make.powerapps.com>

   -   Pilih **Lingkungan** Anda.

   -   Pilih **Solusi**.

   -   Klik untuk membuka solusi **Manajemen Kampus** Anda.

2. Klik **Baru** dan pilih **Otomatisasi**, **Alur cloud**, lalu **Terjadwal**. Tindakan ini akan membuka editor alur Power Automate di jendela baru.

3. Atur alur agar berulang setiap **15** menit.

4. Klik **Buat**.

5. Klik **Langkah baru**. Cari *Saat ini* dan pilih konektor **Microsoft Dataverse**. Pilih tindakan **Daftar baris**.

   * Masukkan **Kunjungan** sebagai **Nama tabel**
   
   * Klik **Tampilkan opsi tingka lanjut**

   * Masukkan ekspresi berikut sebagai **Filter baris**

   ```
     statecode eq 0 and bc_actualstart ne null and bc_actualend eq null and Microsoft.Dynamics.CRM.OlderThanXMinutes(PropertyName='bc_scheduledend',PropertyValue=15)
   ```
   
   * Untuk memecahnya:
       * **statecode eq 0** memfilter kunjungan aktif (dengan Status sama dengan Aktif)
       * **bc_actualstart ne null** membatasi pencarian pada kunjungan yang memiliki nilai Waktu Mulai Aktual, yaitu ada check-in
       * **bc_actualend eq null** membatasi pencarian pada kunjungan yang tidak ada check out (Actual End tidak memiliki nilai) 
       * **Microsoft.Dynamics.CRM.OlderThanXMinutes(PropertyName='bc_scheduledend',PropertyValue=15)** membatasi kunjungan yang seharusnya diselesaikan lebih dari 15 menit yang lalu.

   * Pada tindakan ini, klik elipsis ( **...** ) dan klik **Ganti nama**. Ganti nama tindakan ini **"Daftar kunjungan aktif yang berakhir lebih dari 15 menit yang lalu"** . Ini adalah praktik yang baik, sehingga Anda dan editor alur lainnya dapat memahami tujuan dari langkah tersebut tanpa harus menyelami detailnya.

6.  Klik **Langkah baru**. Cari *Terapkan*, pilih **Terapkan ke setiap** tindakan 

7.  Pilih **nilai** dari konten dinamis di bidang **Pilih output dari langkah sebelumnya**. Perhatikan bahwa ini berada di bawah header abu-abu **Daftar kunjungan aktif yang berakhir lebih dari 15 menit yang lalu**. Ini berarti Anda memilih daftar kunjungan yang Anda cari di langkah sebelumnya. 

8.  Ambil data Gedung untuk catatan terkait

    * Klik **Tambahkan tindakan** di dalam Terapkan ke Setiap perulangan.
    
    * Pilih **Microsoft Dataverse**. 
    
    * Pilih tindakan **Dapatkan baris menurut ID**.
    
    * Pilih **Gedung** sebagai **Nama tabel**
    
    * Pilih **Gedung (Nilai)** sebagai **ID Baris** dari konten Dinamis
    
    * Klik **...** di samping **Dapatkan catatan**, pilih **Ganti nama**. Masukkan **Dapatkan bangunan** sebagai nama langkah
    
9.  Mengambil data Pengunjung untuk catatan terkait

    * Klik **Tambahkan tindakan** di dalam Terapkan ke Setiap perulangan.
    
    * Pilih **Microsoft Dataverse**.
    
    * Pilih tindakan **Dapatkan baris menurut ID**.
    
    * Pilih **Kontak** sebagai **Nama tabel**
    
    * Pilih **Pengunjung (Nilai)** sebagai **ID Baris** dari konten Dinamis
    
    * Klik **...** di samping **Dapatkan catatan**, pilih **Ganti nama**. Masukkan **Dapatkan pengunjung** sebagai nama langkah
    
10.  Mengirim Pemberitahuan Email

     * Klik **Tambahkan tindakan** di dalam Terapkan ke Setiap perulangan. Tambahkan tindakan **Kirim email (V2)** dari koneksi **Office 365 Outlook**.

11.  Masukkan alamat email Anda sebagai **Kepada**

12.  Masukkan hal berikut ini di bidang **Subjek**. **Nama Lengkap** adalah konten dinamis dari langkah **Dapatkan pengunjung**.

   ```
   {Full Name} overstayed their welcome
   ```
   
13.  Masukkan hal berikut ini di bidang **Isi**. **Nama** adalah konten dinamis dari langkah **Dapatkan bangunan**. Anda mungkin perlu menggulir ke bagian bawah daftar.

   ```
   There is an overstay in building {Name}.
         
   Best,
         
   Campus Security
   ```

14.  Pilih nama alur **Tanpa Judul** di sudut kiri atas dan ganti namanya menjadi **Security Sweep**

15.  Tekan **Simpan**

    Alur Anda akan terlihat kira-kira seperti berikut:

![Pembersihan keamanan alur terjadwal bagian 1](media/4-power-automate-security-sweep-flow.png)

## <a name="task-2-validate-and-test-the-flow"></a>Tugas #2: Memvalidasi dan menguji alurnya

Alur Anda akan mulai mengirimi Anda email (ke email yang Anda tentukan saat membuat kontak John Doe sebelumnya) jika ada kunjungan yang memenuhi persyaratan yang ditetapkan dalam alur.

1. Validasi bahwa Anda memiliki catatan kunjungan yang:

   1. Memiliki status aktif
   
   2. Akhir yang Dijadwalkan sudah lewat (lebih dari 15 menit)
   
   3. Waktu Mulai Aktual memiliki nilai.
   
   > **Catatan**: Untuk melihat data ini, navigasikan ke make.powerapps.com di tab baru. Klik Solusi di panel kiri untuk menemukan solusi Anda. Pilih entitas Kunjungan, lalu pilih tab Data. Klik Kunjungan Aktif di sudut kanan atas untuk menampilkan pemilih tampilan, lalu pilih Semua bidang.
   
2. Navigasikan ke alur **Pembersihan Keamanan** Anda, jika belum ada di sana.

3. Saat alur Anda terbuka, klik **Uji**.

4. Pilih **Secara Manual**.

5. Klik **Simpan & Uji** dan **Jalankan Alur**.

6. Saat alur bersaing, klik **Selesai**. 

7. Luaskan **Terapkan ke masing-masing**, lalu luaskan langkah **Kirim pemberitahuan email**. Periksa nilai **Subjek**, **Isi Email**.

8. Pilih panah kembali ke detail alur Pembersihan Keamanan. Pilih **Matikan** pada bilah perintah. Hal ini untuk mencegah alur dari mengeksekusi pada jadwal pada sistem pengujian.

# <a name="challenges"></a>Tantangan

* Tambahkan Waktu Mulai Aktual dan Waktu Selesai Terjadwal ke isi email.
* Bagaimana Anda bisa memastikan pemformatan tanggal yang ramah pengguna digunakan di isi email?
* Apakah mungkin untuk membuat tabel dengan informasi perpanjangan dan hanya mengirim satu email?
* Bisakah Anda membuat kode batang untuk kode kunjungan? Kapan hal ini akan berguna?
