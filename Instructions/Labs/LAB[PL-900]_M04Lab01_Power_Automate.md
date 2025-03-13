---
lab:
  title: 'Lab 4: Cara membangun solusi otomatis'
  module: 'Module 4: Describe building automation with Microsoft Power Automate'
---

# Lab 4: Cara membangun solusi otomatis

**Penyewa WWL - Ketentuan Penggunaan** Jika Anda diberikan penyewa sebagai bagian dari pengiriman pelatihan yang dipimpin instruktur, harap dicatat bahwa penyewa tersedia untuk tujuan mendukung lab langsung dalam pelatihan yang dipimpin instruktur. Penyewa tidak boleh dibagikan atau digunakan untuk tujuan di luar lab praktik. Penyewa yang digunakan dalam kursus ini adalah penyewa uji coba dan tidak dapat digunakan atau diakses setelah kelas berakhir dan tidak memenuhi syarat untuk ekstensi. Penyewa tidak boleh dikonversi ke langganan berbayar. Penyewa yang diperoleh sebagai bagian dari kursus ini tetap menjadi milik Microsoft Corporation dan kami berhak mendapatkan akses dan repositorinya kapan saja. 

## Skenario

Bellows College adalah organisasi pendidikan dengan beberapa kampus dan program. Banyak instruktur dan administrator Bellow Colleges perlu menghadiri acara, dan membeli item. Secara historis, melacak pengeluaran ini merupakan sebuah tantangan. 

Administrasi kampus ingin memodernisasi sistem pelaporan pengeluaran mereka dengan menyediakan cara digital kepada karyawan untuk melaporkan pengeluaran. 

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan karyawan Bellows College mengelola pengeluaran. 

Di lab ini, Anda akan membuat alur Power Automate untuk mengirim salinan laporan pengeluaran melalui email saat mereka membuat Laporan Pengeluaran baru.

## Langkah-langkah lab tingkat tinggi

Berikut ini telah diidentifikasi sebagai persyaratan yang harus Anda terapkan untuk menyelesaikan proyek:

- Karyawan perlu menerima email saat Laporan Pengeluaran dikirimkan. 

### Prasyarat

- Penyelesaian **Modul 1 Lab 0 - Memvalidasi lingkungan lab**

## Latihan 1: Membuat alur Pemberitahuan Laporan Pengeluaran

**Tujuan:** Dalam latihan ini, Anda akan membuat alur Power Automate yang mengimplementasikan persyaratan. 

### Tugas 1: Buat alur

1. Navigasikan ke `https://make.powerapps.com`

1. Anda mungkin perlu mengautentikasi ulang, pilih **Masuk** dan ikuti instruksi, jika diperlukan.

1. Pilih lingkungan **Dev One** di kanan atas jika belum dipilih.

1. Di menu navigasi kiri, pilih **Alur**.

1. Jika diminta, pilih **Mulai**.

1. Pilih **+ Alur baru** dan pilih **Alur cloud otomatis**.

1. Masukkan `Expense Notification` untuk **Nama** alur.

1. Di **Pilih pemicu alur Anda**, cari Dataverse

1. Pilih pemicu **Saat baris ditambahkan, dimodifikasi, atau dihapus**, lalu pilih **Buat**.

1. Isi kondisi pemicu untuk alur:

    1. Pilih **Ditambahkan** untuk **Ubah jenis**
    
    1. Pilih **Laporan Pengeluaran** untuk **Nama tabel**

    1. Pilih **Organisasi** untuk **Cakupan**

    1. Pada langkah pemicu, pilih elipsis (**...**) dan pilih **Ganti Nama**. Ganti nama langkah pemicu menjadi `When an Expense Report is added` 

Ini adalah praktik yang baik, sehingga Anda dan editor alur lainnya dapat memahami tujuan langkah tanpa harus menyelami detailnya.

### Tugas #2: Buat langkah untuk mendapatkan baris Laporan Pengeluaran

1. Pilih **+ Langkah baru**. Langkah ini akan mengambil informasi Laporan Pengeluaran, termasuk alamat email.

1. Telusuri Dataverse

1. Pilih tindakan **Dapatkan baris berdasarkan ID**.

1. Pilih **Pengguna** sebagai **Nama tabel**

1. Pilih bidang **ID Baris**. Perhatikan bahwa jendela muncul untuk memilih **Konten dinamis** atau **Ekspresi**.

1. Di bidang **ID Baris**, pilih **Pemilik (Nilai)** dari daftar **Konten dinamis**. Dalam langkah ini, Anda mencari Pemilik untuk baris Laporan Pengeluaran yang dibuat untuk memicu alur ini. 

1. Pada tindakan **Dapatkan baris berdasarkan ID**, pilih elipsis (**...**) dan pilih **Ganti Nama**. Ganti nama tindakan ini Dapatkan Pemilik

Ini adalah praktik yang baik, sehingga Anda dan editor alur lainnya dapat memahami tujuan langkah tanpa harus menyelami detailnya.

### Tugas #3: Buat langkah untuk mengirim email untuk mengonfirmasi penyerahan laporan pengeluaran

1. Pilih **+ Langkah baru**. Ini adalah langkah yang akan mengirimkan email ke individu yang mengirimkan laporan pengeluaran.

1. Cari email, pilih tindakan **Kirim email (V2)** dari **Office 365 Outlook **.

1. Jika diminta untuk menerima syarat dan ketentuan untuk menggunakan tindakan ini, pilih **Terima**.

1. Pilih bidang **Untuk** dan masukkan alamat email pribadi Anda. (Ada banyak cara agar kita dapat mengisi alamat email secara dinamis, tetapi untuk latihan ini kita akan menetapkannya secara manual.)  

1. **Di bidang Subjek**, masukkan`Your expense report was submitted`

1. Masukkan teks berikut di **Isi Email**:

Konten dinamis perlu ditempatkan di tempat bidang diberi nama dalam tanda kurung. Disarankan untuk menyalin & menempel semua teks terlebih dahulu dan kemudian menambahkan konten dinamis di tempat yang benar.

    Dear {First Name},
    
    Thank you for submitting your expense report for the total amount of {Report Total Amount} with a due date of {Report Due Date}.
    
     
    Best regards,
    Campus Administration
    Bellows College

1. Sorot teks **{First Name}**. Ganti dengan bidang **Nama Depan** dari langkah **Dapatkan pemilik**.

1. Sorot teks **{Laporkan Jumlah Total}**. Ganti dengan **bidang **Laporkan Jumlah** Total Saat Laporan Pengeluaran ditambahkan**.

1. Sorot teks **{Laporkan Tanggal Jatuh Tempo}**. Ganti dengan **bidang Laporkan tanggal** jatuh tempo dari **langkah Saat Laporan Pengeluaran ditambahkan** .

1. Pilih **Simpan**.

Biarkan tab alur ini terbuka untuk tugas berikutnya. Alur Anda akan terlihat seperti berikut:

![Cuplikan layar alur yang baru saja dibuat](media/lab-4-create-an-automated-solution-01.png)

### Tugas #4: Memvalidasi dan menguji alurnya

1. Buka tab baru di browser Anda dan navigasikan ke https://make.powerapps.com

1. Pilih lingkungan **Dev One** di kanan atas jika belum dipilih.

1. Pilih **Aplikasi** dan buka **Aplikasi Pelacak Pengeluaran**.

1. Dengan membiarkan tab browser ini terbuka, navigasikan kembali ke tab sebelumnya dengan alur Anda.

1. Pada bilah perintah, pilih **Uji**. Pilih **Secara Manual** lalu pilih **Uji**.

1. Navigasikan ke tab browser dengan aplikasi berbasis model Anda terbuka.

1. Menggunakan navigasi peta situs di sebelah kiri, pilih**Laporan Pengeluaran**.

1. Pilih tombol **+Baru** untuk menambahkan catatan **Laporan Pengeluaran** baru.

1. Selesaikan**catatan Laporan Pengeluaran** sebagai berikut:

    - **Nama Laporan:** Laporan Pengujian

    - **Tujuan Laporan:** Konferensi

    - **Tanggal jatuh tempo laporan:** Besok

1. Pilih tombol **Simpan &amp; Tutup**.

1. Navigasikan ke tab browser tempat pengujian Alur Anda berjalan. Setelah penundaan singkat, Anda akan melihat alur berjalan. Di sinilah Anda dapat menangkap masalah apa pun dalam alur atau mengonfirmasi bahwa alur berhasil dijalankan.

Setelah penundaan singkat, Anda akan melihat email di kotak masuk Anda. 

>**Catatan:** Ini mungkin masuk ke folder email Sampah Anda.
