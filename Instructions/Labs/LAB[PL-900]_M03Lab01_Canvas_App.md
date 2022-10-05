---
lab:
  title: 'Lab 2: Cara membuat aplikasi kanvas'
  module: 'Module 3: Get started with Power Apps'
---

# <a name="lab-2-how-to-build-a-canvas-app"></a>Lab 2: Cara membuat aplikasi kanvas

## <a name="scenario"></a>Skenario

Bellows College is an educational organization with multiple buildings on campus. Campus visits are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Currently, campus administration is leveraging an Excel spreadsheet to track visitor registration. They would like to modernize their visitor registration system where access to the buildings is controlled by security personnel and all visits are required to be pre-registered and recorded by their hosts.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

## <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Kami akan mengikuti garis besar di bawah ini untuk mendesain aplikasi kanvas:

- Membuat aplikasi kanvas dari data di tabel Kunjungan

- Mengonfigurasi cara kunjungan ditampilkan di layar penelusuran

- Membuat beberapa perubahan mendasar pada aplikasi

- Menguji fungsionalitas aplikasi

## <a name="prerequisites"></a>Prasyarat

- Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**
- Menyelesaikan **Modul 2 Lab 1 - Membuat Model Data**

## <a name="exercise-1-create-visits-canvas-app"></a>Latihan 1: Membuat aplikasi bagi Visits Canvas

**Tujuan:** Dalam latihan ini, Anda akan membuat aplikasi Canvas dengan menghubungkan tabel Kunjungan yang dibuat sebelumnya.

### <a name="task-1-create-the-visits-app"></a>Tugas \#1: Membuat aplikasi bagi Kunjungan

1.  Navigate to <ph id="ph1">&lt;https://make.powerapps.com&gt;</ph>. You may need to reauthenticate - click <bpt id="p1">**</bpt>Sign in<ept id="p1">**</ept> and follow instructions if needed.

2.  Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

3.  If necessary, click the <bpt id="p1">**</bpt>Home<ept id="p1">**</ept> icon on the left side of the screen. Under the <bpt id="p1">**</bpt>Start from<ept id="p1">**</ept> section, select <bpt id="p2">**</bpt>Dataverse<ept id="p2">**</ept>.

4.  Pilih koneksi Dataverse Anda.

    > **CATATAN:** *Jika koneksi Dataverse tidak ada:*
    > - Pilih **Koneksi Baru**
    > - Cari **Microsoft Dataverse**
    > - Klik **Buat**

5.  Cari dan pilih tabel **Kunjungan** yang Anda buat di lab sebelumnya.

6.  Pilih tombol **Koneksi** di sudut kanan bawah.

7.  Setelah aplikasi dibuat, Pada layar Selamat Datang di Power Apps Studio, centang kotak **Jangan tampilkan ini lagi kepada saya**, lalu pilih **Lewati**.

8.  Setelah pembuatan selesai, akan melihat tampilan seperti gambar di bawah ini.

![Aplikasi kanvas dibuat dari data Kunjungan.](media/2-canvas-app-from-data.png)

9. Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus.

10. Tutup pratinjau aplikasi dengan memilih **X** di kanan atas layar.

Kunjungan kampus saat ini dicatat dalam jurnal kertas.

### <a name="task-2-modify-and-theme-the-newly-created-app"></a>Tugas \#2: Mengubah dan membuat tema aplikasi yang baru dibuat

Dalam tugas ini, Anda akan menyesuaikan teks header di masing-masing dari tiga layar untuk aplikasi Anda (Telusuri, Detail, dan Edit) dan ubah tema aplikasi.

1.  Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

1.  Di sisi kanan layar, di tab Properti, perbarui properti kontrol **Teks** menjadi **“Bellows College Visits”** .

1. Di properti, ubah **Ukuran font** menjadi **24**.

1.  Klik di latar belakang yang kosong untuk melihat teks yang diperbarui di layar Telusuri.

1.  Dengan menggunakan tampilan Pohon di navigasi sebelah kiri, harap pilih **DetailScreen1**.

1.  Pilih label **Kunjungan** di layar.

1.  Di sisi kanan layar, di tab properti, perbarui properti kontrol **Teks** menjadi **“Detail Kunjungan”** .

1.  Klik latar belakang yang kosong untuk melihat teks yang diperbarui di layar Detail Anda.

1.  Dengan menggunakan navigasi di sebelah kiri, harap pilih **EditScreen1** (Anda mungkin perlu menggulir ke bawah untuk melihat ini pada tampilan Pohon).

1.  Pilih label **Kunjungan** di layar.

1.  Di sisi kanan layar, di tab properti, ganti teks Tabel1 di properti kontrol **Teks** dengan **“Edit Detail”** .

1.  Klik di latar belakang yang kosong untuk melihat teks yang diperbarui di layar Edit Anda.

1. Dengan menggunakan tampilan Pohon di navigasi sebelah kiri, harap pilih **BrowseScreen1**.

1. Pada bilah bar toolbar, pilih tombol **Tema** dan dari daftar yang muncul, pilih warna tema **Merah**.

### <a name="task-3-test-your-visits-app"></a>Tugas \#3: Menguji aplikasi Kunjungan Anda

Dalam tugas ini, Anda akan menguji aplikasi baru Anda.

1.  Dengan aplikasi Anda terbuka di Perancang Aplikasi, pilih **File**, perbarui nama aplikasi menjadi **Aplikasi Kunjungan** dan pilih **Simpan**.

2.  Pilih panah **kembali** untuk kembali ke aplikasi Anda.

3.  Di menu navigasi sebelah kiri, pilih **BrowseScreen1**.

4.  In the app designer, select the <bpt id="p1">**</bpt>preview the app<ept id="p1">**</ept> button (Play icon) on the command bar. <bpt id="p1">*</bpt>(You can also preview the app by pressing F5 on your keyboard.)<ept id="p1">*</ept>

4.  Setelah aplikasi terbuka, di bidang **Item Pencarian**, masukkan teks **Maria**
     *(Perhatikan bagaimana item di galeri memfilter berdasarkan apa yang diketik dalam bidang pencarian).*

5.  Saat ini, administrasi kampus memanfaatkan spreadsheet Excel untuk melacak pendaftaran pengunjung.

6.  Untuk mengedit catatan, pilih **Ikon Pensil** di sudut kanan atas aplikasi.

7.  Anda dapat mengedit Nama Kunjungan di sini dan klik ikon Tanda Centang di kanan atas untuk menyimpan perubahan.

8.  Di kanan atas layar, klik Ikon **X** untuk kembali ke editor aplikasi kanvas.

Mereka ingin memodernisasi sistem pendaftaran pengunjung tempat akses ke gedung dikontrol oleh staf keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh tuan rumah mereka.

## <a name="challenges"></a>Tantangan

- Tambahkan kolom berikut ke formulir di DetailScreen1 dan EditScreen1: Waktu Mulai Sebenarnya, Selesai Sebenarnya, Kode, Jadwal Mulai, & Jadwal Selesai