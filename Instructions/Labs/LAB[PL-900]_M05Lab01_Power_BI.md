---
lab:
  title: 'Lab 5: Cara membuat dasbor sederhana'
  module: 'Module 5: Get Started with Power BI'
---

## <a name="lab-5-how-to-build-a-simple-dashboard"></a>Lab 5: Cara membuat dasbor sederhana

## <a name="scenario"></a>Skenario

Bellows College is an educational organization with multiple buildings on campus. Campus visitors are currently recorded in paper journals. The information is not captured consistently, and there are no means to collect and analyze data about the visits across the entire campus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab ini, Anda akan membuat dasbor Power BI yang memvisualisasikan data mengenai kunjungan kampus.

## <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Kami akan mengikuti langkah-langkah di bawah ini untuk merancang dan membuat dasbor Power BI:

-   Membuat serta menerbitkan laporan dengan berbagai visualisasi informasi kunjungan kampus

-   Manfaatkan kueri bahasa alami pengguna untuk membuat visualisasi tambahan

## <a name="prerequisites"></a>Prasyarat

- Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**
- Menyelesaikan **Modul 2 Lab 1 - Membuat Model Data**

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai

-   Siapa target audiens laporan?
-   How will the audience consume the report? Typical device? Location?
-   Apakah Anda memiliki data yang cukup untuk divisualisasikan?
-   Apa kemungkinan karakteristik yang dapat Anda gunakan untuk menganalisis data tentang kunjungan?

## <a name="exercise-1-create-power-bi-report"></a>Latihan 1: Membuat Laporan Power BI

**Tujuan:** Dalam latihan ini, Anda akan membuat laporan Power BI berdasarkan data spreadsheet Excel yang kami gunakan di latihan sebelumnya.

### <a name="task-1-prepare-power-bi-service"></a>Tugas \#1: Mempersiapkan layanan Power BI

1.  Unduh [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) dan simpan di komputer Anda.

2.  Navigasikan ke <https://app.powerbi.com/> dan masuk jika perlu.

3.  Di pojok kiri bawah layar, pilih **Dapatkan Data**

4.  Pilih tombol **Dapatkan** di bagian **File**, **Buat konten baru**.

5.  Pilih **File Lokal**.

6.  Cari dan pilih file **visits.pbix** yang telah Anda unduh sebelumnya.

7.  Setelah pemuatan data selesai, perluas **Ruang kerja saya** dan pilih laporan **kunjungan** (perhatikan bahwa Jenis diatur ke **Laporan**).

8.  Click <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept>. If <bpt id="p1">**</bpt>Edit<ept id="p1">**</ept> menu item is not visible click <bpt id="p2">**</bpt>...<ept id="p2">**</ept> and then select <bpt id="p3">**</bpt>Edit<ept id="p3">**</ept>.

Anda sekarang telah menyiapkan layanan Power BI untuk digunakan di lab Anda.

### <a name="task-2-create-chart-and-time-visualizations"></a>Tugas \#2: Membuat Grafik dan Memvisualisasi Waktu

1.  Tekan ikon **Bagan pai** di panel **Visualisasi** untuk menyisipkan bagan.

2.  Press the drop-down arrow beside <bpt id="p1">**</bpt>bc_building<ept id="p1">**</ept> in the Fields pane. Drag the <bpt id="p1">**</bpt>Building<ept id="p1">**</ept> field and drop it into <bpt id="p2">**</bpt>Legend<ept id="p2">**</ept> box.

3.  Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus.

4.  Ubah ukuran diagram lingkaran menggunakan handel sudut sehingga semua komponen diagram terlihat.

5.  Klik laporan di luar bagan pai untuk membatalkan pilihan dan pilih bagan kolom bertumpuk di panel **Visualisasi**.

6.  Pengunjung kampus saat ini tercatat dalam jurnal kertas.

7.  Seret bidang **Mulai** dan lepas ke kotak target **Sumbu X**.

8.  Di panel Visualisasi, klik **x** di samping **Tahun** dan **Kuartal** untuk menyisakan hanya total **Bulan** dan **Hari** pada sumbu.

9.  Ubah ukuran bagan sesuai keinginan menggunakan handel sudut.

10. Uji interaktivitas laporan:

    1.  Pilih berbagai potongan bangunan pada diagram pai dan amati perubahan pada laporan waktu.

    2.  Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

    3.  Telusuri ke atas dan ke bawah dan pilih berbagai batang pada bagan kolom waktu untuk mengamati perubahan pada laporan pai.

11. Simpan pekerjaan yang sedang berlangsung dengan menekan **Simpan**.

## <a name="exercise-2-create-power-bi-dashboard"></a>Latihan 2: Membuat Dasbor Power BI

### <a name="task-1-create-power-bi-dashboard"></a>Tugas \#1: Membuat Dasbor Power BI

1.  Anda harus membuka laporan dari tugas sebelumnya.

2.  Select <bpt id="p1">**</bpt>Pin to a dashboard<ept id="p1">**</ept> on the menu. Depending on the layout you may need to press <bpt id="p1">**</bpt>...<ept id="p1">**</ept> to show additional menu items.

3.  Pilih **Dasbor baru** pada perintah **Sematkan ke dasbor**.

4.  Masukkan **Manajemen Kampus** sebagai **Nama dasbor**, tekan **Sematkan langsung**.

5.  A pop-up will prompt you that the dashboard has been created. Select <bpt id="p1">**</bpt>Go to dashboard<ept id="p1">**</ept>.

6.  Uji interaktivitas diagram lingkaran dan batang yang ditampilkan.

### <a name="task-2-add-visualizations-using-natural-language"></a>Tugas \#2: Menambahkan Visualisasi Menggunakan Bahasa Alami

1.  Dalam dasbor **Manajemen Kampus**, pilih bilah **Ajukan pertanyaan tentang data Anda** di bagian atas.

2.  Enter <bpt id="p1">**</bpt>buildings by number of visits<ept id="p1">**</ept> in Q&amp;A area. A bar chart will be displayed.

3.  Pilih **Sematkan visual**.

4.  Pilih **Dasbor yang ada**, pilih dasbor **Manajemen Kampus**, tekan **Sematkan**.

5.  Klik **Keluar dari Q&A**.

Your <bpt id="p1">**</bpt>Campus Management<ept id="p1">**</ept> dashboard should be displayed with three visuals on it. You may have to scroll down to see the new Q&amp;A visual.

Dasbor Anda akan terlihat seperti berikut:

![](media/5-powerbi-result.png)