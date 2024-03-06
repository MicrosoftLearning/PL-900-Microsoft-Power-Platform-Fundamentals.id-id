---
lab:
  title: 'Lab 4: Cara membangun solusi otomatis'
  module: 'Module 4: Get Started with Power Automate'
---

# Lab 4: Cara membangun solusi otomatis

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberikan penyewa sebagai bagian dari pengiriman pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa tersedia untuk tujuan mendukung lab langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat perpanjangan. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab ini, Anda akan membuat alur Power Automate untuk mengirim email kepada pengunjung saat kunjungan dijadwalkan.

## Langkah-langkah lab tingkat tinggi

Berikut ini telah diidentifikasi sebagai persyaratan yang harus Anda terapkan untuk menyelesaikan proyek:

- Kontak perlu diberi tahu melalui email saat kunjungan dijadwalkan.

## Prasyarat

- Penyelesaian **Modul 1 Lab 0 - Memvalidasi lingkungan lab**
- Menyelesaikan **Modul 2 Lab 1 - Membuat Model Data**
- Penyelesaian **Modul 2 Lab 3 - Cara membuat aplikasi berbasis model**
- Kontak John Doe dibuat dengan alamat email pribadi yang diisi.

## Latihan 1: Membuat alur Pemberitahuan Kunjungan

**Tujuan:** Dalam latihan ini, Anda akan membuat alur Power Automate yang mengimplementasikan persyaratan. Pengunjung harus dikirimi email yang menyertakan kode unik yang ditetapkan ke kunjungan saat kunjungan dibuat.

### Tugas \#1: Membuat alur

1.  Navigasikan ke `https://make.powerapps.com`

2.  Anda mungkin perlu mengautentikasi ulang, pilih **Masuk** dan ikuti instruksi, jika diperlukan.

3.  **Pilih lingkungan Dev One** di kanan atas, jika belum dipilih.

4.  Di menu navigasi kiri, pilih **Alur**.

5.  Jika diminta, pilih **Mulai**.

6.  Pilih **+ Alur** baru dan pilih **Alur** cloud otomatis.

7.  Masukkan `Visit Notification` untuk **Nama** alur.

8.  Di **Pilih pemicu** alur Anda, cari `Dataverse`

9.  Pilih pemicu **Saat baris ditambahkan, dimodifikasi, atau dihapus**, lalu pilih **Buat**.

10.  Isi kondisi pemicu untuk alur:

    1.  Pilih **Ditambahkan** untuk **Ubah jenis**

    2.  Pilih **Kunjungan** untuk **Nama tabel**

    3.  Pilih **Organisasi** untuk **Cakupan**

    4.  Pada langkah pemicu, pilih elipsis (**...**) dan pilih **Ganti Nama**. Mengganti nama langkah pemicu `When a Visit is added` 

        Ini adalah praktik yang baik, sehingga Anda dan editor alur lainnya dapat memahami tujuan dari langkah tersebut tanpa harus menyelami detailnya.


### Tugas \#2: Buat langkah untuk mendapatkan baris pengunjung

1.  Pilih **+ Langkah baru**. Langkah ini akan mengambil informasi Pengunjung, termasuk alamat email.

2.  Cari `Dataverse`

3.  Pilih tindakan **Dapatkan baris berdasarkan ID**.

4.  Pilih **Kontak** sebagai **Nama tabel**

5.  Pilih bidang **ID Baris**. Perhatikan bahwa jendela muncul untuk memilih **Konten** atau **Ekspresi** dinamis.

6.  **Di bidang ID** Baris, pilih **Pengunjung (Nilai)** dari **daftar Konten** dinamis. Dalam langkah ini, Anda mencari Kontak untuk baris Kunjungan yang dibuat untuk memicu alur ini. Karena alamat email adalah bagian dari tabel Kontak, Anda akan memerlukan informasi ini untuk mengirim email ke pengunjung.

7.  **Pada tindakan Dapatkan baris menurut ID**, pilih elipsis (**...**) dan pilih **Ganti Nama**. Ganti nama tindakan ini `Get the Visitor`
 
    Ini adalah praktik yang baik, sehingga Anda dan editor alur lainnya dapat memahami tujuan dari langkah tersebut tanpa harus menyelami detailnya.


### Tugas \#3: Buat langkah untuk mengirim email ke pengunjung

1.  Pilih **+ Langkah baru**. Ini adalah langkah yang akan mengirim email ke pengunjung.

2.  Cari `mail`, pilih **tindakan Kirim email (V2)** dari **konektor Office 365 Outlook** .

3.  Jika diminta untuk menerima syarat dan ketentuan untuk menggunakan tindakan ini, pilih **Terima**.

4.  Pilih **Tambahkan konten dinamis** di bagian bidang **Kepada**. 
    
5.  Pilih **Email** dari daftar konten Dinamis.

    > Perhatikan bahwa ini berada di bawah header **Dapatkan Pengunjung**. Ini berarti Anda memilih Email yang terkait dengan Pengunjung yang Anda cari di langkah sebelumnya.

7.  **Di bidang Subjek**, masukkan`Your scheduled visit to Bellows College`

8.  Masukkan teks berikut di **Isi Email**:

    > Konten dinamis perlu ditempatkan di tempat bidang diberi nama dalam tanda kurung. Disarankan untuk menyalin & menempel semua teks terlebih dahulu dan kemudian menambahkan konten dinamis di tempat yang benar.

    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    Dear {First Name},

    You are currently scheduled to visit Bellows Campus from {Scheduled Start} until {Scheduled End}.

    Best regards,

    Campus Administration
    Bellows College
    ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

8.  Sorot teks **{First Name}**. Ganti dengan bidang **Nama Depan** dari langkah **Dapatkan Pengunjung**.

9.  Sorot teks **{Scheduled Start}**. Ganti dengan bidang **Mulai Terjadwal** dari langkah **Saat kunjungan ditambahkan**.

10.  Sorot teks **{Scheduled End}**. Ganti dengan bidang **Jadwal Akhir** dari langkah **Saat kunjungan ditambahkan**.

11.  Pilih **Simpan**.

Biarkan tab alur ini terbuka untuk tugas berikutnya. Alur Anda akan terlihat kira-kira seperti berikut:

![Contoh langkah aliran](media/4-Flow.png)


### Tugas \#4: Memvalidasi dan menguji alur

1.  Buka tab baru di browser Anda dan navigasikan ke `https://make.powerapps.com`

2.  **Pilih lingkungan Dev One** di kanan atas, jika belum dipilih.

3.  Pilih **Aplikasi** dan buka **aplikasi berbasis model Bellows Campus Management** yang Anda buat sebelumnya.

3.  Dengan membiarkan tab browser ini terbuka, navigasikan kembali ke tab sebelumnya dengan alur Anda.

4.  Pada bilah perintah, pilih **Uji**. Pilih **Secara Manual** lalu pilih **Uji**.

5.  Navigasikan ke tab browser dengan aplikasi berbasis model Anda terbuka. 

6.  Menggunakan navigasi peta situs di sebelah kiri, pilih **Kunjungan**.

6.  Pilih tombol **+ Baru** untuk menambahkan rekaman Kunjungi** baru**.

7.  Lengkapi catatan Kunjungan sebagai berikut:

    -   **Nama**: `Test Visit`

    -   **Pengunjung:** John Doe

    -   **Jadwal Mulai:** Besok pukul 08.00

    -   **Jadwal Berakhir:** Besok pukul 09.00

8.  Pilih tombol **Simpan & Tutup** .

9.  Navigasikan ke tab browser tempat pengujian Alur Anda berjalan. Setelah penundaan singkat, Anda akan melihat alur berjalan. Di sinilah Anda dapat menangkap masalah apa pun dalam alur atau mengonfirmasi bahwa alur berhasil dijalankan.

    Setelah beberapa saat, Anda akan melihat email di kotak masuk, karena Anda mengisi email John Doe sebagai email pribadi. Perhatikan bahwa email mungkin masuk ke folder Email Sampah Anda.


## Latihan

- Bereksperimenlah dengan pemformatan pada email. Bagaimana anda bisa membuatnya terlihat lebih profesional?


