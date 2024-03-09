---
lab:
  title: 'Lab 5: Cara membangun dasbor sederhana'
  module: 'Module 5: Get Started with Power BI'
---

## Lab 5: Cara membangun dasbor sederhana

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberikan penyewa sebagai bagian dari pengiriman pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa tersedia untuk tujuan mendukung lab langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk ekstensi. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Di lab ini, Anda akan membuat dasbor Power BI yang memvisualisasikan data mengenai kunjungan kampus.

**Langkah-langkah lab tingkat tinggi**

Kami akan mengikuti langkah-langkah di bawah ini untuk merancang dan membuat dasbor Power BI:

- Membuat serta menerbitkan laporan dengan berbagai visualisasi informasi kunjungan kampus

- Manfaatkan kueri bahasa alami pengguna untuk membuat visualisasi tambahan

### Prasyarat

- Penyelesaian **Modul 1 Lab 0 - Memvalidasi lingkungan lab**

**Hal-hal yang perlu dipertimbangkan sebelum Anda mulai**

- Siapa target audiens laporan?

- Bagaimana audiens akan menggunakan laporan? Perangkat khusus? Lokasi?

- Apakah Anda memiliki data yang cukup untuk divisualisasikan?

- Apa kemungkinan karakteristik yang dapat Anda gunakan untuk menganalisis data tentang kunjungan?

## Latihan #1: Membuat Laporan Power BI

**Tujuan:** Dalam latihan ini, Anda akan membuat laporan Power BI berdasarkan data lembar bentang Excel yang kami manfaatkan dalam latihan sebelumnya.

### Tugas #1: Menyiapkan layanan Power BI

1. Anda harus memiliki file visits.pbix yang disimpan di komputer virtual Anda di folder AllFiles di Desktop. Unduh [visits.pbix](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/raw/master/Allfiles/visits.pbix) dan simpan ke komputer Anda, jika belum ada.

1. Buka tab baru dan navigasikan ke https://app.powerbi.com dan masuk, jika diperlukan.

1. Pilih **Ruang** kerja saya dari navigasi sisi kiri.

1. Pilih **Unggah** lalu **Telusuri**.

1. Temukan dan pilih **file visits.pbix** yang telah Anda unduh sebelumnya.

1. Setelah pemuatan data selesai, pilih **laporan kunjungan** .

    >**Catatan:** Jenis diatur ke **Laporan**, jangan pilih Himpunan Data.

1. Pilih **Edit**.

**Jika item menu Edit** tidak terlihat, pilih elipsis **...** lalu pilih **Edit**.

Anda sekarang telah menyiapkan layanan Power BI untuk digunakan di lab Anda.

### Tugas #2: Membuat Bagan dan Visualisasi Waktu

1. **Pilih ikon Bagan** pai di panel **Visualisasi** untuk menyisipkan bagan.

1. Perluas **bc_Visit** di panel **Bidang** . **Seret bidang Bangunan** dan letakkan ke dalam kotak **Legenda**.

1. **Seret bidang Kunjungi** dan letakkan ke dalam kotak **Nilai**.

1. Ubah ukuran diagram lingkaran menggunakan handel sudut sehingga semua komponen diagram terlihat.

1. Klik laporan di luar bagan pai untuk membatalkan pilihannya dan pilih **ikon Bagan** kolom bertumpuk di panel **Visualisasi** .

1. Perluas **bc_Visit** di panel **Bidang** jika belum diperluas. **Seret bidang Kunjungi** dan letakkan ke dalam **kotak sumbu** Y.

1. Seret **bidang Mulai** dan letakkan ke dalam **kotak sumbu** X.

1. Di panel **Visualisasi**, pilih x** di **samping **Tahun** dan **Kuartal** untuk hanya **menyisakan total Bulan** dan **Hari** untuk sumbu X.

1. Ubah ukuran bagan sesuai keinginan menggunakan handel sudut.

1. Uji interaktivitas laporan:

    - Pilih irisan bangunan yang berbeda pada bagan pai dan amati perubahan pada bagan kolom Bertumpuk.

    - Pilih bagan kolom Bertumpuk. Pilih panah atas, untuk **Menelusuri paling detail**. Pilih panah bawah untuk mengaktifkan **mode Telusuri paling detail** , lalu pilih kolom untuk menelusuri paling detail ke tingkat berikutnya (hari).

    - Telusuri paling detail dan pilih berbagai bilah pada bagan kolom Bertumpuk untuk mengamati perubahan pada laporan pai.

1. Simpan pekerjaan yang sedang berlangsung dengan memilih **Simpan laporan** ini.

## Latihan 2: Membuat Dasbor Power BI

### Tugas #1: Membuat Dasbor Power BI

1. Anda harus membuka laporan dari tugas sebelumnya.

1. Pilih **Sematkan ke dasbor** pada menu. Bergantung pada tata letak, Anda mungkin perlu memilih menu **elipsis ...** untuk menampilkan lebih banyak opsi.

1. Pilih **Dasbor baru** pada perintah **Sematkan ke dasbor**.

1. Masukkan Manajemen Kampus sebagai **Nama** dasbor dan pilih **Sematkan langsung**.

1. Jendela pop-up akan muncul dengan pemberitahuan bahwa dasbor telah dibuat. Pilih **Buka dasbor**.

1. Uji interaktivitas diagram lingkaran dan batang yang ditampilkan.

### Tugas #2: Menambahkan Visualisasi Menggunakan Bahasa Alami

1. Dalam dasbor **Manajemen Kampus**, pilih bilah **Ajukan pertanyaan tentang data Anda** di bagian atas.

1. Masukkan bangunan menurut jumlah kunjungan di area Tanya Jawab. Diagram batang akan ditampilkan.

1. Pilih **Sematkan visual**.

1. Pilih **Dasbor** yang sudah ada, pilih **dasbor Manajemen** Kampus, pilih **Sematkan**.

1. Pilih **Keluar dari Q&amp;A**.

Dasbor **Manajemen Kampus** Anda akan ditampilkan dengan tiga visual di atasnya. Anda mungkin harus menggulir ke bawah untuk melihat visual Q&A yang baru.

Dasbor Anda akan terlihat seperti berikut:

[![Cuplikan layar dasbor yang baru saja dibuat](media/lab-5-power-bi-01.png)](https://github.com/MicrosoftLearning/PL-900-Microsoft-Power-Platform-Fundamentals/blob/master/Instructions/Labs/media/5-powerbi-result.png)

 
