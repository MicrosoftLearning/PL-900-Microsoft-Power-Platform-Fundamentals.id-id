---
lab:
  title: 'Lab 2: Cara membuat aplikasi kanvas'
  module: 'Module 3: Describe how to build applications with Microsoft Power Apps'
---

# Lab 2: Cara membuat aplikasi kanvas

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberikan penyewa sebagai bagian dari penyelenggaraan pelatihan yang dipimpin instruktur, harap diperhatikan bahwa penyewa disediakan untuk mendukung praktikum dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk ekstensi. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa kampus dan program. Banyak instruktur dan administrator Bellow Colleges perlu menghadiri acara, dan membeli item. Secara historis, melacak pengeluaran ini merupakan sebuah tantangan. 

Administrasi kampus ingin memodernisasi sistem pelaporan pengeluaran mereka dengan menyediakan cara digital kepada karyawan untuk melaporkan pengeluaran. 

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan karyawan Bellows College mengelola pengeluaran. 


## Langkah-langkah lab tingkat tinggi

Kami akan mengikuti garis besar di bawah ini untuk mendesain aplikasi kanvas:

- Membuat aplikasi kanvas laporan pengeluaran 

- Konfigurasikan cara menampilkan laporan pengeluaran di layar penelusuran

- Membuat beberapa perubahan mendasar pada aplikasi

- Menguji fungsionalitas aplikasi

## Prasyarat

- Penyelesaian **Modul 1 Lab 0 - Memvalidasi lingkungan lab**

## Latihan 1: Membuat aplikasi Kanvas Laporan Pengeluaran

### Tujuan: Dalam latihan ini, Anda akan membuat aplikasi kanvas dengan menyambungkan ke tabel Laporan Pengeluaran.

### Tugas 1: Membuat aplikasi Laporan Pengeluaran

1. Navigasikan ke `https://make.powerapps.com`

1. Anda mungkin perlu mengautentikasi ulang - pilih **Masuk** dan ikuti petunjuk jika diperlukan.

1. Pilih **lingkungan Dev One** pada bagian kanan atas, jika belum dipilih.

1. Pilih **+ Buat** dari navigasi kiri layar. Di bagian **Mulai dari**, pilih **Dataverse**.

1. Pilih koneksi Dataverse Anda.

    >**Catatan**: Jika koneksi Dataverse tidak ada:

    >   - Pilih **+Koneksi baru**

    >   - Cari **Microsoft Dataverse**

    >   - Pilih **Buat**

    >   - **Masuk** dan pilih **Izinkan akses**

1. Temukan dan pilih **tabel Laporan** Pengeluaran.

1. Pilih tombol **Koneksi** di sudut kanan bawah.

1. Setelah aplikasi Anda dibuat, pada layar Selamat Datang di Power Apps Studio, pilih **Jangan tampilkan ini lagi**, lalu pilih **Lewati**.

1. Pada perancang aplikasi, pilih **Tombol pratinjau aplikasi** (ikon Putar) pada bilah perintah. (Anda juga dapat melakukan pratinjau aplikasi dengan menekan F5.) Silakan melihat-lihat dan lihat tampilan aplikasi Anda yang unik.

1. Tutup pratinjau aplikasi dengan memilih **X** di kanan atas layar.

Selamat, Anda telah berhasil membuat Power App dari tabel Dataverse. Langkah selanjutnya dalam proses ini adalah menyesuaikan aplikasi agar sejalan dengan branding organisasi Anda. Serangkaian langkah selanjutnya akan memandu Anda menyediakan beberapa penyesuaian tambahan untuk aplikasi.

### Tugas #2: Mengubah dan membuat tema aplikasi yang baru dibuat

Dalam tugas ini, Anda akan menyesuaikan teks header di masing-masing dari tiga layar untuk aplikasi Anda (Telusuri, Detail, dan Edit) dan ubah tema aplikasi.

1. Anda berada di layar Telusuri. Pilih **Label Laporan** Pengeluaran pada layar.

1. Pada sisi kanan layar, di bawah tab Properti, perbarui properti kontrol **Teks** menjadi Laporan Pengeluaran Saya

1. Pada tab **Properti,** ubah **Ukuran font** menjadi **24**.

1. Pilih latar belakang layar yang kosong untuk melihat teks yang diperbarui pada layar Telusur Anda.

1. Dengan menggunakan **tampilan Pohon**pada navigasi sebelah kiri, pilih **DetailScreen1**.

1. Pilih **Label Laporan** Pengeluaran pada layar.

1. Pada sisi kanan layar, di bawah tab **Properti,** perbarui properti kontrol **Teks** menjadi Detail Laporan

1. Klik latar belakang yang kosong untuk melihat teks yang diperbarui di layar Detail Anda.

1. Dengan menggunakan **tampilan Pohon** pada navigasi sebelah kiri, pilih **EditScreen1** (Anda mungkin perlu menggulir ke bawah untuk melihatnya pada tampilan Pohon).

1. Pilih **Label Laporan** Pengeluaran pada layar.

1. Pada sisi kanan layar, di tab **Properti,** ganti teks pada properti kontrol **Teks** dengan Detail Edit

1. Klik di latar belakang yang kosong untuk melihat teks yang diperbarui di layar Edit Anda.

1. Dengan menggunakan **tampilan Pohon**, pada navigasi sebelah kiri, pilih **BrowseScreen1**.

1. Pada bar alat, pilih tombol **Tema** dan dari daftar yang muncul, pilih warna tema **Merah**.

### Tugas #3: Menguji aplikasi Laporan Pengeluaran Anda

Dalam tugas ini, Anda akan menguji aplikasi baru Anda.

1. Dengan aplikasi dalam kondisi terbuka di Desainer Aplikasi, pilih **Pengaturan** (Anda mungkin perlu memilih … agar Ikon Pengaturan ditampilkan), pada bagian **Umum** perbarui nama aplikasi Anda menjadi Aplikasi Laporan Pengeluaran, pilih **X** untuk menutup layar pengaturan lalu pilih **Simpan**.

1. Di menu navigasi sebelah kiri, pilih **BrowseScreen1**.

1. Pada perancang aplikasi, pilih **Tombol pratinjau aplikasi** (ikon Putar) pada bilah perintah. (Anda juga dapat melakukan pratinjau aplikasi dengan menekan F5.)

1. Setelah aplikasi terbuka, pada bidang **item Pencarian**, masukkan teks Perjalanan (Perhatikan cara item dalam galeri memfilter berdasarkan apa yang diketikkan pada bidang penelusuran).

1. Setelah catatan **Perjalanan ke Konferensi Power Platform** ditampilkan, pilih baris untuk menavigasi dan membuka layar Detail untuk Biaya tersebut.
 
    >**Catatan**: Jika lebih dari satu catatan Perjalanan ke Konferensi Power Platform yang ditampilkan, pilih salah satunya.

1. Untuk mengedit catatan, pilih **Ikon Pensil** di sudut kanan atas aplikasi.

1. Anda dapat mengedit **Nama Laporan** di sini dan pilih ikon **Tanda Centang** pada bagian kanan atas untuk menyimpan perubahan.

1. Pada bagian kanan atas layar, pilih ikon **X** untuk menutup mode pratinjau dan kembali ke editor aplikasi kanvas.

Selamat! Anda telah membuat dan mengonfigurasi aplikasi kanvas pertama Anda.

 
