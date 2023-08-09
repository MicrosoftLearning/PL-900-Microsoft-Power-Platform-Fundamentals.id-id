---
lab:
  title: 'Lab 5: Cara membuat dasbor sederhana'
  module: 'Module 5: Get Started with Power BI'
---

## Lab 5: Cara membuat dasbor sederhana

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberikan penyewa sebagai bagian dari pengiriman pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa tersedia untuk tujuan mendukung lab langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab langsung. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk ekstensi. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak untuk mendapatkan akses dan repositori kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab ini, Anda akan membuat dasbor Power BI yang memvisualisasikan data mengenai kunjungan kampus.

## Langkah-langkah lab tingkat tinggi

Kami akan mengikuti langkah-langkah di bawah ini untuk merancang dan membuat dasbor Power BI:

-   Membuat serta menerbitkan laporan dengan berbagai visualisasi informasi kunjungan kampus

-   Manfaatkan kueri bahasa alami pengguna untuk membuat visualisasi tambahan

## Prasyarat

- Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**
- Menyelesaikan **Modul 2 Lab 1 - Membuat Model Data**

## Hal-hal yang perlu dipertimbangkan sebelum memulai

-   Siapa target audiens laporan?
-   Bagaimana audiens akan menggunakan laporan? Perangkat khusus? Lokasi?
-   Apakah Anda memiliki data yang cukup untuk divisualisasikan?
-   Apa kemungkinan karakteristik yang dapat Anda gunakan untuk menganalisis data tentang kunjungan?

## Latihan 1: Membuat Laporan Power BI

**Tujuan:** Dalam latihan ini, Anda akan membuat laporan Power BI berdasarkan data spreadsheet Excel yang kami gunakan di latihan sebelumnya.

### Tugas \#1: Mempersiapkan layanan Power BI

1.  Anda harus memiliki file visits.pbix yang disimpan di komputer virtual Anda di folder AllFiles di Desktop. Unduh [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) dan simpan ke komputer Anda, jika belum ada.

2.  Buka tab baru dan navigasi ke <https://app.powerbi.com/> dan masuk, jika diperlukan.

3.  Pilih **Ruang kerja saya** dari navigasi sisi kiri.

5.  Pilih **Unggah** lalu **Telusuri**.

6.  Temukan dan pilih file **visits.pbix** yang telah Anda unduh sebelumnya. 

7.  Setelah pemuatan data selesai, pilih laporan **kunjungan** .

    > **Catatan:** Jenis diatur ke **Laporan**, jangan pilih Himpunan Data.

8.  Pilih **Edit**. 

    Jika item menu **Edit** tidak terlihat, pilih elipsis **...** lalu pilih **Edit**.

Anda sekarang telah menyiapkan layanan Power BI untuk digunakan di lab Anda.


### Tugas \#2: Membuat Grafik dan Memvisualisasi Waktu

1.  Pilih ikon **Bagan pai** di panel **Visualisasi** untuk menyisipkan bagan.

2.  Perluas **bc_Visit** di panel **Bidang** . Seret bidang **Bangunan** dan letakkan ke dalam kotak **Legenda** .

3.  Seret bidang **Kunjungi** dan letakkan ke dalam kotak **Nilai** .

4.  Ubah ukuran diagram lingkaran menggunakan handel sudut sehingga semua komponen diagram terlihat.

5.  Klik laporan di luar bagan pai untuk membatalkan pilihannya dan pilih ikon **bagan kolom Tumpuk** di panel **Visualisasi** .

6.  Perluas **bc_Visit** di panel **Bidang** jika belum diperluas. Seret bidang **Kunjungi** dan letakkan ke dalam kotak **sumbu Y** .

7.  Seret bidang **Mulai** dan letakkan ke dalam kotak **sumbu X** .

8.  Di panel **Visualisasi** , pilih **x** di samping **Tahun** dan **Kuartal** untuk hanya menyisakan total **Bulan** dan **Hari** untuk sumbu X.

9.  Ubah ukuran bagan sesuai keinginan menggunakan handel sudut.

10. Uji interaktivitas laporan:

    1.  Pilih irisan bangunan yang berbeda pada bagan pai dan amati perubahan pada bagan kolom Tumpuk.

    2.  Pilih bagan kolom Bertumpuk. Pilih panah atas, untuk **Menelusuri paling detail**. Pilih panah bawah untuk mengaktifkan mode **Telusuri paling detail** , lalu pilih kolom untuk menelusuri paling detail ke tingkat berikutnya (hari).

    3.  Telusuri paling detail dan pilih berbagai batang pada bagan kolom Tumpuk untuk mengamati perubahan pada laporan pai.

11. Simpan pekerjaan yang sedang berlangsung dengan memilih **Simpan laporan ini**.


## Latihan 2: Membuat Dasbor Power BI

### Tugas \#1: Membuat Dasbor Power BI

1.  Anda harus membuka laporan dari tugas sebelumnya.

2.  Pilih **Sematkan ke dasbor** pada menu. Bergantung pada tata letak, Anda mungkin perlu memilih **...** untuk menampilkan lebih banyak opsi.

3.  Pilih **Dasbor baru** pada perintah **Sematkan ke dasbor**.

4.  Masukkan `Campus Management` sebagai **Nama dasbor** dan pilih **Sematkan langsung**.

5.  Jendela pop-up akan muncul dengan pemberitahuan bahwa dasbor telah dibuat. Pilih **Buka dasbor**.

6.  Uji interaktivitas diagram lingkaran dan batang yang ditampilkan.


### Tugas \#2: Menambahkan Visualisasi Menggunakan Bahasa Alami

1.  Dalam dasbor **Manajemen Kampus**, pilih bilah **Ajukan pertanyaan tentang data Anda** di bagian atas.

2.  Masukkan `buildings by number of visits` di area Q&A. Diagram batang akan ditampilkan.

3.  Pilih **Sematkan visual**.

4.  Pilih **Dasbor yang sudah ada**, pilih dasbor **Manajemen Kampus** , pilih **Sematkan**.

5.  Pilih **Keluar dari Q&A**.

Dasbor **Manajemen Kampus** Anda akan ditampilkan dengan tiga visual di atasnya. Anda mungkin harus menggulir ke bawah untuk melihat visual Q&A yang baru.

Dasbor Anda akan terlihat seperti berikut:

![](media/5-powerbi-result.png)
