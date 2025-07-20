---
lab:
  title: 'Lab 1: Membuat solusi'
  learning path: 'Learning Path: Manage the Microsoft Power Platform environment'
  module: 'Module 1: Describe Microsoft Dataverse'
---

## Tujuan pembelajaran

Dalam latihan ini, Anda akan membuat solusi Power Platform untuk menyimpan berbagai komponen yang Anda bangun. Di Power Platform, solusi digunakan untuk mengelompokkan komponen yang berbeda bersama-sama, dan untuk memberikan kemampuan transportasi. Solusi yang Anda buat dalam latihan ini akan digunakan di seluruh sisa kursus.

### Skenario

Contoso Consulting adalah organisasi layanan profesional yang berspesialisasi dalam layanan konsultasi IT dan AI. Sepanjang tahun, mereka menawarkan banyak acara yang berbeda kepada pelanggan mereka. Beberapa di antaranya adalah acara gaya pameran dagang di mana mereka memiliki banyak mitra masuk dan memberikan detail tentang produk baru, tren pasar, dan layanan. Yang lain terjadi sepanjang tahun dan merupakan webinar cepat yang digunakan untuk memberikan detail tentang masing-masing produk.

Contoso ingin menggunakan Power Platform untuk membangun solusi Manajemen peristiwa yang dapat mereka gunakan untuk mengelola berbagai peristiwa yang mereka host sepanjang tahun.

Dalam latihan ini Anda membuat solusi yang akan digunakan untuk Manajemen Siklus Hidup Aplikasi (ALM), dan untuk mengelompokkan semua aplikasi, situs, dan alur yang berbeda yang kami buat bersama sehingga dapat dikelola dan diangkut dengan mudah.

Perkiraan waktu untuk menyelesaikan latihan ini adalah **15 hingga 20** menit.

Setelah berhasil menyelesaikan latihan ini, Anda akan:

- Membuat solusi Manajemen peristiwa
- Tambahkan tabel Akun dan Kontak yang ada ke solusi.
- Buat tabel baru yang disebut Peristiwa dari dalam solusi.

## Tugas 1: Membuat solusi manajemen Peristiwa

1.  Buka [Power Apps portal pembuat](https://make.powerapps.com).
1.  Navigasi ke **Solusi**.
1.  Pada bilah perintah, pilih **+Solusi baru.**
1.  Di layar solusi baru konfigurasikan sebagai berikut:
    - **Nama tampilan:** Manajemen Peristiwa
    - **Nama:** EventManagement
1.  Di bawah **Publisher**, pilih **+ Penerbit baru**
1.  Konfigurasikan penerbit baru sebagai berikut
    - **Nama tampilan:** EventMSLearn
    - **Nama:** EventMSLearn
    - **Awalan:** mslearn
    - **Awalan nilai pilihan:** Biarkan default

    ![Cuplikan layar Buat Penerbit Baru.](media/61fa62c324d424f7c73c8291a0724130.png)

1.  Pilih tombol **Simpan** untuk menyimpan penerbit.
1.  **Di bidang Penerbit**, pilih **penerbit EventMSlearn** yang baru saja Anda buat.
1.  Pilih **Atur sebagai solusi** pilihan Anda.

    ![Cuplikan layar solusi yang telah selesai](media/f968526926661bfa401f10742e6f376f.png)

1.  Pilih **Buat** untuk membuat solusi.

## Tugas 2: Tambahkan komponen yang ada ke solusi.

Sekarang setelah kita membuat solusi untuk menyimpan komponen kita, kita akan menambahkan beberapa tabel yang ada ke dalamnya. Kami akan menambahkan tabel Akun dan Kontak, sehingga dapat dengan mudah digunakan di aplikasi, alur, dan situs Manajemen Peristiwa kami yang berbeda. Pertama, kita akan menambahkan tabel Akun ke solusi.

1.  Jika perlu, buka solusi Manajemen** Peristiwa yang **Anda buat di tugas sebelumnya.
1.  Pada bilah **Perintah**, Pilih **Tambahkan yang sudah ada.**
1.  Dari menu yang muncul, pilih **Tabel.**
1.  **Pilih tabel Akun**, lalu pilih **Berikutnya.**
1.  **Pada layar Tabel yang** dipilih, pilih **Sertakan semua objek.**
1.  Pilih **Tambahkan**.

    Sekarang setelah kita memiliki tabel Akun, kita akan menambahkan tabel Kontak.

1.  Pada bilah **Perintah**, Pilih tombol **Tambahkan yang** sudah ada lagi.
1.  Dari menu yang muncul, pilih **Tabel.**
1.  **Pilih tabel Kontak**, lalu pilih **Berikutnya.**
1.  **Pada layar Tabel yang** dipilih, pilih **Sertakan semua objek**
1.  Pilih **Tambahkan**

    ![Cuplikan layar memperlihatkan tabel Akun dan Kontak dalam solusi.](media/a53817e242fca7371765583d9e565c36.png)

Selamat. Anda telah berhasil membuat solusi baru menggunakan Power Platform. Kami akan terus menggunakan solusi untuk menambahkan komponen tambahan ke dalamnya.
