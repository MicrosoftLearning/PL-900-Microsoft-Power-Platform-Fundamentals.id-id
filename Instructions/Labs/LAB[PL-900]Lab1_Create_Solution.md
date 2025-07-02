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

Contoso ingin menggunakan Power Platform untuk membangun solusi Manajemen Peristiwa yang dapat mereka gunakan untuk mengelola berbagai peristiwa yang mereka host sepanjang tahun.

Dalam latihan ini Anda akan membuat solusi yang akan digunakan untuk Manajemen Siklus Hidup Aplikasi, dan untuk mengelompokkan semua aplikasi, situs, dan alur yang berbeda yang kami buat bersama-sama sehingga dapat dikelola dan diangkut dengan mudah.

Perkiraan waktu untuk menyelesaikan latihan ini adalah **15 hingga 20** menit.

Setelah berhasil menyelesaikan latihan ini, Anda akan:

- Membuat Solusi Manajemen peristiwa
- Tambahkan tabel Akun dan Kontak yang ada ke solusi.
- Buat tabel baru yang disebut Peristiwa dari dalam solusi.

## Tugas 1: Membuat solusi Manajemen Peristiwa

1.  Buka [Power Apps portal pembuat](https://make.powerapps.com).
2.  Navigasi ke **Solusi**.
3.  Pada bilah perintah, pilih **Solusi Baru.**
4.  Di layar solusi baru konfigurasikan sebagai berikut:
    - **Nama Tampilan:** Manajemen Peristiwa
    - **Nama:** Manajemen peristiwa
5.  Di bawah **Publisher**, pilih **+ Penerbit baru**
6.  Konfigurasikan penerbit baru sebagai berikut
    - **Nama tampilan:** EventMSLEventMSLearnarn
    - **Nama:** EverntMSLearn
    - **Awalan:** mslearn
    - **Awalan nilai pilihan:** Biarkan default

![Cuplikan layar Buat Penerbit Baru.](media/61fa62c324d424f7c73c8291a0724130.png)

7.  Pilih tombol **Simpan** untuk menyimpan penerbit.
8.  **Di bidang Penerbit**, pilih **penerbit EventMSlearn** yang baru saja Anda buat.
9.  Pilih **Atur sebagai solusi** pilihan Anda.

![Cuplikan layar solusi yang telah selesai](media/f968526926661bfa401f10742e6f376f.png)

10.  Pilih **Buat**.

## Tugas 2: Tambahkan komponen yang ada ke solusi.

Sekarang setelah kita membuat solusi untuk menyimpan komponen kita, kita akan menambahkan beberapa tabel yang ada ke dalamnya. Kami akan menambahkan tabel Akun dan Kontak, sehingga dapat dengan mudah digunakan di aplikasi, alur, dan situs Manajemen Peristiwa kami yang berbeda. Pertama, kita akan menambahkan tabel Akun ke solusi.

1.  Jika perlu, buka solusi Manajemen** Peristiwa yang **Anda buat di tugas sebelumnya.
2.  Pada bilah **Perintah**, Pilih **Tambahkan yang sudah ada.**
3.  Dari menu yang muncul, pilih **Tabel**.
4.  **Pilih tabel Akun**, lalu pilih **Berikutnya.**
5.  **Pada layar Pilih Tabel**, pilih **Sertakan semua objek.**
6.  Pilih **Tambahkan**

Sekarang setelah kita memiliki tabel Akun, kita akan menambahkan tabel kontak.

7.  Pada bilah **Perintah**, Pilih tombol **Tambahkan yang** sudah ada lagi **.**
8.  Dari menu yang muncul, pilih **Tabel.**
9.  **Pilih tabel Kontak**, lalu pilih **Berikutnya.**
10.  **Pada layar Pilih Tabel**, pilih **Sertakan semua objek**
11.  Pilih **Tambahkan**

![Cuplikan layar memperlihatkan tabel Akun dan Kontak dalam solusi.](media/a53817e242fca7371765583d9e565c36.png)

Selamat, Anda telah berhasil membuat solusi baru menggunakan Microsoft power Platform. Kami akan terus menggunakan solusi untuk menambahkan komponen tambahan ke dalamnya.
