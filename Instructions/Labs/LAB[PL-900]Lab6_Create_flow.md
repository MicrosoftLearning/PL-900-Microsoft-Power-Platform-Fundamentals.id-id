---
lab:
  title: 'Lab 6: Membuat alur Power Automate'
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Automate'
  module: 'Module 2: Build a Microsoft Power Automate flow'
---

## Tujuan pembelajaran

Dalam latihan ini, pelajar akan membuat serangkaian alur cloud yang berbeda menggunakan Microsoft Copilot di Power Automate. Anda akan menggunakan metode pembuatan yang berbeda seperti Copilot dan dari awal agar terbiasa dengan berbagai opsi yang tersedia.

Setelah berhasil menyelesaikan latihan ini, Anda akan:

- Menggunakan perintah bahasa alami untuk merancang alur kerja
- Mengonfigurasi pemicu dan tindakan
- Uji otomatisasi untuk penggunaan praktis.

### Skenario

Contoso Consulting adalah organisasi layanan profesional yang berspesialisasi dalam layanan konsultasi IT dan AI. Sepanjang tahun, mereka menawarkan banyak acara yang berbeda kepada pelanggan mereka. Beberapa di antaranya adalah acara gaya pameran dagang di mana mereka memiliki banyak mitra masuk dan memberikan detail tentang produk baru, tren pasar, dan layanan. Yang lain terjadi sepanjang tahun dan merupakan webinar cepat yang digunakan untuk memberikan detail tentang masing-masing produk. Selain itu, Contoso mulai menggunakan Agen otomatis untuk membantu pelanggan dengan pertanyaan.

Contoso ingin menggunakan Power Automate untuk membangun alur konfirmasi pendaftaran yang akan mengirim email otomatis ke pelanggan saat mereka mendaftar untuk suatu acara. 

Dalam latihan ini Anda akan membangun serangkaian alur Power Automate berdasarkan kriteria tertentu.

Sebelum memulai latihan ini, Anda harus telah menyelesaikan lab berikut:

- **Lab 2 – Membuat model data**
- **Lab 5 – Membangun aplikasi berbasis model**

Perkiraan waktu untuk menyelesaikan latihan ini adalah 20 hingga 30 menit.

## Latihan 1: Membuat alur pemberitahuan Pendaftaran Sesi

Dalam latihan pertama ini, Anda akan membangun alur yang akan berjalan secara otomatis ketika Pendaftaran Sesi baru dibuat. Ini akan mendapatkan detail sesi, acara, dan kontak siapa yang mendaftar dan mengirim email ke ini dengan detail pendaftaran mereka.

### Tugas 1: Membuat alur

Kami ingin mengirim konfirmasi pendaftaran kepada pengguna yang baru terdaftar. Kami akan membuat alur yang akan mengambil detail pendaftaran dan mengirim email konfirmasi ke pengguna terdaftar.

1. Buka [https://make.powerautomate.com](https://make.powerautomate.com/).

1. Anda mungkin perlu mengautentikasi ulang, pilih **Masuk** dan ikuti instruksi, jika diperlukan.

1. Pilih lingkungan **Dev One** di kanan atas jika belum dipilih. (Penting, lupakan untuk melakukan langkah ini).

1. Di navigasi kiri, pilih **+ Buat**. (Jika diminta, pilih **Memulai**.)

1. Pilih  **Alur** cloud otomatis.

1. Masukkan `Registration Notification` untuk **Nama** alur.

1. Di **Pilih pemicu** alur Anda, cari `Dataverse`.

1. Pilih pemicu **Saat baris ditambahkan, dimodifikasi, atau dihapus**, lalu pilih **Buat**.

    Jika Anda melihat kesalahan Parameter** Tidak **Valid, ini karena Anda belum mengautentikasi. Ikuti langkah-langkah di bawah ini untuk membuat koneksi. 
    - Pilih **Ubah Koneksi**.
    - Pilih **Tambahkan baru**.
    - **Di bidang Nama** koneksi, masukkan **Administrator** MOD. **Biarkan Jenis** autentikasi sebagai **OAuth**, dan Pilih **Masuk**.
    - Setelah masuk, pindah ke **Langkah 9.** 

1. Isi kondisi pemicu untuk alur:

    - Pilih **Ditambahkan** untuk **Ubah jenis**
    - Pilih **Pendaftaran** Sesi untuk **Nama tabel.**
    - Pilih **Organisasi** untuk **Cakupan** Pada langkah pemicu. 

1. Ganti nama langkah `When a Session Registration is added`pemicu .

    ![Cuplikan layar saat sesi ditambahkan konfigurasi pemicu](media/power-automate-01.png)

Ini adalah praktik yang baik, sehingga Anda dan editor alur lainnya dapat memahami tujuan langkah tanpa harus menyelami detailnya.


### Tugas 2: Buat langkah untuk mendapatkan detail Sesi Peristiwa tempat Pendaftaran.

1. Pilih **+ Langkah baru**. 

1. Cari **Dapatkan baris menurut ID**. 

1. Pilih tindakan **Dapatkan baris berdasarkan ID**.

1. Pilih **Sesi** Peristiwa sebagai **Nama tabel**

1. Pilih bidang **ID Baris**. Perhatikan bahwa ikon muncul untuk memilih **Konten** atau **Ekspresi** dinamis.

1. **Di bidang ID** Baris, pilih **Sesi Peristiwa (Nilai)** dari **daftar Konten** dinamis. Dalam langkah ini, Anda mencari **Sesi** Peristiwa untuk **Pendaftaran** Sesi yang dibuat untuk memicu alur ini.

1. **Pada tindakan Dapatkan baris menurut ID**. Ganti nama tindakan ini `Get the Event Session`

    ![Cuplikan layar konfigurasi tindakan Dapatkan Sesi Peristiwa](media/power-automate-02.png)

    Selanjutnya, kita akan mendapatkan detail Acara tempat sesi berada.

1. **Di bawah langkah Dapatkan Sesi** Peristiwa, pilih **+ Sisipkan Tindakan.**

1. Cari **Dapatkan baris menurut ID**. 

1. Pilih tindakan **Dapatkan baris berdasarkan ID**.

1. Pilih **Peristiwa** sebagai **Nama tabel**

1. Pilih bidang **ID Baris**. Perhatikan bahwa ikon muncul untuk memilih **Konten** atau **Ekspresi** dinamis.

1. **Di bidang ID** Baris, pilih **Peristiwa (Nilai)** dari daftar Konten** dinamis**. Dalam langkah ini, Anda mencari **Peristiwa** untuk **Sesi** Peristiwa yang diambil di langkah sebelumnya.

1. **Pada tindakan Dapatkan baris menurut ID**. Ganti nama tindakan `Get the Event`ini .

    ![Cuplikan layar konfigurasi Dapatkan tindakan Peristiwa](media/power-automate-03a.png)

    Terakhir, kita akan mendapatkan detail orang yang terdaftar untuk sesi tersebut.

1. Di bawah Dapatkan Detail Peristiwa, atur pilih **Sisipkan Tindakan** baru.

1. Di bidang pencarian masukkan **Dapatkan baris menurut ID**.

1. Pilih **Dapatkan baris menurut ID**.

1. Pilih **Kontak** sebagai **Nama tabel**

1. Pilih bidang **ID Baris**. Perhatikan bahwa jendela muncul untuk memilih **Konten dinamis** atau **Ekspresi**.

1. **Di bidang ID** Baris, pilih **bidang Peserta (Nilai)** dari pemicu **Saat pendaftaran sesi ditambahkan** dari **daftar Konten dinamis**.

1. **Pilih teks Dapatkan baris menurut ID**, dan ganti nama tindakan `Get Participant Details`ini .

    ![Cuplikan layar konfigurasi tindakan Dapatkan Detail Peserta](media/power-automate-04a.png)

### Tugas 3: Buat langkah untuk mengirim email untuk mengonfirmasi pendaftaran sesi

1. **Di bawah langkah Dapatkan Detail** Peserta, pilih **Sisipkan Tindakan** baru.

1. Di bidang pencarian masukkan **Kirim email**.

1. Pilih **Kirim email (V2)**.

    Anda mungkin diminta untuk membuat koneksi ke outlook, jika demikian pilih tombol **Masuk** , dan masuk dengan **akun Administrator** Mod. 

    ![Cuplikan layar Layar Buat Koneksi](media/power-automate-05.png)

1. Tepat di atas **bidang Kepada** , pilih **ikon Gigi** . Dari menu yang muncul, pilih **Gunakan konten** dinamis.

    ![Cuplikan layar menggunakan Konten Dinamis](media/power-automate-06.png) 

1. Menggunakan Nilai dinamis, di **bidang Kepada** , pilih **Email** di **bawah Dapatkan Detail** Peserta.

    ![Cuplikan layar pengaturan bidang ke ke email peserta.](media/power-automate-07.png)

1. **Di bidang Subjek**, pastikan tertulis `Registration Confirmation`.

1. Masukkan teks berikut di **Isi Email**:

    > **Catatan:** Konten dinamis perlu ditempatkan di mana bidang dinamai dalam tanda kurung siku. Disarankan untuk menyalin & menempel semua teks terlebih dahulu dan kemudian menambahkan konten dinamis di tempat yang benar.

    *`Dear {First Name}, Thank you for registering for our upcoming session {Session Name} on {Event Date}. {Speaker} will be your speaker in this session. Your session is scheduled to last {Duration (Hours)}. Check out our other session at our {Event Name}.`*

    *`Best regards,`*

    *`Events Administration`*
    
    *`Contoso Consulting`*

    Selanjutnya, kita akan mengganti teks dalam tanda kurung dengan item yang diuraikan di bawah ini.

1. Sorot teks **{First Name}**. Ganti dengan **bidang Nama** Depan dari **langkah Dapatkan Detail** Peserta.

1. **Sorot teks {Nama Sesi}**. Ganti dengan **bidang Nama** Sesi dari **langkah Dapatkan Sesi** Peristiwa.

1. **Sorot teks {Event Date}**. Ganti dengan **bidang Tanggal** Peristiwa dari **langkah Dapatkan Detail** Peristiwa.

1. **Sorot teks {Speaker}**. Ganti dengan **bidang Pembicara (Nilai)** dari **langkah Dapatkan Sesi** Peristiwa.

1. **Sorot teks {Duration (Jam)}**. Ganti dengan **bidang Durasi (Jam)** dari **langkah Dapatkan Sesi** Peristiwa.

1. **Sorot teks {Nama Peristiwa}**. Ganti dengan **bidang Nama** Peristiwa dari **langkah Dapatkan Detail** Peristiwa.

    Langkah Anda yang telah selesai harus menyerupai gambar:

    ![Cuplikan layar email yang telah selesai](media/power-automate-08.png)

1. Pilih **Simpan**.

    Biarkan tab alur ini terbuka untuk tugas berikutnya. Alur Anda akan terlihat seperti berikut:

### Tugas 4: Masukkan beberapa data sampel

> **Catatan:** Jika Anda menyelesaikan Lab 5 – Membangun aplikasi berbasis model, Anda dapat melewati tugas ini dan berpindah langsung ke Tugas 5. 

1. Menggunakan navigasi di sebelah kiri, pilih **Aplikasi**.

1. Ubah aplikasi yang ditampilkan dari **Aplikasi** saya ke **Semua**.

1. Arahkan mouse ke **aplikasi Manajemen** Peristiwa dan pilih **ikon Putar** .

1. Menggunakan navigasi di sebelah kiri, pilih **Kontak**.

1. Pada bilah perintah, pilih tombol **+ Baru** .

1. **Di layar Kontak** Baru, konfigurasikan sebagai berikut:

    - **Nama Depan:** Suzanne

    - **Nama Belakang:** Diaz

    - **Jabatan Pekerjaan:** Insinyur

1. Di header formulir, pilih panah bawah di samping **Tipe** Kontak.

1. Atur **Jenis** Kontak ke **Pembicara**.
    ![Cuplikan layar memperlihatkan cara mengatur bidang Tipe Kontak pada formulir.](media/power-automate-09.png)

1. Pilih tombol **Simpan** untuk menyimpan kontak dan membiarkannya terbuka.

1. Pilih tombol **+ Baru**.

1. **Di layar Kontak** Baru, konfigurasikan sebagai berikut:

    - **Nama Depan:** Edgar

    - **Nama Belakang:** Swenson

    - **Jabatan Pekerjaan:** Arsitek

    - **Email:** Masukkan alamat email Anda (PENTING atau alur Anda tidak akan berjalan)

1. Di header formulir, pilih panah bawah di samping **Tipe** Kontak.

1. Atur **Tipe** Kontak ke **Peserta**.

1. Pilih tombol **Simpan &amp; Tutup**.

    Selanjutnya, kita akan menambahkan peristiwa baru.

1. Menggunakan navigasi di sebelah kiri, pilih **Peristiwa**.

1. Pada bilah perintah, pilih tombol **+ Baru** .

1. **Di layar Kejadian** Baru, konfigurasikan sebagai berikut:

    - **Nama Acara:** Konferensi musim semi.

    - **Tanggal Acara:** Tanggal besok.

    - **Peserta Maks:** 500

    - **Detail Acara:** Konferensi musim semi untuk menampilkan produk dan layanan terbaru dari vendor kami yang didukung.

    - **Jenis Acara:** Konferensi

    - **Lokasi:** Seattle

    - **Pendaftaran Diperlukan:** Ya/Benar

    ![Cuplikan layar formulir Peristiwa yang telah selesai. ](media/power-automate-10.png)

1. Pilih tombol **Simpan &amp; Tutup**.

    Selanjutnya, kita akan menambahkan sesi baru untuk Acara.

1. Menggunakan navigasi di sebelah kiri, pilih **Sesi** Peristiwa.

1. Pilih tombol **+ Baru**.

1. Konfigurasikan **Sesi** Peristiwa sebagai berikut:

    - **Nama Sesi:** AI yang bertanggung jawab

    - **Tanggal Sesi:** Tanggal Besok

    - **Durasi:** 1,5 Jam

    - **Deskripsi Sesi:** Dengan semua solusi AI baru, menjadi bertanggung jawab adalah penting. Kita akan membahas tantangannya.

    - **Pembicara:** Suzanne Diaz

    - **Acara:** Konferensi Musim Semi

    ![Cuplikan layar formulir sesi Peristiwa yang telah selesai. ](media/power-automate-11.png)

1. Pilih tombol **Simpan dan tutup** .

 
### Tugas 5: Memvalidasi dan menguji alur

1. Jika perlu, buka tab baru di browser Anda dan navigasi ke [https://make.powerapps.com](https://make.powerapps.com/). 

1. Pilih lingkungan **Dev One** di kanan atas jika belum dipilih.

1. Pilih **Aplikasi** dan buka **Aplikasi** Manajemen Peristiwa Contoso.

1. Dengan membiarkan tab browser ini terbuka, navigasikan kembali ke tab sebelumnya dengan alur Anda.

1. Pada bilah perintah, pilih **Uji**. Pilih **Secara Manual** lalu pilih **Uji**.

1. Navigasikan ke tab browser dengan aplikasi berbasis model Anda terbuka.

    Akhirnya, kita akan membuat **Pendaftaran** Sesi.

1. Menggunakan navigasi di sebelah kiri, pilih **Pendaftaran Sesi.**

1. Pada bilah **Perintah**, pilih **+ Baru**.

1. Selesaikan pendaftaran sesi sebagai berikut:

    - **Nama**: `E, Swenson Registration`.

    - **Tanggal Pendaftaran:** Tanggal Hari Ini

    - **Peserta:** `Edgar Swenson`

    - **Sesi:** `Responsible AI`

    ![Cuplikan layar formulir pendaftaran Sesi yang telah selesai. ](media/power-automate-12.png)

1. Pilih tombol Simpan dan Tutup **** .

1. Navigasikan ke tab browser tempat pengujian Alur Anda berjalan. Setelah penundaan singkat, Anda akan melihat alur berjalan. Di sinilah Anda dapat menangkap masalah apa pun dalam alur atau mengonfirmasi bahwa alur berhasil dijalankan.

Setelah penundaan singkat, Anda akan melihat email di kotak masuk Anda.

> **Catatan:** Ini mungkin masuk ke folder email Sampah Anda.
