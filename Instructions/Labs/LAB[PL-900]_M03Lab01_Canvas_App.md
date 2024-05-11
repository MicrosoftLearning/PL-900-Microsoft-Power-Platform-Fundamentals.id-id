---
lab:
  title: 'Lab 2: Cara membuat aplikasi kanvas'
  module: 'Module 3: Get started with Power Apps'
---

# Lab 2: Cara membuat aplikasi kanvas

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberikan penyewa sebagai bagian dari pengiriman pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa tersedia untuk tujuan mendukung lab langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk ekstensi. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa kampus dan program. Banyak instruktur dan administrator Bellow Colleges perlu menghadiri acara, dan membeli item. Secara historis melacak pengeluaran ini telah menjadi tantangan. 

Administrasi kampus ingin memodernisasi sistem pelaporan pengeluaran mereka dengan menyediakan cara digital kepada karyawan untuk melaporkan pengeluaran. 

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan karyawan Bellows College mengelola pengeluaran. 


## Langkah-langkah lab tingkat tinggi

Kami akan mengikuti garis besar di bawah ini untuk mendesain aplikasi kanvas:

- Membuat aplikasi kanvas laporan pengeluaran 

- Mengonfigurasi bagaimana laporan pengeluaran ditampilkan di layar telusur

- Membuat beberapa perubahan mendasar pada aplikasi

- Menguji fungsionalitas aplikasi

## Prasyarat

- Penyelesaian **Modul 1 Lab 0 - Memvalidasi lingkungan lab**

## Latihan 1: Membuat aplikasi Kanvas Laporan Pengeluaran

### Tujuan: Dalam latihan ini, Anda akan membuat aplikasi kanvas dengan menyambungkan ke tabel Laporan Pengeluaran.

### Tugas #1: Membuat aplikasi Laporan Pengeluaran

1. Navigasikan ke https://make.powerapps.com

1. Anda mungkin perlu mengautentikasi ulang - pilih **Masuk** dan ikuti instruksi, jika diperlukan.

1. **Pilih lingkungan Dev One** di kanan atas, jika belum dipilih.

1. Pilih **+ Buat** dari navigasi kiri layar. Di bagian **Mulai dari**, pilih **Dataverse**.

1. Pilih koneksi Dataverse Anda.

    >**Catatan**: Jika koneksi Dataverse tidak ada:

    >   - Pilih **+Koneksi baru**

    >   - Cari **Microsoft Dataverse**

    >   - Pilih **Buat**

    >   - **Masuk** dan pilih **Izinkan akses**

1. Temukan dan pilih **tabel Laporan** pengeluaran.

1. Pilih tombol **Koneksi** di sudut kanan bawah.

1. Setelah aplikasi Anda dibuat, pada layar Selamat Datang di Power Apps Studio, pilih **Jangan tampilkan lagi**, lalu pilih **Lewati**.

1. Di perancang aplikasi, pilih tombol **Pratinjau aplikasi** (ikon Putar) pada bilah perintah. (Anda juga dapat mempratinjau aplikasi dengan menekan F5.) Lihat sekeliling dan lihat bagaimana aplikasi Anda terlihat out-of-the-box.

1. Tutup pratinjau aplikasi dengan memilih **X** di kanan atas layar.

Selamat, Anda telah berhasil membuat Power App dari tabel Dataverse. Langkah selanjutnya dalam proses ini adalah menyesuaikan aplikasi agar sesuai dengan branding organisasi Anda. Serangkaian langkah selanjutnya akan memandu Anda menyediakan beberapa penyesuaian tambahan untuk aplikasi.

### Tugas #2: Ubah dan tema aplikasi yang baru dibuat

Dalam tugas ini, Anda akan menyesuaikan teks header di masing-masing dari tiga layar untuk aplikasi Anda (Telusuri, Detail, dan Edit) dan ubah tema aplikasi.

1. Anda berada di layar Telusuri. Pilih **label Laporan** Pengeluaran di layar.

1. Di sisi kanan layar, di bawah tab Properti, perbarui **properti Kontrol teks** ke Laporan Pengeluaran Saya

1. Di tab **Properti** , ubah **ukuran** Font menjadi **24**.

1. Pilih latar belakang kosong layar untuk melihat teks yang diperbarui di layar Telusuri Anda.

1. **Menggunakan tampilan** Pohon di navigasi kiri, pilih **DetailScreen1**.

1. Pilih **label Laporan** Pengeluaran di layar.

1. Di sisi kanan layar, di bawah tab **Properti, perbarui **properti Kontrol teks** ke** Detail Laporan

1. Klik latar belakang yang kosong untuk melihat teks yang diperbarui di layar Detail Anda.

1. **Menggunakan tampilan** Pohon di navigasi kiri, pilih **Edit Layar1** (Anda mungkin perlu menggulir ke bawah untuk melihat ini pada tampilan Pohon).

1. Pilih **label Laporan** Pengeluaran di layar.

1. Di sisi kanan layar, pada tab **Properti**, ganti teks di **** properti Kontrol teks dengan Edit Detail

1. Klik di latar belakang yang kosong untuk melihat teks yang diperbarui di layar Edit Anda.

1. **Menggunakan tampilan** Pohon, di navigasi kiri, pilih **Telusuri Layar1**.

1. Pada toolbar perintah, pilih tombol **Tema** dan dari daftar yang muncul, pilih **warna tema Merah** .

### Tugas #3: Menguji aplikasi Laporan Pengeluaran Anda

Dalam tugas ini, Anda akan menguji aplikasi baru Anda.

1. Dengan aplikasi Anda terbuka di Perancang Aplikasi, pilih **Pengaturan** (Anda mungkin perlu memilih ... untuk Ikon Pengaturan untuk ditampilkan), di bagian **Umum** perbarui nama aplikasi Anda ke Aplikasi Laporan Pengeluaran pilih **X** untuk menutup layar pengaturan lalu pilih **Simpan**.

1. Di menu navigasi sebelah kiri, pilih **BrowseScreen1**.

1. Di perancang aplikasi, pilih tombol **Pratinjau aplikasi** (ikon Putar) pada bilah perintah. (Anda juga dapat mempratinjau aplikasi dengan menekan F5.)

1. Setelah aplikasi terbuka, di **bidang Cari item** , masukkan teks Perjalanan (Perhatikan bagaimana item di filter galeri berdasarkan apa yang diketik di bidang pencarian).

1. **Setelah rekaman Konferensi** Perjalanan ke Power Platform ditampilkan, pilih baris untuk menavigasi dan membuka layar Detail untuk Pengeluaran tersebut.
 
    >**Catatan**: Jika lebih dari satu rekaman Konferensi Perjalanan ke Power Platform ditampilkan, pilih salah satunya.

1. Untuk mengedit catatan, pilih **Ikon Pensil** di sudut kanan atas aplikasi.

1. Anda dapat mengedit **Nama** Laporan di sini dan memilih **ikon Tanda** Centang di kanan atas untuk menyimpan perubahan.

1. Di kanan atas layar, pilih **ikon X** untuk menutup mode pratinjau dan kembali ke editor aplikasi kanvas.

Selamat! Anda telah membuat dan mengonfigurasi aplikasi kanvas pertama Anda.

 
