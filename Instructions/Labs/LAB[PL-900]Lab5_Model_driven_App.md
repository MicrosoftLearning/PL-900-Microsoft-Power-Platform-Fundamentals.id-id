---
lab:
  title: 'Lab 5: Membuat aplikasi berbasis model'
  learning path: 'Learning Path: Demonstrate the capabilities of Microsoft Power Apps'
  module: 'Module 3: Build a model-driven app'
---
## Tujuan pembelajaran

Dalam latihan ini, pelajar akan membuat aplikasi berbasis model di Power Apps menggunakan Copilot. Anda akan menentukan model data, memodifikasi formulir dan tampilan, dan membuat aplikasi.

**Setelah berhasil menyelesaikan lab ini, Anda akan:**

-   Buat aplikasi berbasis Model.
-   Ubah formulir dan tampilan dalam aplikasi agar paling sesuai dengan kebutuhan Anda.
-   Navigasikan melalui aplikasi berbasis model.

### Skenario

Contoso Consulting adalah organisasi layanan profesional yang berspesialisasi dalam layanan konsultasi IT dan AI. Sepanjang tahun, mereka menawarkan banyak acara yang berbeda kepada pelanggan mereka. Beberapa di antaranya adalah acara gaya pameran dagang di mana mereka memiliki banyak mitra masuk dan memberikan detail tentang produk baru, tren pasar, dan layanan. Yang lain terjadi sepanjang tahun dan merupakan webinar cepat yang digunakan untuk memberikan detail tentang masing-masing produk.

Contoso ingin menggunakan Power Platform untuk membangun solusi Manajemen Peristiwa yang dapat mereka gunakan untuk mengelola berbagai peristiwa yang mereka host sepanjang tahun.

Dalam latihan ini Anda akan membangun aplikasi berbasis model untuk mengelola peristiwa Contoso. Aplikasi berbasis model akan didasarkan pada model data yang ada dan akan mencakup Peristiwa, Sesi Peristiwa, dan pendaftaran Sesi.

### Detail Lab:

Sebelum memulai latihan ini, Disarankan agar selesai:

-   **Lab 2– Membuat Solusi Power Platform**
-   **Lab 3– Membuat Model Data**

Perkiraan waktu untuk menyelesaikan latihan ini adalah **20 hingga 30** menit.

## Tugas 1: Buat Model untuk mendukung aplikasi berbasis Model baru Anda

Contoso saat ini menyimpan informasi kontak dalam instans Dataverse mereka, sehingga mereka ingin menggunakan Dataverse untuk melacak kursus dan pendaftaran kursus. Anda perlu membuat tabel yang diperlukan untuk mendukung aplikasi dan membangun aplikasi berbasis model berdasarkan model data tersebut.

1.  Jika perlu, buka browser web dan navigasikan ke [portal pembuat Power Apps](https://make.powerapps.com/) , dan Masuk menggunakan kredensial akun Microsoft Anda.
2.  Menggunakan navigasi di sebelah kiri, pilih **Solusi.**
3.  **Buka solusi Manajemen** Peristiwa yang Anda buat sebelumnya.
4.  Pada bilah **Perintah** pilih **Aplikasi** berbasis Model Aplikasi \> **** Baru.** \> **
5.  Pilih bagian **Buat** .
    -   **Nama:** Manajemen Peristiwa Contoso
    -   **Deskripsi:** Digunakan untuk mengelola Peristiwa dan Sesi Peristiwa.
6.  Pilih tombol ****Buat**.**
7.  Pilih tombol **Tambahkan Halaman** , pilih **Tabel Dataverse.**
8.  Pilih tabel berikut:
    -   Kontak
    -   Kejadian
    -   Sesi Acara
    -   Pendaftaran sesi
9.  Pastikan **Perlihatkan di navigasi** dipilih.

![Cuplikan layar yang menampilkan dialog pilih tabel.](media/bb46dc856d2939af9c55bdc0303b8a27.png)

10. Pilih tombol **Tambahkan**.

> [!NOTE]
> Terkadang Anda akan diminta untuk masuk saat bekerja dengan perancang. Pilih X untuk membatalkan keluar dari layar masuk.

## Tugas 2: Edit aplikasi berbasis model agar sesuai dengan kebutuhan Anda

Sekarang setelah aplikasi dibuat, kita akan membuat beberapa perubahan pada cara aplikasi disajikan. Kami memiliki dua golongan yang berbeda; Orang dan Peristiwa. Kami ingin memiliki tabel Kontak di grup Orang, dan semua tabel Peristiwa di grup Acara.

1.  Di bawah **Navigasi** di sisi kiri layar, pilih **Grup** Baru.
2.  Di sisi kanan aplikasi, perluas **panel Properti** .
3.  **Ubah Judul** dari **Grup** Baru menjadi **Orang.**

    ![Cuplikan layar memperlihatkan perubahan nama grup. ](media/82b6d0cdc4fdbaf4a9eaf2d1f82e972f.png)

4.  Pilih **Elipsis** pada **grup Orang** .
5.  Pilih **Grup** baru.
6.  Di panel **Properti** , ubah nama grup dari **Grup** Baru menjadi **Peristiwa.**
7.  Arahkan mouse ke atas **tampilan** Pendaftaran Sesi di sebelah kiri, pilih **elipsis**, dan pilih **Pindah ke bawah** untuk memindahkan **Pendaftaran** Sesi ke **dalam grup Peristiwa** .
8.  Arahkan mouse ke atas tampilan Sesi** Peristiwa di sebelah kiri, pilih **elipsis**, dan pilih **Pindah ke bawah** untuk memindahkan **Sesi** Peristiwa ke **dalam grup Peristiwa**.**
9.  Arahkan mouse ke atas **tampilan** Peristiwa di sebelah kiri, pilih **elipsis**, dan pilih **Pindahkan ke bawah** untuk memindahkan **Peristiwa** ke **dalam grup** Peristiwa.

Aplikasi Anda harus menyerupai gambar:

![cuplikan layar memperlihatkan peta situs yang diperbarui](media/ff039cad105533933959854cec4ec95e.png)

## Tugas 3: Edit berbagai formulir dan tampilan di aplikasi berbasis model Anda agar sesuai dengan kebutuhan Anda.

Aplikasi berbasis model menggunakan formulir dan tampilan untuk menyajikan data kepada pengguna di antarmuka Pengguna (UI). Kita akan membuat beberapa perubahan pada item tersebut.

1.  Jika perlu, pastikan aplikasi Contoso Event Management** Anda **terbuka di perancang.
2.  Di sisi kiri layar, di bawah **grup Orang** , arahkan kursor **ke formulir** Kontak dan pilih **Edit.**

    Jika Anda diminta untuk menyimpan perubahan, pilih **Simpan dan Lanjutkan.**

3.  Di bawah **Kolom** Tabel di sebelah kiri, pilih **Kolom** tabel baru.
4.  Konfigurasikan kolom tabel sebagai berikut:
    -   **Nama Tampilan:** Tipe Kontak
    -   **Jenis Data:** Pilihan
    -   **Sinkronkan dengan pilihan global:** Tidak
5.  Atur **Label** pilihan pertama ke **Pembicara.**
6.  Pilih **+ Pilihan** Baru dan atur label ke **Peserta.**
7.  Pilih **+ Pilihan** Baru dan atur label ke **Staf** Dukungan.

![Cuplikan layar kolom Jenis Kontak.](media/b1982b779d91cf134b41b6f445b8f07c.png)

8.  Pilih tombol **Simpan**.
9.  Menggunakan mouse Anda, pilih **teks Kontak** Baru untuk memilih header formulir. *(Persegi panjang ungu akan muncul di sekitar header)*
10. Di bawah **Kolom** Tabel, di **bidang Pencarian** , masukkan **Kontak**.
11. **Pilih kolom tabel Tipe** Kontak yang baru saja Anda buat.
12. **Tipe** Kontak sekarang akan muncul di **Header**.

![Cuplikan layar memperlihatkan bidang jenis kontak pada formulir.](media/4debe7a09e460f79c1cb05a6824dad66.png)

13. Pada bilah Perintah formulir **, pilih tombol **Simpan dan terbitkan**.**
14. Pilih tombol Panah** belakang **untuk kembali ke perancang aplikasi berbasis model
15. Di bawah **Navigasi** di sebelah kiri, arahkan kursor **ke **tampilan** Kontak, dan pilih ikon Edit**.
16. Pilih **+ Tampilkan Kolom**.
17. Cari dan tambahkan **kolom Tipe** Kontak ke formulir.
18. Pilih tombol **Simpan dan Terbitkan** .

Selanjutnya, kita akan membuat perubahan yang diperlukan pada formulir yang tersisa.

19.  Di bawah **Navigasi**, pilih **Tampilan** Peristiwa.

Perhatikan bahwa mungkin **ada kolom EventDetails1** . Jika demikian, kita akan menghapusnya dari tampilan. *(Jika Anda tidak memilikinya,* **Anda dapat melompat ke Langkah 28***)*

20.  Arahkan mouse ke **atas tampilan** Peristiwa dan pilih tombol **Edit** .

Jika diminta untuk **Menyimpan perubahan, pilih **Simpan dan lanjutkan****.

21.  Pada Tampilan **** pilih panah di samping **EventDetails1**, dan dari menu yang muncul, pilih **Hapus**.

![Cuplikan layar memperlihatkan cara menghapus kolom tambahan dari tampilan.](media/f0f1484a4f3a679abc18cdb1cd5c04da.png)

22.  Pilih tombol **Simpan dan Terbitkan** .
23.  Pilih tombol Panah** belakang **untuk kembali ke perancang aplikasi.
24.  Di bawah **Navigasi**, arahkan mouse ke **atas formulir** Peristiwa **** dan pilih **Edit**.

Jika diminta untuk menyimpan perubahan, pilih **Simpan dan lanjutkan**.

25.  Pilih **bidang Detail Peristiwa1** dan tekan tombol **Hapus** di keyboard Anda.

Formulir Anda harus menyerupai gambar:

![Cuplikan layar memperlihatkan formulir Peristiwa yang diperbarui, setelah kolom tambahan dihapus. ](media/d9e8903c79b01e85e32c6ef5279a2ad5.png)

26.  Pilih tombol **Simpan dan terbitkan** .
27.  Pilih tombol Panah** belakang **untuk kembali ke perancang aplikasi.

Jika Anda tidak memiliki bidang EventDetail1 pada formulir Anda, lanjutkan di sini.

28.  Pada bilah **Perintah** aplikasi, pilih tombol **Simpan dan Terbitkan** .
29.  Pilih tombol **Kembali** untuk kembali ke **portal pembuat** Power Apps.
30.  Pilih **Kembali ke solusi** untuk kembali ke layar Utama **Power Apps** .

## Tugas 4: Uji aplikasi baru Anda

Sekarang setelah aplikasi berbasis model Anda dibuat, kami akan menguji fungsionalitasnya.

Pertama kita akan menambahkan beberapa kontak.

1.  Menggunakan navigasi di sebelah kiri, pilih **Aplikasi**.
2.  Ubah aplikasi yang ditampilkan dari **Aplikasi** saya ke **Semua**.
3.  Arahkan mouse ke **aplikasi Course Event Management** yang baru saja Anda buat dan pilih **ikon Putar** .
4.  Menggunakan navigasi di sebelah kiri, pilih **Kontak**.
5.  Pada bilah perintah, pilih tombol **+ Baru** .
6.  **Di layar Kontak** Baru, konfigurasikan sebagai berikut:
    -   **Nama Depan:** Suzanne
    -   **Nama Belakang:** Diaz.
    -   **Jabatan Pekerjaan:** Insinyur
7.  Di header formulir, pilih panah bawah di samping **Tipe** Kontak.
8.  Atur **Jenis** Kontak ke **Pembicara**.

![Cuplikan layar memperlihatkan cara mengatur bidang Tipe Kontak pada formulir.](media/0860116a9b7df096c14728212b9977b1.png)

9.  Pilih tombol **Simpan** untuk menyimpan kontak dan membiarkannya terbuka.
10. Pilih tombol **+ Baru**.
11. **Di layar Kontak** Baru, konfigurasikan sebagai berikut:
    -   **Nama Depan:** Edgar
    -   **Nama Belakang:** Swenson
    -   **Jabatan Pekerjaan:** Arsitek
12. Di header formulir, pilih panah bawah di samping **Tipe** Kontak.
13. Atur **Tipe** Kontak ke **Peserta**.
14. Pilih tombol **Simpan & Tutup** .

Selanjutnya, kita akan menambahkan peristiwa baru.

15.  Menggunakan navigasi di sebelah kiri, pilih **Peristiwa**.
16.  Pada bilah perintah, pilih tombol **+ Baru** .
17.  **Di layar Kejadian** Baru, konfigurasikan sebagai berikut:
- **Nama Acara:** Konferensi musim semi.
- **Tanggal Acara:** Tanggal besok.
- **Peserta Maks:** 500
- **Detail Acara:** Konferensi musim semi untuk menampilkan produk dan layanan terbaru dari vendor kami yang didukung.
- **Jenis Acara:** Konferensi
- **Lokasi:** Seattle
- **Pendaftaran Diperlukan:** Ya/Benar

![Cuplikan layar formulir Peristiwa yang telah selesai. ](media/802f68c4c34c635eeff620a23d42acd8.png)

18.  Pilih tombol **Simpan & Tutup** .

Selanjutnya, kita akan menambahkan sesi baru untuk Acara.

19.  Menggunakan navigasi di sebelah kiri, pilih **Sesi** Peristiwa.
20.  Pilih tombol **+ Baru**.
21.  Konfigurasikan **Sesi** Peristiwa sebagai berikut:
- **Nama Sesi:** AI yang bertanggung jawab
- **Tanggal Sesi:** Tanggal Besok
- **Durasi:** 1,5 Jam
- **Deskripsi Sesi:** Dengan semua solusi AI baru, menjadi bertanggung jawab adalah penting. Kita akan membahas tantangannya.
- **Pembicara:** Suzanne Diaz
- **Acara:** Konferensi Musim Semi

![Cuplikan layar formulir sesi Peristiwa yang telah selesai. ](media/6e509e4a29e6f253b5db3b4c9f82e42e.png)

22.  Pilih tombol **Simpan dan tutup** .

Akhirnya, kita akan membuat **Pendaftaran** Sesi.

23.  Menggunakan navigasi di sebelah kiri, pilih **Pendaftaran Sesi.**
24.  Pada bilah **Perintah**, pilih **+ Baru**.
25.  Selesaikan pendaftaran sesi sebagai berikut:
- **Nama:** E, Pendaftaran Swenson.
- **Tanggal Pendaftaran:** Tanggal Hari Ini
- **Peserta:** Edgar Swenson
- **Sesi:** Mark Jones

![Cuplikan layar formulir pendaftaran Sesi yang telah selesai.  ](media/16cccd9ebb949ba0f364211f1ee55d4d.png)

26.  Pilih tombol Simpan dan Tutup **** .
