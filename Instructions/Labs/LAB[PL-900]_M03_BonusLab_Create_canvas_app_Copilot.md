---
lab:
  title: 'Lab Bonus: Membuat aplikasi kanvas menggunakan Copilot'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Lab Bonus: Membuat aplikasi kanvas menggunakan Copilot

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberi penyewa sebagai bagian dari penyediaan pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa disediakan untuk tujuan mendukung lab praktik langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa percobaan dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk perpanjangan. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Di lab ini, Anda akan menggunakan Copilot untuk membuat aplikasi kanvas baru untuk mencatat kunjungan. 

## Langkah-langkah lab tingkat tinggi

Kami akan mengikuti garis besar di bawah ini untuk mendesain aplikasi kanvas:

- Jelaskan aplikasi yang ingin Anda buat

- Gunakan Copilot untuk mengubah struktur tabel pendukung

 ## Prasyarat

- Penyelesaian **Modul 1 Lab 0 - Memvalidasi lingkungan lab**

## Latihan 1: Gunakan Copilot untuk membangun aplikasi kunjungan perguruan tinggi.

**Tujuan:** Dalam latihan ini, Anda akan membuat aplikasi kanvas dengan menyambungkan ke tabel Kunjungan kampus.

### Tugas \#1: Buat aplikasi awal

1. Navigasikan ke https://make.powerapps.com

2. Anda mungkin perlu mengautentikasi ulang - pilih **Masuk** dan ikuti petunjuk jika diperlukan.

3. Pilih lingkungan **Dev One** pada bagian kanan atas, jika belum dipilih.

4. Dalam kotak **Jelaskan aplikasi yang ingin Anda buat**, masukkan teks berikut. Buat aplikasi yang mencatat kunjungan ke kampus perguruan tinggi. 

5. Pilih tombol **Buka**.

Copilot akan mulai membuat struktur tabel untuk mendukung aplikasi Anda. 

> **PENTING:** Saat menggunakan AI generatif, Anda tidak akan selalu mendapatkan hasil yang sama persis. Ada kemungkinan tabel Anda tidak akan sama persis dengan tabel yang dibuat untuk siswa lain. 

6. Di kotak **Jelaskan yang harus diubah**, masukkan teks: Tambahkan dua kolom, Waktu masuk dan Waktu keluar. Keduanya harus berupa bidang tanggal dan waktu.  

7. Pilih tombol **Buka** atau tekan **Enter**. 

8. Gulir ke sisi tabel dan verifikasi bahwa kolom **Waktu masuk** dan **Waktu keluar** telah dibuat. 

Karena kita mencatat waktu pengunjung masuk dan keluar, kita tidak lagi memerlukan bidang tanggal kunjungan lainnya. 

9. Temukan bidang **Tanggal Kunjungan** (atau bidang yang serupa) dan di **kotak Jelaskan yang harus diubah**, masukkan teks Hapus Bidang Tanggal Kunjungan. 

10. Pilih tombol **Buka**. 

11. Hapus bidang tanggal tambahan yang mungkin ada selain **Waktu masuk** dan **Waktu keluar**. 

Awalnya, ditambahkan bidang seperti bidang **Tujuan** diformat dengan tipe data teks. Kita akan meminta Copilot mengubahnya menjadi menu drop-down (Pilihan). 

12. Di **kotak Jelaskan yang harus diubah**, masukkan teks berikut: Ubah bidang Tujuan menjadi menu pilihan dengan opsi berikut: Tur Kampus, Pameran Kerja, Bertemu dengan Profesor, Konseling Mahasiswa, Lainnya. 

13. Pilih tombol **Buka**. 

14. Karena kita juga ingin mengambil nomor gedung, di **kotak Jelaskan yang harus diubah**, masukkan: Tambahkan kolom gedung. 

15. Pilih tombol **Buka**. 

16. Setelah Anda puas dengan tabel Anda, pilih tombol **Buat Aplikasi**. 

17. Jika diperlukan, pada layar **Selamat Datang di Power Apps Studio**, pilih **Jangan tampilkan ini lagi**, dan pilih tombol **Lewati**. 

![Cuplikan layar aplikasi yang baru saja dibuat](media/bonus-lab-copilot-01.png)

Selamat, Anda telah menggunakan Copilot untuk membuat aplikasi baru. 
