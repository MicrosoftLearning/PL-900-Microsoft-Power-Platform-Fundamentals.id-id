---
lab:
  title: 'Lab 2: Cara membuat aplikasi kanvas'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 24d99d14079d40f74a43ed0de64dd6ae5d7046c7
ms.sourcegitcommit: 0118c25a230425d0ccba16e6c3922053ee07c183
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/06/2022
ms.locfileid: "144810920"
---
# <a name="module-3-get-started-with-power-apps"></a>Modul 3: Mulai dengan Power Apps
## <a name="lab-how-to-build-a-canvas-app"></a>Lab: Cara membuat aplikasi kanvas

# <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Kunjungan kampus saat ini dicatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Saat ini, administrasi kampus memanfaatkan spreadsheet excel, untuk melacak pendaftaran pengunjung. Mereka ingin memodernisasi sistem pendaftaran pengunjung tempat akses ke gedung dikontrol oleh staf keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh tuan rumah mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

# <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Kami akan mengikuti garis besar di bawah ini untuk mendesain aplikasi kanvas:

-   Membuat aplikasi kanvas dari data di tabel Kunjungan

-   Mengonfigurasi cara kunjungan ditampilkan di layar penelusuran

-   Membuat beberapa perubahan mendasar pada aplikasi

-   Menguji fungsionalitas aplikasi

## <a name="prerequisites"></a>Prasyarat

-   Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**

# <a name="exercise-1-create-visits-app"></a>Latihan \#1: Membuat Aplikasi Kunjungan

**Tujuan:** Dalam latihan ini, Anda akan membuat aplikasi kanvas dengan menghubungkan tabel Awal Kunjungan yang dibuat sebelumnya.

## <a name="task-1-create-a-visits-app"></a>Tugas \#1: Membuat Aplikasi Kunjungan

1.  Navigasikan ke <https://make.powerapps.com>. Anda mungkin perlu mengautentikasi ulang - klik **Masuk** dan ikuti petunjuk jika diperlukan.

2.  Pilih lingkungan **Latihan [inisial saya]** Anda di kanan atas jika belum dipilih.

3.  Jika perlu, klik ikon **Beranda** di sisi kiri layar. Di bagian **Mulai dari**, pilih **Dataverse**.

4.  Pilih koneksi Dataverse Anda. 

    >   **CATATAN:** *Jika koneksi Dataverse tidak ada:*
    >   -   Pilih **Koneksi Baru**
    >   -   Cari **Microsoft Dataverse**
    >   -   Klik **Buat**

5.  Cari dan pilih tabel **Kunjungan** yang Anda buat di lab sebelumnya.

6.  Pilih tombol **Koneksi** di sudut kanan bawah.

7.  Setelah aplikasi dibuat, Pada layar Selamat Datang di Power Apps Studio, centang kotak **Jangan tampilkan ini lagi kepada saya**, lalu pilih **Lewati**.

8.  Setelah pembuatan selesai, akan melihat tampilan seperti gambar di bawah ini.

![Aplikasi kanvas dibuat dari data Kunjungan.](media/2-canvas-app-from-data.png)

9. Di perancang aplikasi, pilih tombol **pratinjau aplikasi Anda** (ikon Putar) pada bilah perintah. *(Anda juga dapat melihat pratinjau aplikasi dengan menekan F5 pada keyboard.)* Silakan melihat-lihat dan lihat tampilan aplikasi Anda yang unik.

10. Tutup pratinjau aplikasi dengan memilih **X** di kanan atas layar.

Selamat, Anda telah berhasil membuat Power App dari tabel Dataverse. Langkah selanjutnya dalam proses ini adalah menyesuaikan aplikasi agar sesuai dengan branding perguruan tinggi Anda. Serangkaian langkah selanjutnya akan memandu Anda menyediakan beberapa penyesuaian tambahan untuk aplikasi.

## <a name="task-2-modify-and-theme-the-newly-created-app"></a>Tugas \#2: Mengubah dan membuat tema aplikasi yang baru dibuat

Dalam tugas ini, Anda akan menyesuaikan teks header di masing-masing dari tiga layar untuk aplikasi Anda (Telusuri, Detail, dan Edit) dan ubah tema aplikasi.

1.  Anda berada di layar Telusuri. Pilih label **Kunjungan** di layar.

3.  Di sisi kanan layar, di tab Properti, perbarui properti kontrol **Teks** menjadi **“Bellows College Visits”** .

4. Di properti, ubah **Ukuran font** menjadi **24**.

4.  Klik di latar belakang kosong untuk melihat teks yang diperbarui di layar Telusuri Anda.

5.  Di menu navigasi sebelah kiri, pilih **DetailScreen1**.

5.  Pilih label **Kunjungan** di layar.

6.  Di sisi kanan layar, di tab properti, perbarui properti kontrol **Teks** menjadi **“Detail Kunjungan”** .

7.  Klik latar belakang kosong untuk melihat teks yang diperbarui di layar Detail Anda.

8.  Menggunakan navigasi di sebelah kiri, pilih **EditScreen1** (Anda mungkin perlu menggulir ke bawah untuk melihat ini pada tampilan Pohon).

9.  Pilih label **Kunjungan** di layar.

10.  Di sisi kanan layar, di tab properti, ganti teks Tabel1 di properti kontrol **Teks** dengan **“Edit Detail”** .

11.  Klik di latar belakang kosong untuk melihat teks yang diperbarui di layar Edit Anda.

12. Di menu navigasi sebelah kiri, pilih **BrowseScreen1**.

13. Pada bilah bar toolbar, pilih tombol **Tema** dan dari daftar yang muncul, pilih warna tema **Merah**.

## <a name="task-3-test-your-visits-app"></a>Tugas \#3: Menguji aplikasi Kunjungan Anda

Dalam tugas ini, Anda akan menguji aplikasi baru Anda.

1.  Dengan aplikasi Anda terbuka di Perancang Aplikasi, pilih **File**, perbarui nama aplikasi menjadi **Aplikasi Kunjungan** dan pilih **Simpan**.

2.  Pilih panah **kembali** untuk kembali ke aplikasi Anda.

3.  Di menu navigasi sebelah kiri, pilih **BrowseScreen1**.

4.  Di perancang aplikasi, pilih tombol **pratinjau aplikasi Anda** (ikon Putar) pada bilah perintah. *(Anda juga dapat melihat pratinjau aplikasi dengan menekan F5 pada keyboard.)*

4.  Setelah aplikasi terbuka, di bidang **Item Pencarian**, masukkan teks **Maria**
     *(Perhatikan bagaimana item di galeri memfilter berdasarkan apa yang diketik dalam bidang pencarian).*

5.  Setelah rekaman **Contoso Suites** untuk **Maria Campbell** ditampilkan, klik baris untuk menavigasi untuk membuka detail kunjungan tersebut. (**Catatan**: *Jika lebih dari satu data Contoso Suites Maria Campbell ditampilkan, pilih salah satu*)

6.  Untuk mengedit catatan, pilih **Ikon Pensil** di sudut kanan atas aplikasi.

7.  Anda dapat mengedit Nama Kunjungan di sini dan klik ikon Tanda Centang di kanan atas untuk menyimpan perubahan.

8.  Di kanan atas layar, klik Ikon **X** untuk kembali ke editor aplikasi kanvas.

Selamat! Anda telah membuat dan mengonfigurasi aplikasi kanvas pertama Anda.

# <a name="challenges"></a>Tantangan

-   Tambahkan kolom berikut ke formulir di DetailScreen1 dan EditScreen1: Waktu Mulai Sebenarnya, Selesai Sebenarnya, Kode, Jadwal Mulai, & Jadwal Selesai
