---
lab:
  title: 'Lab 4: Cara membangun solusi otomatis'
  module: 'Module 4: Get Started with Power Automate'
---

# <a name="lab-4-how-to-build-an-automated-solution"></a>Lab 4: Cara membangun solusi otomatis

## <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab ini, Anda akan membuat alur Power Automate untuk mengirim email kepada pengunjung saat kunjungan dijadwalkan.

## <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Berikut ini telah diidentifikasi sebagai persyaratan yang harus Anda terapkan untuk menyelesaikan proyek:

- Kontak perlu diberi tahu melalui email saat kunjungan dijadwalkan.

## <a name="prerequisites"></a>Prasyarat

- Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**
- Menyelesaikan **Modul 2 Lab 1 - Membuat Model Data**
- Penyelesaian **Modul 2 Lab 3 - Cara membuat aplikasi berbasis model**
- Kontak John Doe dibuat dengan alamat email pribadi yang diisi

## <a name="exercise-1-create-visit-notification-flow"></a>Latihan 1: Membuat alur Pemberitahuan Kunjungan

**Tujuan:** Dalam latihan ini, Anda akan membuat alur Power Automate yang mengimplementasikan persyaratan. Pengunjung harus dikirimi email yang menyertakan kode unik yang ditetapkan ke kunjungan saat kunjungan dibuat.

### <a name="task-1-create-a-flow"></a>Tugas \#1: Buat alur

1.  Navigasikan ke <https://make.powerapps.com>. Anda mungkin perlu mengautentikasi ulang - klik **Masuk** dan ikuti petunjuk jika diperlukan.

2.  Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

3.  Di menu navigasi kiri, pilih **Alur**.

4.  Jika diminta, pilih **Mulai**.

5.  Klik **Alur baru** dan pilih **Alur cloud otomatis**.

6.  Masukkan "Kunjungi Pemberitahuan" untuk **nama Flow**.

7.  Di **Pilih pemicu alur Anda**, cari **Dataverse**.

8.  Pilih pemicu **Bila baris ditambahkan, diubah, atau dihapus**, lalu klik **Buat**.

9.  Isi kondisi pemicu untuk alur:

    1.  Pilih **Ditambahkan** untuk **Ubah jenis**

    2.  Pilih **Kunjungan** untuk **Nama tabel**

    3.  Pilih **Organisasi** untuk **Cakupan**

    4.  Pada langkah pemicu, klik elipsis ( **...** ) dan klik **Ganti nama**. Ganti nama pemicu ini **"Saat kunjungan ditambahkan"** . Ini adalah praktik yang baik, sehingga Anda dan editor alur lainnya dapat memahami tujuan dari langkah tersebut tanpa harus menyelami detailnya.

### <a name="task-2-create-a-step-to-get-the-visitor-row"></a>Tugas \#2: Membuat langkah untuk mendapatkan baris pengunjung

1.  Pilih **+ Langkah baru**. Langkah ini diperlukan untuk mengambil informasi pengunjung, termasuk alamat email.

2.  Cari **Dataverse**.

3.  Pilih tindakan **Dapatkan baris berdasarkan ID**.

4.  Pilih **Kontak** sebagai **Nama tabel**

5.  Pilih bidang **ID Baris**. Perhatikan bahwa jendela muncul untuk memilih Konten atau Ekspresi dinamis.

6.  Di bidang **ID Baris**, pilih **Pengunjung (Nilai)** dari daftar konten Dinamis. Dalam langkah ini, Anda mencari Kontak untuk baris Kunjungan yang dibuat untuk memicu alur ini. Karena alamat email adalah bagian dari tabel Kontak, Anda akan memerlukan informasi ini untuk mengirim email ke pengunjung.

7.  Pada tindakan ini, klik elipsis ( **...** ) dan klik **Ganti nama**.
        Ganti nama tindakan ini **"Dapatkan Pengunjung"** . Ini adalah praktik yang baik, sehingga Anda dan editor alur lainnya dapat memahami tujuan dari langkah tersebut tanpa harus menyelami detailnya.

### <a name="task-3-create-a-step-to-send-an-email-to-the-visitor"></a>Tugas \#3: Membuat langkah untuk mengirim email ke pengunjung

1.  Klik **+ Langkah baru**. Ini adalah langkah yang akan mengirim email ke pengunjung.

2.  Cari *email*, pilih konektor **Office 365 Outlook** dan tindakan **Kirim email (V2)** .

3.  Jika diminta untuk Menerima persyaratan dan ketentuan untuk menggunakan tindakan ini, klik **Terima**.

4.  Pilih **Tambahkan konten dinamis** di bagian bidang **Kepada**. 
    
5.  Pilih **Email** dari daftar konten Dinamis.
        > Notice that it is beneath the **Get the visitor** header. This means you
        are selecting the Email that is related to the Visitor that you looked
        up in the previous step.

6.  Masukkan **Kunjungan terjadwal Anda ke Bellows College** di bidang **Subjek**.

7.  Masukkan teks berikut di **Isi Email**:

>   Konten dinamis perlu ditempatkan di tempat bidang diberi nama dalam tanda kurung. Disarankan untuk menyalin & menempel semua teks terlebih dahulu dan kemudian menambahkan konten dinamis di tempat yang benar.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
   Dear {First Name},

   You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

   Best regards,

   Campus Administration
   Bellows College
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Sorot teks **{First Name}** . Ganti dengan bidang **Nama Depan** dari langkah **Dapatkan Pengunjung**.

9.  Sorot teks **{Scheduled Start}** . Ganti dengan bidang **Mulai Terjadwal** dari langkah **Saat kunjungan ditambahkan**.

10.  Sorot teks **{Scheduled End}** . Ganti dengan bidang **Jadwal Akhir** dari langkah **Saat kunjungan ditambahkan**.

11.  Klik **Simpan**.

Biarkan tab alur ini terbuka untuk tugas berikutnya. Alur Anda akan terlihat kira-kira seperti berikut:

![Contoh langkah alur.](media/4-Flow.png)

### <a name="task-4-validate-and-test-the-flow"></a>Tugas \#4: Memvalidasi dan menguji alurnya

1.  Buka tab baru di browser Anda dan navigasikan ke <https://make.powerapps.com>.

2.  Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

3.  Klik **Aplikasi** dan pilih aplikasi berbasis model, **Bellows Campus Management**, yang Anda buat sebelumnya.

3.  Dengan membiarkan tab browser ini terbuka, navigasikan kembali ke tab sebelumnya dengan alur Anda.

4.  Pada bilah perintah, klik **Uji**. Pilih **Secara Manual** lalu klik **Uji**.

5.  Navigasikan ke tab browser dengan aplikasi berbasis model Anda terbuka. 

6.  Di menu navigasi sebelah kiri, pilih **Kunjungan**

6. Tekan tombol **+ Baru** untuk menambahkan data **Kunjungan** baru.

7. Lengkapi catatan Kunjungan sebagai berikut:

    -   **Nama:** Kunjungan Pengujian

    -   **Pengunjung:** John Doe

    -   **Jadwal Mulai:** Besok pukul 08.00

    -   **Jadwal Selesai:** Besok pukul 09.00

8. Pilih tombol **Simpan dan Tutup**.

9. Navigasikan ke tab browser dengan pengujian alur Anda berjalan. Setelah penundaan singkat, Anda akan melihat alur berjalan. Di sinilah Anda dapat menangkap masalah apa pun dalam alur atau mengonfirmasi bahwa alur berhasil dijalankan.

Setelah beberapa saat, Anda akan melihat email di kotak masuk, karena Anda mengisi email John Doe sebagai email pribadi. Perhatikan bahwa email mungkin masuk ke folder Email Sampah Anda.

## <a name="challenges"></a>Tantangan

- Coba ubah pemformatan pada email. Bagaimana cara membuatnya terlihat lebih profesional?