---
lab:
  title: 'Lab 5: Cara membuat dasbor sederhana'
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: 8d104c42de9d4114c668a63a4d8d30cbbcc4b39e
ms.sourcegitcommit: 36c8fda9cdc6f448416d7000e38c1606bea87d2e
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 05/07/2022
ms.locfileid: "144812934"
---
# <a name="module-5-get-started-with-power-bi"></a>Modul 5: Memulai dengan Power BI
## <a name="lab-how-to-build-a-simple-dashboard"></a>Lab: Cara membuat dasbor sederhana

# <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab ini, Anda akan membuat dasbor Power BI yang memvisualisasikan data tentang kunjungan kampus.

# <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Kami akan mengikuti langkah-langkah di bawah ini untuk merancang dan membuat dasbor Power BI:

-   Menghubungkan ke Dataverse

-   Mengubah data untuk menyertakan deskripsi yang mudah digunakan untuk baris terkait (pencarian)

-   Membuat dan menerbitkan laporan dengan berbagai visualisasi informasi kunjungan kampus

-   Manfaatkan kueri bahasa alami pengguna untuk membuat visualisasi tambahan

-   Membangun tampilan seluler dasbor Power BI

## <a name="prerequisites"></a>Prasyarat

-   Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**

-   Penyelesaian **Modul 2 Lab 1 - Pengantar Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai

-   Siapa target audiens laporan?

-   Bagaimana audiens akan menggunakan laporan? Perangkat khusus? Lokasi?

-   Apakah Anda memiliki data yang cukup untuk divisualisasikan?

-   Apa kemungkinan karakteristik yang dapat Anda gunakan untuk menganalisis data tentang kunjungan?

# <a name="exercise-1-create-power-bi-report"></a>Latihan \#1: Membuat Laporan Power BI

**Tujuan:** Dalam latihan ini, Anda akan membuat laporan Power BI berdasarkan data spreadsheet Excel yang kami gunakan di latihan sebelumnya.

## <a name="task-1-prepare-power-bi-service"></a>Tugas \#1: Mempersiapkan layanan Power BI

1.  Unduh [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) dan simpan di komputer Anda.

2.  Navigasikan ke <https://app.powerbi.com/> dan masuk jika perlu.

3.  Di pojok kiri bawah layar, pilih **Dapatkan Data**

4.  Pilih tombol **Dapatkan** di bagian **File**, **Buat konten baru**.

5.  Pilih **File Lokal**.

6.  Cari dan pilih file **visits.pbix** yang telah Anda unduh sebelumnya.

7.  Setelah pemuatan data selesai, pilih laporan **kunjungan** (perhatikan bahwa Jenis diatur ke **Laporan**).

8.  Klik **Edit**. Jika item menu **Edit** tidak terlihat, klik **...** lalu pilih **Edit**.

Anda sekarang telah menyiapkan layanan Power BI untuk digunakan di lab Anda. 

## <a name="task-2-create-chart-and-time-visualizations"></a>Tugas \#2: Membuat Grafik dan Memvisualisasi Waktu

1.  Tekan ikon **Bagan pai** di panel **Visualisasi** untuk menyisipkan bagan.

2.  Tekan panah drop-down di samping **bc_name** di panel Bidang. Seret bidang **Gedung** dan letakkan di kotak **Legenda**.

3.  Tekan panah drop-down di samping **bc_Visit** di panel Bidang. Seret bidang **Kunjungan** dan letakkan di kotak **Nilai**.

4.  Ubah ukuran diagram lingkaran menggunakan handel sudut sehingga semua komponen diagram terlihat.

5.  Klik laporan di luar bagan pai untuk membatalkan pilihan dan pilih bagan kolom bertumpuk di panel **Visualisasi**.

6.  Tekan panah drop-down di samping **bc_Visit** di panel Bidang. Seret bidang **Kunjungan** dan letakkan di kotak **Nilai**.

7.  Seret bidang **Mulai** dan jatuhkan ke kotak target **Sumbu**.

8.  Di panel Visualisasi, klik **x** di samping **Tahun** dan **Kuartal** untuk menyisakan hanya total **Bulan** dan **Hari** pada sumbu.

9.  Ubah ukuran bagan sesuai keinginan menggunakan handel sudut.

10. Uji interaktivitas laporan:

    1.  Pilih berbagai potongan bangunan pada diagram pai dan amati perubahan pada laporan waktu.

    2.  Klik pada grafik kolom. Tekan panah bawah untuk mengaktifkan mode **Telusuri paling detail** (atau klik kanan pada bagan dan pilih **Telusuri paling detail**), lalu klik kolom untuk menelusuri paling detail ke tingkat berikutnya (hari). 
    
    3.  Telusuri ke atas dan ke bawah dan pilih berbagai batang pada bagan kolom waktu untuk mengamati perubahan pada laporan pai.

11. Simpan pekerjaan yang sedang berlangsung dengan menekan **Simpan**.

# <a name="exercise-2-create-power-bi-dashboard"></a>Latihan \#2: Membuat Dasbor Power BI

## <a name="task-1-create-power-bi-dashboard"></a>Tugas \#1: Membuat Dasbor Power BI

1.  Anda harus membuka laporan dari tugas sebelumnya.

2.  Pilih **Sematkan ke dasbor** pada menu. Tergantung pada tata letak, Anda mungkin perlu menekan **...** untuk menampilkan item menu tambahan.

3.  Pilih **Dasbor baru** pada perintah **Sematkan ke dasbor**.

4.  Masukkan **Manajemen Kampus** sebagai **Nama dasbor**, tekan **Sematkan langsung**.

5.  Pilih **Ruang kerja saya** di bagian atas, pilih dasbor **[Nama Belakang Anda] Manajemen Kampus**.

6.  Jendela pop-up akan muncul dengan pemberitahuan bahwa dasbor telah dibuat. Pilih **Buka dasbor**.

7.  Uji interaktivitas diagram lingkaran dan batang yang ditampilkan.

## <a name="task-2-add-visualizations-using-natural-language"></a>Tugas \#2: Menambahkan Visualisasi Menggunakan Bahasa Alami

1.  Dalam dasbor **Manajemen Kampus**, pilih bilah **Ajukan pertanyaan tentang data Anda** di bagian atas.

2.  Masukkan **bangunan menurut jumlah kunjungan** di area Tanya Jawab. Diagram batang akan ditampilkan.

3.  Pilih **Sematkan visual**.

4.  Pilih **Dasbor yang ada**, pilih dasbor **Manajemen Kampus**, tekan **Sematkan**.

5.  Klik **Keluar dari Q&A**.

Dasbor **Manajemen Kampus** Anda akan ditampilkan dengan tiga visual di atasnya. Anda mungkin harus menggulir ke bawah untuk melihat visual Q&A yang baru.

Dasbor Anda akan terlihat seperti berikut:

![](media/5-powerbi-result.png)
