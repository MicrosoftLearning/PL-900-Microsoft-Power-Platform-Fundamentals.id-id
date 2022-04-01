---
lab:
  title: 'Lab: Memvalidasi lingkungan lab'
  module: 'Module 0: Course introduction'
ms.openlocfilehash: f98bf8aee0be31934acee15f3b5668d3e6e6108a
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898901"
---
<a name="module-0-course-introduction"></a>Modul 0: Pengantar kursus
=================================

<a name="scenario"></a>Skenario
--------

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Pengunjung kampus saat ini tercatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Administrasi kampus ingin memodernisasi sistem pendaftaran pengunjung mereka dengan akses ke gedung dikendalikan oleh personel keamanan dan semua kunjungan harus didaftarkan sebelumnya dan dicatat oleh pemandu mereka.

Sepanjang kursus ini, Anda akan membangun aplikasi dan melakukan otomatisasi untuk memungkinkan administrasi dan personel keamanan Bellows College mengelola dan mengontrol akses ke gedung-gedung di kampus.

Di lab Modul 0 ini, Anda akan memperoleh penyewa percobaan Power Platform dan mengakses pusat administrator Power Platform. Di pusat administrator, Anda kemudian akan membuat lingkungan **Latihan** tempat Anda akan melakukan sebagian besar pekerjaan lab Anda.

## <a name="exercise-1--setup"></a>Latihan 1 – Menyiapkan

### <a name="task-1---acquire-your-microsoft-power-platform-trial-tenant"></a>Tugas 1 - Mendapatkan penyewa percobaan Microsoft Power Platform Anda

1. Salin **kredensial Microsoft 365** Anda dari Host Lab yang Diotorisasi.

2. Navigasikan ke <https://powerapps.microsoft.com> dan klik **Mulai gratis.**

3. Di bawah **Mulai**, masukkan alamat email dari kredensial Microsoft 365 Anda di kotak teks yang bertuliskan **Masukkan alamat email kantor Anda.**

4. Anda melihat permintaan bahwa Anda memiliki akun yang sudah ada dengan Microsoft. Pilih **Masuk.**

5. Masukkan kata sandi yang diberikan oleh Host Lab yang Diotorisasi. 

6. Pilih **Ya** untuk tetap masuk.

7. Lengkapi info akun Anda dan pilih **Mulai** untuk mendaftar percobaan Microsoft Power Platform.  

### <a name="task-2--create-environment"></a>Tugas \#2 – Membuat lingkungan

1. Akses <https://admin.powerplatform.microsoft.com> dan masuk dengan kredensial Microsoft 365 Anda jika diminta lagi.

2. Pilih **Lingkungan** dan klik **+Baru.**

    - Untuk **Nama**, masukkan **[Inisial Saya] Latihan.** (Contoh: Latihan AJ.)
    
    - Untuk **Jenis**, pilih **Percobaan** (jangan pilih opsi Percobaan (berbasis langganan)).
    
    - Ubah tombol dwiarah pada **Buat database untuk lingkungan ini?** menjadi **Ya.**
    
    - Biarkan semua pilihan lainnya sebagai default dan klik **Berikutnya.**
    
    - Pada tab berikutnya, biarkan semua pilihan default dan klik **Simpan.**

3. Lingkungan **Latihan** Anda sekarang akan ditampilkan dalam daftar Lingkungan. 

    > Lingkungan Anda mungkin memerlukan beberapa menit untuk disiapkan. Refresh halaman jika diperlukan.

# <a name="exercise-2-provision-a-power-apps-portal"></a>Latihan \#2: Menyediakan portal Power Apps

**Tujuan:** Menyediakan portal Power Apps dapat memakan waktu. Dalam latihan ini, Anda akan membuat portal Power Apps di lingkungan Anda sehingga proses penyediaan dapat dimulai. Anda akan menggunakan portal ini di lab selanjutnya.

## <a name="task-1-create-power-apps-portal"></a>Tugas \#1: Membuat portal Power Apps

1.  Masuk ke <https://make.powerapps.com>

2.  Jika **Lingkungan** yang ditampilkan di kanan atas bukan lingkungan Latihan Anda, klik untuk memilih Lingkungan Anda.

3.  Pada Beranda, klik panel **Portal dari kosong** di bawah **Buat aplikasi Anda sendiri**

    > Jika Anda tidak melihat opsi ini, coba perkecil.

4.  Memberikan detail portal baru

    -   Masukkan **```Bellows College Visitors```** sebagai **Nama** portal

    -   Memberikan URL unik; **sesuatu**.powerappsportals.com (jika nama telah digunakan, pilih yang lain)

    -   Pilih **Bahasa** portal dasar

    -   Klik **Buat**

    > Proses penyediaan Portal akan berjalan dari 30 hingga 45 menit. Anda tidak perlu menunggu, karena proses ini akan berlanjut sambil beralih ke modul berikutnya.
