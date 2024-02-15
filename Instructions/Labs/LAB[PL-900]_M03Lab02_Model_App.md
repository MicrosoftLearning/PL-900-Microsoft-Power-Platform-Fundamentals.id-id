---
lab:
  title: 'Lab 3: Cara membuat aplikasi berbasis model'
  module: 'Module 3: Get started with Power Apps'
---

# Lab 3: Cara membuat aplikasi berbasis model

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberikan penyewa sebagai bagian dari pengiriman pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa tersedia untuk tujuan mendukung lab langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat perpanjangan. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab ini, Anda akan membuat aplikasi berbasis model Power Apps untuk memungkinkan staf kampus backoffice mengelola catatan kunjungan di seluruh kampus.

## Langkah-langkah lab tingkat tinggi

Sebagai bagian dari pembuatan aplikasi berbasis model, Anda akan menyelesaikan hal berikut:

- Membuat aplikasi berbasis model baru bernama Manajemen Kampus

- Mengedit navigasi aplikasi untuk merujuk tabel yang diperlukan

- Menyesuaikan bentuk dan tampilan tabel yang diperlukan untuk aplikasi

Kami akan bekerja dengan komponen berikut:

- **Tampilan**: Tampilan memungkinkan pengguna menampilkan data yang ada dalam tabel formulir.

- **** Formulir: Di sinilah pengguna membuat/memperbarui baris baru dalam tabel.

Keduanya akan diintegrasikan ke aplikasi berbasis model untuk pengalaman pengguna yang lebih baik.

## Prasyarat

- Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**

- Menyelesaikan **Modul 2 Lab 1 - Membuat Model Data**

Hal-hal yang perlu dipertimbangkan sebelum memulai

- Perubahan apa yang harus kami lakukan untuk meningkatkan pengalaman pengguna?

- Apa yang harus kami sertakan dalam aplikasi berbasis model berdasarkan model data yang telah kami buat?

- Penyesuaian apa yang dapat dilakukan pada peta situs aplikasi berbasis model?

## Latihan 1: Menyesuaikan Tampilan serta Formulir

**Tujuan:** Dalam latihan ini, Anda akan menyesuaikan tampilan dan formulir tabel kustom yang dibuat yang akan digunakan di aplikasi berbasis model.

### Tugas #1: Edit Formulir Kunjungan

1.  Jika Anda belum melakukannya, masuk ke `https://make.powerapps.com` 

2.  **Pilih lingkungan Dev One** di kanan atas, jika belum dipilih.

3.  Menggunakan navigasi di sebelah kiri, pilih **Tabel**, dan buka tabel Kunjungi Anda.** **

    Jika Anda tidak melihat tabel Kunjungi, pastikan Anda berada di lingkungan yang benar (langkah 2).

4.  Di bawah bagian **Pengalaman data** , pilih **Formulir** dan buka **formulir Informasi** dengan **jenis Formulir Utama** . (**Penting:** Pastikan Anda memilih formulir dengan jenis **formulir Utama**.) 

    > **PENTING:** Karena secara default semua formulir diberi nama Informasi, pastikan untuk memverifikasi bahwa formulir yang Anda pilih memiliki Jenis **Utama** Formulir dan bukan yang lain. Secara default, formulir memiliki dua bidang: Nama dan Pemilik.

5.  Di sisi kanan layar pada panel **Properti** , pilih **bidang Nama** Tampilan, dan ubah menjadi `Main Information`

6.  Pilih **Kolom tabel** dari panel navigasi kiri dan tambahkan bidang berikut ini di bawah **bidang Pemilik** dengan menyeret kolom ke formulir atau cukup mengklik nama kolom:

    1. **Pengunjung**

    2. **Waktu Mulai yang Dijadwalkan**

    3. **Waktu Selesai yang Dijadwalkan**

    4. **Mulai Aktual**

    5. **Akhir Aktual**

7.  Seret kolom **Kode** dan letakkan di header formulir.

    Header adalah area kanan atas formulir. Anda mungkin perlu menciutkan panel Properti di sisi kanan layar untuk melihat bidang pada formulir.

8.  Dengan bidang **Kode** masih dipilih, centang kotak **Baca-saja** di panel Properti di sisi kanan layar.

9.  Pilih bidang **Pemilik**. Di panel Properti, ubah Label** menjadi **`Host`

10. Pilih tombol **Simpan dan terbitkan** di kanan atas dan tunggu hingga penyimpanan dan penerbitan selesai.

11. Jika tampilan Edit dibuka di tab atau jendela browser baru, tutup tampilan tersebut. Jika tidak, pilih **🡠 Kembali** di kiri atas layar. Anda sekarang harus kembali ke **Formulir Tabel kunjungan** .

12. Menggunakan remah roti di kiri atas (**Tabel** > **Kunjungi > ****Formulir).** Pilih **Kunjungi** untuk kembali ke **layar properti Kunjungi** Tabel. 


### Tugas #2: Edit tampilan Kunjungan Aktif

Dalam tugas ini, kita akan mengubah tampilan Kunjungan Aktif default dan membuat tampilan baru untuk kunjungan hari ini.

1.  Di bawah bagian **Pengalaman data**, pilih **Tampilan** dan buka tampilan Kunjungan** Aktif Anda**.

2.  Tambahkan bidang berikut ke tampilan dengan mengklik atau menyeret dan menjatuhkan bidang:

    1. **Kode**

    2. **Pengunjung**

    3. **Waktu Mulai yang Dijadwalkan**

    4. **Waktu Selesai yang Dijadwalkan**

3.  Pilih menu drop-down pada **kolom Dibuat Pada** dan pilih **Hapus**. Bidang **Dibuat Pada** sekarang akan dihapus dari tampilan.

4.  Mengubah ukuran lebar kolom individual sesuai dengan data.

5.  Di bawah **Urutkan menurut ...** pilih X untuk menghapus **Nama** dan sebagai gantinya, pilih **Mulai** Terjadwal.

6.  Pilih **Mulai** Terjadwal untuk mengubah urutan pengurutan menjadi **Lebih Baru ke yang lebih** lama.

7.  Pilih tombol **Simpan dan terbitkan** di kanan atas dan tunggu penerbitan selesai.


### Tugas #3: Membuat tampilan baru untuk kunjungan hari ini

Sekarang, kita akan mengkloning tampilan untuk membuat tampilan baru untuk kunjungan hari ini.

> **PENTING:** Pastikan Anda tidak menutup tampilan Kunjungan Aktif, karena kami akan memanfaatkannya untuk membuat tampilan kunjungan baru hari ini.

1.  Pilih **Simpan Sebagai**.

2.  **Ubah Nama** menjadi `Today’s Visits` dan pilih **Simpan**.

3.  Pilih **Edit filter**, di panel Properti.

4.  Pilih **+ Tambahkan**, pilih **Tambahkan baris**.

5.  Pilih **Bidang Mulai** Terjadwal sebagai, lalu ubah **Sama dengan** **Hari Ini** sebagai kondisi di menu drop-down.

6.  **Pilih ...** **** Perintah lainnya pada baris Status** dan pilih **Hapus** untuk menghapus kondisi filter tersebut**.

7.  Pilih **Ok** untuk menyimpan kondisi. Tampilan sekarang difilter untuk memperlihatkan hanya rekaman di mana **tanggal Mulai** Terjadwal adalah hari ini.

8.  Tambahkan bidang **Waktu Mulai Aktual** dan **Waktu Selesai Aktual** ke tampilan.

> **CATATAN:** Karena kami tidak lagi memfilter status tampilan, kami akan mendapatkan semua kunjungan hari ini termasuk yang telah selesai. Kolom ini akan membantu membedakan kunjungan yang telah selesai dan kunjungan yang sedang berlangsung.

9.  Pilih tombol **Simpan dan terbitkan** di kanan atas dan tunggu penerbitan selesai.


## Latihan 2: Membuat Aplikasi Berbasis Model

**Tujuan:** Dalam latihan ini, Anda akan membuat aplikasi berbasis model, menyesuaikan peta situs, serta menguji aplikasi.

Demi kesederhanaan dan waktu, kita tidak akan membahas beberapa kolom Kunjungan di lab ini.

### Tugas #1: Membuat aplikasi

1.  Jika Anda belum melakukannya, masuk ke `https://make.powerapps.com` 

2.  **Pilih lingkungan Dev One** di kanan atas, jika belum dipilih.

3.  Pilih **+ Buat** di navigasi kiri.

4.  Buat Aplikasi Berbasis Model:

    1. Pilih **Aplikasi** kosong di bagian ****Mulai dari** layar Buat aplikasi** Anda.

    2. Di bagian **Aplikasi kosong berdasarkan Dataverse**, pilih **Buat**.

    3. Masukkan `Bellows Campus Management` untuk **Nama** dan pilih **Buat**.

5.  Setelah aplikasi berbasis model baru Anda dimuat, pilih tombol **+ Tambahkan Halaman**.

6.  **Pada layar Tambahkan Halaman**, pilih **Tabel** dataverse, lalu pilih tombol **Berikutnya**.

7.  Pilih tabel berikut:

    1. Kunjungan

    2. Kontak

8.  Setelah Anda memiliki kedua tabel, pilih **Tambahkan**.

9.  Menggunakan ikon navigasi di sisi kiri layar, pilih **Navigasi**.

10. Pada Panel Navigasi, pilih **Grup** Baru di bawah ini di mana tertulis Navigasi. Anda mungkin perlu memperluas menu di sebelah kiri.

11. Di sisi kanan layar, di bagian Opsi tampilan **, ubah **properti Judul** menjadi**`Security`

12. Klik **Simpan** dan tunggu hingga perubahan disimpan.

13. Setelah **Simpan** selesai, pilih tombol **Terbitkan** untuk menerbitkan perubahan Anda. Tunggu hingga penerbitan selesai.


### Tugas #2: Uji aplikasi

Mulai aplikasi

1. Pilih tombol **Putar** , aplikasi berbasis model akan dimuat di tab baru.

Buat Kontak baru

2.  Aplikasi akan terbuka pada tampilan **Kontak Aktif Saya**. Jika tidak, pilih **Kontak** di navigasi kiri.

3.  Pilih **+ Baru** dari bilah perintah.

4.  Masukkan **Nama** Depan sebagai `John` dan **Nama** Belakang sebagai `Doe`

5.  Berikan email pribadi Anda sebagai **Email**. Ini akan digunakan di lab mendatang, di mana Anda akan menerima email.

6.  Pilih **Simpan &amp; Tutup**.

7.  Anda kini akan melihat kontak yang dibuat pada tampilan **Kontak Aktif Saya**.

Buat Kunjungan baru

8.  Pilih **Kunjungan** dari navigasi sebelah kiri (Juga dikenal sebagai peta situs.)

9.  Pilih **+ Baru**.

10. Masukkan bidang sebagai berikut:

    1. **Nama**: `New test visit`

    2. **** Pengunjung: pilih **John Doe**

    3. **Mulai** Terjadwal: Pilih tanggal besok dan 14.00 sebagai waktu mulai

    4. **Akhir** Terjadwal: Pilih tanggal besok dan 15.30 sebagai waktu akhir

11. Pilih **Simpan &amp; Tutup**. Ini akan membuat Kunjungan dan Anda harus dapat melihatnya pada **tampilan Kunjungan** Aktif.

12. Ubah tampilan ke **Kunjungan** Hari Ini dengan menggunakan menu drop-down di samping **Kunjungan** Aktif. Anda sekarang tidak akan melihat kunjungan baru lagi dalam tampilan, karena dijadwalkan untuk besok.

13. Anda dapat menambahkan beberapa catatan pengujian lainnya.

Aplikasi berbasis model anda yang sedang berjalan akan terlihat seperti berikut ini:

![](media/3-model-driven-app.png)

Selamat! Anda telah membuat dan mengonfigurasi aplikasi berbasis model pertama Anda.

## Tantangan

- Pilih tampilan dan formulir tertentu untuk Kontak.

