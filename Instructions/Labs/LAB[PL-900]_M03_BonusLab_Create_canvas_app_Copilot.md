---
lab:
  title: 'Lab Bonus: Membuat aplikasi kanvas menggunakan Copilot'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Lab Bonus: Membuat aplikasi kanvas menggunakan Copilot

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberi penyewa sebagai bagian dari penyediaan pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa disediakan untuk tujuan mendukung lab praktik langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk ekstensi. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

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

1. Buka `https://make.powerapps.com`.

2. Anda mungkin perlu mengautentikasi ulang - pilih **Masuk** dan ikuti petunjuk jika diperlukan.

3. Pilih **lingkungan Dev One** pada bagian kanan atas, jika belum dipilih.

4. Pilih **+ Buat** dari navigasi kiri layar. Di bawah bagian **Buat aplikasi** Anda, pilih **Mulai dengan Salinan**.

5. Dalam kotak **Mulai menggunakan Copilot** , masukkan teks berikut ini. `Create an application that logs visits to a college campus`. 

6. Pilih tombol **Hasilkan**.

Copilot akan mulai membuat struktur tabel untuk mendukung aplikasi Anda. 

> **PENTING:** Saat menggunakan AI generatif, Anda tidak akan selalu mendapatkan hasil yang sama persis. Ada kemungkinan tabel Anda tidak akan sama persis dengan tabel yang dibuat untuk siswa lain. 

7. Di sisi kanan, pilih struktur tabel di jendela Salinan lalu pilih **Opsi tabel**.

8. Pilih **opsi Satu tabel** lalu pilih **Terapkan**.
 
    ![Cuplikan layar struktur Tabel yang baru saja dibuat](media/bonus-lab-tablestr.png)


> Untuk melihat struktur tabel, pilih tabel dan klik **tombol Tampilkan data** 

9. Dalam kotak **Apa yang ingin Anda lakukan berikutnya?** , masukkan teks: Tambahkan dua kolom, Waktu masuk dan Waktu habis dalam tabel. Keduanya harus berupa bidang tanggal dan waktu. 

10. Pilih tombol **Buka** atau tekan **Enter**. 

11. Gulir ke sisi tabel dan verifikasi bahwa **kolom Waktu masuk** dan **Waktu Habis** dibuat. 

Karena kita mencatat waktu pengunjung masuk dan keluar, kita tidak lagi memerlukan bidang tanggal kunjungan lainnya. 

12. **Temukan bidang Tanggal** Kunjungan (atau bidang yang setara) dan di kotak **Apa yang ingin Anda lakukan berikutnya?** , masukkan teks: Hapus Bidang Tanggal Kunjungan (atau bidang yang setara). 

>Jika diperlukan, perbarui nama bidang yang akan dihapus dari nama tabel yang relevan.

13. Pilih tombol **Buka**. 

14. Hapus bidang tanggal tambahan yang mungkin ada selain **Waktu masuk** dan **Waktu keluar**. 

Awalnya, ditambahkan bidang seperti bidang **Tujuan** diformat dengan tipe data teks. Kita akan meminta Copilot mengubahnya menjadi menu drop-down (Pilihan). 

15. **Di menu Apa yang ingin Anda lakukan selanjutnya?** masukkan teks berikut: Ubah bidang Tujuan menjadi menu pilihan dengan pilihan berikut: Tur Kampus, Pameran Karier, Bertemu dengan Profesor, Konseling Siswa, Lainnya. 

16. Pilih tombol **Buka**. 

17. Karena kami juga ingin mengambil nomor bangunan, di **kolom Apa yang ingin Anda lakukan berikutnya?**, masukkan: Tambahkan kolom bangunan. 

18. Pilih tombol **Buka**. 

19. Setelah Anda puas dengan tabel Anda, pilih tombol **Simpan dan buka aplikasi** . 

20. Jika perlu, Pada **layar Selesai berfungsi?** , pilih **Jangan tanya saya lagi**, dan pilih tombol **Simpan dan buka aplikasi** . 

![Cuplikan layar aplikasi yang baru saja dibuat](media/bonus-lab-copilot-02.png)

Selamat, Anda telah menggunakan Copilot untuk membuat aplikasi baru. 
