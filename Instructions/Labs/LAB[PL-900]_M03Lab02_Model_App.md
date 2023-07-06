---
lab:
  title: 'Lab 3: Cara membuat aplikasi berbasis model'
  module: 'Module 3: Get started with Power Apps'
---

# Lab 3: Cara membuat aplikasi berbasis model

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberikan penyewa sebagai bagian dari pengiriman pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa tersedia untuk tujuan mendukung lab langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab langsung. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk ekstensi. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak untuk mendapatkan akses dan repositori kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab ini, Anda akan membuat aplikasi berbasis model Power Apps untuk memungkinkan staf kampus backoffice mengelola catatan kunjungan di seluruh kampus.

Langkah-langkah lab tingkat tinggi

Sebagai bagian dari pembuatan aplikasi berbasis model, Anda akan menyelesaikan hal berikut:

- Membuat aplikasi berbasis model baru bernama Manajemen Kampus

- Mengedit navigasi aplikasi untuk merujuk tabel yang diperlukan

- Menyesuaikan bentuk dan tampilan tabel yang diperlukan untuk aplikasi

Kami akan bekerja dengan komponen berikut:

- **Tampilan**: Tampilan memungkinkan pengguna menampilkan data yang ada dalam tabel formulir.

- **Formulir**: Di sinilah pengguna membuat/memperbarui baris baru dalam tabel.

Keduanya akan diintegrasikan ke aplikasi berbasis model untuk pengalaman pengguna yang lebih baik.

Prasyarat

- Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**

- Menyelesaikan **Modul 2 Lab 1 - Membuat Model Data**

Hal-hal yang perlu dipertimbangkan sebelum memulai

- Perubahan apa yang harus kami lakukan untuk meningkatkan pengalaman pengguna?

- Apa yang harus kami sertakan dalam aplikasi berbasis model berdasarkan model data yang telah kami buat?

- Penyesuaian apa yang dapat dilakukan pada peta situs aplikasi berbasis model?

Latihan 1: Menyesuaikan Tampilan serta Formulir

**Tujuan:** Dalam latihan ini, Anda akan menyesuaikan tampilan dan bentuk tabel yang dibuat khusus yang akan digunakan dalam aplikasi berbasis model.

Tugas 1: Mengedit Formulir Kunjungan

1. Masuk ke [https://make.powerapps.com](https://make.powerapps.com/) jika Anda belum masuk.

2. Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

3. Menggunakan navigasi di sebelah kiri, pilih **Tabel**, dan klik untuk membuka tabel **Kunjungi** Anda.

Jika Anda tidak melihat tabel Kunjungi, pastikan Anda berada di lingkungan yang benar (langkah 2).

4. Pada bagian **Pengalaman data**, pilih **Formulir** dan klik untuk membuka formulir Informasi dengan jenis formulir **Utama**. (**Penting:** Pastikan Anda memilih yang memiliki jenis formulir **Utama**.) 

**PENTING:** Karena secara default semua formulir diberi nama Informasi, pastikan untuk memverifikasi bahwa formulir yang Anda pilih memiliki Jenis Formulir **Utama** dan bukan yang lain. Secara default, formulir memiliki dua bidang: Nama dan Pemilik.

1. Di sisi kanan layar di panel Properti, pilih bidang **Nama Tampilan**, dan ubah ke **Informasi Utama**.

2. Pilih **Kolom Tabel** dari panel navigasi sebelah kiri dan tambahkan bidang berikut di bawah bidang **Pemilik** dengan menyeret kolom ke formulir atau cukup mengklik nama kolom:

    1. **Pengunjung**

    2. **Waktu Mulai yang Dijadwalkan**

    3. **Waktu Selesai yang Dijadwalkan**

    4. **Mulai Aktual**

    5. **Akhir Aktual**

3. Seret kolom **Kode** dan letakkan di header formulir.

Header adalah area kanan atas formulir. Anda mungkin perlu menciutkan panel Properti di sisi kanan layar untuk melihat bidang pada formulir.

1. Dengan bidang **Kode** masih dipilih, centang kotak **Baca-saja** di panel Properti di sisi kanan layar.

2. Pilih bidang **Pemilik**. Di panel Properti, ubah **Label** menjadi **Host**

3. Klik tombol **Simpan dan Terbitkan** di kanan atas dan tunggu hingga penyimpanan dan penerbitan selesai.

4. Jika tampilan edit dibuka di tab atau jendela browser baru, tutup tampilan tersebut. Jika tidak, klik **Kembali** di kiri atas layar. Anda sekarang harus kembali ke Formulir tabel Kunjungan.

5. Menggunakan petunjuk navigasi di kiri atas (Tabel>Kunjungan>Formulir). Pilih **Kunjungan** untuk kembali ke layar utama tabel **Kunjungan**.

Tugas #2: Edit tampilan Kunjungan Aktif

Dalam tugas ini, kita akan mengubah tampilan Kunjungan Aktif default dan membuat tampilan baru untuk kunjungan hari ini.

1. Pada bagian **Pengalaman data**, pilih **Tampilan** dan klik untuk membuka tampilan **Kunjungan Aktif** Anda.

2. Tambahkan bidang berikut ke tampilan dengan mengklik atau menyeret dan menjatuhkan bidang:

    1. **Kode**

    2. **Pengunjung**

    3. **Waktu Mulai yang Dijadwalkan**

    4. **Waktu Selesai yang Dijadwalkan**

3. Klik kolom **Dibuat Pada** dan pilih **Hapus**. Bidang **Dibuat Pada** sekarang akan dihapus dari tampilan.

4. Ubah ukuran lebar kolom masing-masing agar sesuai dengan data.

5. Di bawah **Urutkan berdasar ...** pilih X untuk menghapus **Nama** dan sebagai gantinya, pilih **Mulai Terjadwal**.

6. Pilih **Mulai Terjadwal** untuk mengubah urutan pengurutan menjadi **Baru ke Lama**.

7. Klik **Simpan** dan tunggu hingga perubahan disimpan.

8. Klik **Terbitkan** dan tunggu hingga penerbitan selesai.

Tugas #3: Membuat tampilan baru untuk kunjungan hari ini

Sekarang, kita akan mengkloning tampilan untuk membuat tampilan baru untuk kunjungan hari ini.

PENTING: Pastikan Anda tidak menutup tampilan Kunjungan Aktif, karena kita akan memanfaatkannya untuk membuat tampilan kunjungan hari ini yang baru.

1. Klik **panah dropdown** di sebelah tombol Simpan (hati-hati jangan sampai tidak sengaja menekan tombol itu) dan pilih **Simpan Sebagai**.

2. Ubah nama menjadi **Kunjungan Hari Ini** dan tekan **Simpan**.

3. Klik tautan **Edit filter** di panel Properti.

4. Klik **Tambahkan**, pilih **Tambahkan baris**.

5. Pilih **Waktu Mulai yang Dijadwalkan** sebagai bidang, lalu pilih **Hari ini** sebagai ketentuan di dropdown.

6. Klik **…** pada baris **Status** dan klik **Hapus** untuk menghapus kondisi filter tersebut.

7. Tekan **Oke** untuk menyimpan kondisi. Tampilan sekarang difilter untuk menampilkan hanya catatan dengan tanggal Mulai Terjadwal adalah hari ini.

8. Tambahkan bidang **Waktu Mulai Aktual** dan **Waktu Selesai Aktual** ke tampilan.

**Catatan:** Karena kita tidak lagi memfilter status tampilan, kita akan mendapatkan semua kunjungan hari ini termasuk kunjungan yang telah selesai. Kolom ini akan membantu membedakan kunjungan yang telah selesai dan kunjungan yang sedang berlangsung.

1. Klik **Simpan** dan tunggu hingga perubahan disimpan.

2. Klik **Terbitkan** dan tunggu hingga penerbitan selesai.

Latihan 2: Membuat Aplikasi Berbasis Model

**Tujuan:** Dalam latihan ini, Anda akan membuat aplikasi berbasis model, menyesuaikan peta situs, serta menguji aplikasi.

Demi kesederhanaan dan waktu, kita tidak akan membahas beberapa kolom Kunjungan di lab ini.

Tugas #1: Membuat aplikasi

1. Masuk ke [https://make.powerapps.com](https://make.powerapps.com/) (jika Anda belum masuk).

2. Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

3. Jika perlu, klik ikon **Beranda** di sisi kiri layar.

4. Buat Aplikasi Berbasis Model:

    1. Pilih **Aplikasi kosong** di bagian **Mulai dari** layar Beranda.

    2. Di bagian **Aplikasi kosong berdasarkan Dataverse**, pilih **Buat**.

    3. Masukkan **Manajemen Kampus Bellows** untuk Nama dan pilih **Buat**.

5. Setelah aplikasi berbasis model baru Anda dimuat, pilih tombol **+ Tambahkan Halaman**.

6. Pada layar **Tambahkan Halaman** , pilih **tabel Dataverse**, lalu pilih tombol **Berikutnya** .

7. Tambahkan tabel berikut:

    1. Kunjungan

    2. Kontak

8. Setelah memilih 2 tabel, pilih **Tambahkan**.

9. Menggunakan ikon navigasi di sisi kiri layar, pilih **Navigasi**.

10. Di Panel Navigasi, pilih **Grup 1** di bawah teks bertuliskan bilah Navigasi. Anda mungkin perlu memperluas menu di sebelah kiri.

11. Di sisi kanan layar, di bagian **Opsi Tampilan**, ubah properti **Judul** menjadi **Keamanan**.

12. Di Panel Navigasi, di grup keamanan, pilih **SubArea1**.

13. Pilih **Ellipsis**, dan dari menu yang muncul, pilih **Hapus dari navigasi**.

14. Klik **Simpan** dan tunggu hingga perubahan disimpan.

15. Setelah **Simpan** selesai, pilih tombol **Terbitkan** untuk menerbitkan perubahan Anda.

Tugas #2: Uji aplikasi

1. Mulai aplikasi

    1. Pilih tombol **Putar**, aplikasi baru akan memuat tab baru.

2. Membuat Kontak baru

    1. Aplikasi akan terbuka pada tampilan **Kontak Aktif Saya**. Jika tidak, harap pilih Kontak di navigasi bagian kiri.

    2. Klik **+ Baru** dari menu atas.

    3. Berikan **Nama Depan** sebagai John dan **Nama Belakang** sebagai Doe.

    4. Berikan email pribadi Anda sebagai **Email**. Ini akan digunakan di lab mendatang di mana Anda akan menerima email.

    5. Klik **Simpan &amp; Tutup**.

    6. Anda kini akan melihat kontak yang dibuat pada tampilan **Kontak Aktif Saya**.

3. Membuat Kunjungan baru

    1. Pilih **Kunjungan** dari navigasi peta situs sebelah kiri.

    2. Klik **+ Baru**.

    3. Masukkan bidang sebagai berikut

        1. **Nama**: Kunjungan pengujian baru

        2. **Pengunjung**: pilih John Doe

        3. **Waktu Mulai yang Dijadwalkan**: pilih tanggal besok dan pukul 14.00 sebagai waktu mulai

        4. **Waktu Selesai yang Dijadwalkan**: pilih tanggal besok dan pukul 15.30 sebagai waktu selesai

- Klik **Simpan &amp; Tutup**. Ini akan membuat Kunjungan dan Anda akan dapat melihatnya di Tampilan Kunjungan Aktif.

- Ubah tampilan ke **Kunjungan Hari Ini** dengan menggunakan menu menurun di samping **Kunjungan Aktif**. Anda sekarang tidak akan melihat kunjungan baru lagi dalam tampilan, karena dijadwalkan untuk besok.

1. Anda dapat menambahkan lebih banyak catatan pengujian.

Aplikasi Anda yang sedang berjalan akan terlihat kira-kira seperti berikut:

![](media/3-model-driven-app.png)

Selamat! Anda telah membuat dan mengonfigurasi aplikasi berbasis model pertama Anda.

## Tantangan

- Pilih tampilan dan formulir tertentu untuk Kontak.
