---
lab:
  title: 'Lab 7: Cara membuat dasbor sederhana'
  module: 'Module 5: Get Started with Power BI'
ms.openlocfilehash: 5381acb81a59a46f6eb6aca9f2bde18de9846473
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898950"
---
# <a name="module-5-get-started-with-power-bi"></a>Modul 5: Memulai dengan Power BI
## <a name="lab-how-to-build-a-simple-dashboard"></a>Lab: Cara membuat dasbor sederhana

# <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus. 

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus. 

Di lab ini, Anda akan membuat dasbor Power BI yang memvisualisasikan data tentang kunjungan kampus.

# <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Kami akan mengikuti langkah-langkah di bawah ini untuk mendesain dan membuat dasbor Power BI:

-   Menghubungkan ke Dataverse
-   Mengubah data untuk menyertakan deskripsi yang mudah digunakan untuk baris terkait (pencarian)
-   Membuat dan menerbitkan laporan dengan berbagai visualisasi informasi kunjungan kampus
-   Manfaatkan kueri bahasa alami pengguna untuk membuat visualisasi tambahan
-   Membangun tampilan seluler dasbor Power BI


## <a name="prerequisites"></a>Prasyarat

* Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**
* Penyelesaian **Modul 2 Lab 1 - Pengantar Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai

-   Siapa target audiens laporan?
-   Bagaimana audiens akan menggunakan laporan? Perangkat khusus? Lokasi?
-   Apakah Anda memiliki data yang cukup untuk divisualisasikan?
-   Apa kemungkinan karakteristik yang dapat Anda gunakan untuk menganalisis data tentang kunjungan?

# <a name="exercise-1-create-power-bi-report"></a>Latihan \#1: Membuat Laporan Power BI 

**Tujuan:** Dalam latihan ini, Anda akan membuat laporan Power BI berdasarkan data dari database Dataverse Anda.

## <a name="task-1-install-power-bi-desktop--prepare-power-bi-service"></a>Tugas \#1: Menginstal Power BI Desktop / Menyiapkan layanan Power BI

1. Ikuti petunjuk di bawah ini untuk menyiapkan Power BI: 

    - Jika Power BI Desktop **sudah** terinstal, lewati ke [Tugas \#2](#task-2-prepare-data).
    
    - Jika Anda belum menginstal Power BI Desktop, selesaikan **Langkah #2**.
    
    - Jika Anda tidak memiliki izin yang diperlukan atau mengalami masalah saat menjalankan Power BI Desktop, lanjutkan ke **Langkah #4**.

2. Navigasikan ke [https://aka.ms/pbidesktopstore](https://aka.ms/pbidesktopstore) untuk mengunduh dan menginstal Power BI Desktop.

    > [!IMPORTANT]
    > Jika Anda mengalami masalah saat menginstal Power BI Desktop menggunakan Microsoft Store, coba penginstal mandiri yang dapat diunduh dari [https://aka.ms/pbiSingleInstaller](https://aka.ms/pbiSingleInstaller).

3. Jika Anda berhasil menginstal Power BI Desktop, Anda sekarang dapat melompat ke [Tugas \#2](#task-2-prepare-data); jika tidak, lanjutkan ke langkah berikutnya.

    > Jika Anda tidak memiliki izin yang diperlukan untuk menginstal aplikasi desktop atau mengalami kesulitan dalam menjalankan atau mengonfigurasi Power BI Desktop, selesaikan langkah-langkah tugas di bawah ini.

4. Unduh [visits.pbix](../../Allfiles/visits.pbix) dan simpan di komputer Anda.

5. Navigasikan ke [https://app.powerbi.com/](https://app.powerbi.com/) dan klik **Masuk**. 

6. Klik **Ruang Kerja Saya**. 

7. Jika halaman **Dapatkan Data** muncul, klik **Lewati**. 

8. Luaskan **+Baru** dan pilih **Unggah file**.

    > [!IMPORTANT]
    > Jika Anda tidak melihat **+Baru**, Anda mungkin perlu mengaktifkan tampilan baru untuk Power BI. Pastikan untuk mengalihkan **Tampilan baru** ke **Aktif** di bagian atas layar Anda.

9. Pilih **File Lokal**.

10. Cari dan pilih file **visits.pbix** yang telah Anda unduh sebelumnya.

11. Setelah pemuatan data selesai, pilih laporan **kunjungan** (perhatikan bahwa Jenis diatur ke **Laporan**).

12. Klik **Edit**. Jika item menu **Edit** tidak terlihat, klik **...** lalu pilih **Edit**.

13. Anda sekarang telah menyiapkan layanan Power BI untuk digunakan di lab Anda. Lanjutkan ke [Tugas \#3](#task-3-create-chart-and-time-visualizations), tetapi gunakan layanan Power BI online di [https://app.powerbi.com](https://app.powerbi.com), bukan Power BI Desktop di seluruh lab.

## <a name="task-2-prepare-data"></a>Tugas \#2: Mempersiapkan Data

1.  Mencari tahu URL organisasi Anda

    * Di tab baru, navigasikan ke Pusat Admin Power Platform di <https://admin.powerplatform.com>
    
    * Di halaman navigasi kiri, pilih Lingkungan, lalu buka lingkungan Latihan Anda.
    
    * Klik kanan mouse **URL Lingkungan** pada panel **Detail**, lalu pilih **Salin alamat tautan**.
    
2. Buka Power BI Desktop, masuk dengan kredensial yang Anda berikan jika diminta.

3. Pilih **Dapatkan data** lalu pilih **lainnya...** .

4. Pilih **Power Platform** di sebelah kiri, lalu pilih **Layanan Data Umum (Legacy)** , dan tekan **Hubungkan**. Jika diminta, masuk dengan kredensial yang Anda berikan dan klik **Hubungkan**.

5. Tempelkan URL lingkungan yang Anda salin sebelumnya ke bidang **URL Server**, tekan **OK**.

6. Luaskan node **Entitas**, pilih entitas **bc_Building** dan **bc_Visit**, klik **Muat**.

7. Klik ikon **Model** di bilah alat vertikal kiri.

8. Seret kolom **bc_buildingid** dari tabel **bc_Building** dan jatuhkan ke kolom **bc_building** di tabel **bc_Visit**. Tindakan ini akan membuat hubungan antara dua tabel yang dapat digunakan Power BI untuk menampilkan data terkait.

9. Pilih ikon **Laporkan** di bilah alat kiri.

10. Luaskan node **bc_Visit** di panel **Bidang**.

11. Klik **...** di samping **bc_Visit** dan pilih **Kolom Baru**.

12. Lengkapi rumus sebagai berikut:

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    dan tekan ENTER. Tindakan ini akan menambahkan bidang baru dengan nama gedung ke dalam data kunjungan.

13. Klik **...** di samping bidang **Kolom** yang baru saja Anda buat dan pilih **Ganti nama**. Masukkan **Gedung** sebagai nama bidang.

14. Klik **...** di samping bidang **bc_visitid** dan pilih **Ganti nama**. Masukkan **Kunjungan** sebagai nama bidang.

15. Klik **...** di samping bidang **bc_scheduledstart** dan pilih **Ganti nama**. Masukkan **Mulai** sebagai nama bidang.

16. Simpan pekerjaan yang sedang berlangsung dengan menekan **File\| Simpan** dan masukkan nama file pilihan Anda.

## <a name="task-3-create-chart-and-time-visualizations"></a>Tugas #3: Membuat Grafik dan Memvisualisasi Waktu

1. Tekan ikon diagram lingkaran di panel **Visualisasi** untuk menyisipkan diagram.

2. Seret bidang **Gedung** dan letakkan di kotak **Legenda**.

3. Seret bidang **Kunjungan** dan jatuhkan ke kotak target **Nilai**.

4. Ubah ukuran diagram lingkaran menggunakan handel sudut sehingga semua komponen diagram terlihat.

5. Klik laporan di luar bagan pai untuk membatalkan pilihan dan pilih bagan kolom bertumpuk di panel **Visualisasi**. 

6. Seret bidang **Kunjungi** dan jatuhkan ke kotak target **Nilai**.

7. Seret bidang **Mulai** dan jatuhkan ke kotak target **Sumbu**.

8. Di panel Visualisasi, klik **x** di samping **Hari** dan **Kuartal** untuk menyisakan total **Tahun** dan **Bulan** untuk sumbu.

9. Ubah ukuran bagan sesuai keinginan menggunakan handel sudut.

10. Uji interaktivitas laporan:

    * Pilih berbagai potongan bangunan pada diagram lingkaran dan amati perubahan pada laporan waktu.
    
    * Klik pada grafik kolom. Tekan panah bawah untuk mengaktifkan mode **Lihat ke bawah**, lalu tekan kolom untuk menelusuri ke tingkat berikutnya (bulan). Cara lain untuk melakukannya adalah dengan mengklik **Data/Bor \| Perluas tingkat berikutnya** pada pita.
    
    * Telusuri ke atas dan ke bawah dan pilih berbagai batang pada bagan kolom waktu untuk mengamati perubahan pada laporan pai.
    
11. Simpan pekerjaan yang sedang berlangsung dengan menekan **File\| Simpan**.

# <a name="exercise-2-create-power-bi-dashboard"></a>Latihan #2: Membuat Dasbor Power BI

## <a name="task-1-publish-power-bi-report"></a>Tugas 1: Menerbitkan Laporan Power BI

1. Tekan tombol **Terbitkan** pada tab Beranda di pita.

2. Pilih **Ruang kerja saya** sebagai tujuan, lalu tekan **Pilih**.

3. Tunggu hingga penerbitan selesai dan klik **Buka \<name of your report\>.pbix di Power BI**.

## <a name="task-2-create-power-bi-dashboard"></a>Tugas #2: Membuat Dasbor Power BI

1. Anda harus membuka laporan dari tugas sebelumnya.

2. Pilih **Sematkan ke dasbor** pada menu. Tergantung pada tata letak, Anda mungkin perlu menekan **...** untuk menampilkan item menu tambahan.

3. Pilih **Dasbor baru** pada perintah **Sematkan ke dasbor**.

4. Masukkan **[Nama Belakang Anda] Manajemen Kampus** sebagai **Nama dasbor**, tekan **Sematkan langsung**.

5. Pilih **Ruang kerja saya** di bagian atas, pilih dasbor **[Nama Belakang Anda] Manajemen Kampus**.

6. Uji interaktivitas diagram lingkaran dan batang yang ditampilkan.

## <a name="task-3-add-visualizations-using-natural-language"></a>Tugas #3: Menambahkan Visualisasi Menggunakan Bahasa Alami

1. Dalam dasbor **Manajemen Kampus**, pilih bilah **Ajukan pertanyaan tentang data Anda** di bagian atas.

2. Masukkan **bangunan menurut jumlah kunjungan** di area Tanya Jawab. Diagram batang akan ditampilkan.

3. Pilih **Sematkan visual**.

4. Pilih **Dasbor yang ada**, pilih dasbor **[Nama Belakang Anda] Manajemen Kampus**, tekan **Sematkan**.

5. Klik **Keluar dari Q&A**.

Dasbor **[Nama Belakang Anda] Manajemen Kampus** Anda akan muncul. Anda mungkin harus menggulir ke bawah untuk melihat visual Q&A yang baru. 

Dasbor Anda akan terlihat seperti berikut:

![Dasbor Power BI](media/5-powerbi-result.png)

## <a name="task-4-build-mobile-phone-view-and-share-a-report-with-a-qr-code"></a>Tugas #4: Membangun Tampilan Ponsel dan Membagikan Laporan dengan Kode QR

1. Di Dasbor, pilih **Edit \| Tata Letak Seluler**.

2. Atur ulang petak sesuai keinginan.

3. Klik **Tata letak seluler** di kanan atas dan ubah Tampilan menjadi **Tata letak web**.

4. Pilih **Ruang Kerja Saya** di bagian atas, dan pilih **Laporan** Anda.

5. Pilih **Edit** lalu pilih **... \| Buat Kode QR**.

6. *Opsional:* Jika Anda memiliki perangkat seluler, pindai kode menggunakan aplikasi pemindai QR yang tersedia di platform iOS dan Android, atau aplikasi kamera jika ponsel Anda mendukungnya. Masuk ke akun Anda jika diminta. Navigasikan dan jelajahi laporan di perangkat seluler.

# <a name="challenges"></a>Tantangan

* Dasbor dan laporan untuk menyertakan rencana kampus dan gedung Anda
* Melaporkan serta menganalisis pola dan tren kunjungan
* Visualisasi yang terlalu lama
* Streaming Power BI untuk pemrosesan mendekati real-time untuk kampus besar 
