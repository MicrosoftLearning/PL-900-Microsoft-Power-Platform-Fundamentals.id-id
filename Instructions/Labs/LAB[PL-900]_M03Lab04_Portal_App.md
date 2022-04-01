---
lab:
  title: 'Lab 5: Cara membangun portal Power Apps'
  module: 'Module 3: Get started with Power Apps'
ms.openlocfilehash: 3bbeaad63ccd84285b5471894b8377918433f383
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898925"
---
# <a name="module-3-get-started-with-power-apps"></a>Modul 3: Mulai dengan Power Apps

## <a name="lab-4-how-to-build-a-power-apps-portal"></a>Lab 4: Cara membangun portal Power Apps

# <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Kunjungan kampus saat ini dicatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Pihak administrasi kampus ingin memberikan informasi kepada para pengunjung tentang gedung-gedung di kampus. Para pengunjung akan dapat melihat daftar bangunan di situs web, yang akan dibangun menggunakan portal Power Apps.

Di lab ini, Anda akan menyediakan portal Power Apps dan membuat halaman web portal yang akan menampilkan daftar bangunan di kampus.

# <a name="high-level-lab-steps"></a>Langkah-langkah lab tingkat tinggi

Anda akan mengikuti garis besar di bawah ini untuk mendesain portal Power Apps:

* Menyediakan portal Power Apps di lingkungan Dataverse
* Membuat dan mengonfigurasi halaman web untuk menampilkan daftar bangunan
* Membuat tema baru dan menerapkan ke portal

## <a name="prerequisites"></a>Prasyarat

* Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**
* Penyelesaian **Modul 2 Lab 1 - Pengantar Microsoft Dataverse**

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai

* Aplikasi portal Power Apps selalu dimulai dari template, bukan dari aplikasi kosong. Portal Anda seharusnya dibuat di Modul 0 Lab 0. Setelah Anda menyediakan portal, portal tersebut sudah memiliki halaman, menu, dan tema default. 

# <a name="exercise-1-create-a-portal-webpage"></a>Latihan \#1: Membuat Halaman Web Portal

**Tujuan:** Dalam latihan ini, Anda akan membuat halaman web baru yang akan menampilkan beberapa konten statis serta daftar bangunan dari Dataverse.

## <a name="task-1-navigate-to-portal"></a>Tugas \#1: Mengarahkan ke Portal

1.  Navigasikan ke <https://make.powerapps.com>.

2.  Verifikasi bahwa Anda berada di Lingkungan Latihan Anda. Jika tidak, ubah lingkungan di kanan atas.

3.  Klik **Aplikasi**

4.  Temukan aplikasi yang memiliki **Jenis** **Portal**

5.  Klik pada nama aplikasi untuk membuka portal

    > Anda akan diarahkan ke halaman arahan situs web portal dengan pesan selamat datang. Arahkan portal Anda untuk melihat apa yang dibuat secara default saat menyediakan portal Anda. 

## <a name="task-2-create-a-webpage"></a>Tugas \#2: Membuat Halaman Web

1.  Membuka portal Power Apps Studio

    -   Masuk ke <https://make.powerapps.com> (Anda mungkin masih membuka tab ini)

    -   Pilih **Aplikasi**
    
    -   Temukan aplikasi yang memiliki **Jenis** **Portal**

    -   Klik elipsis ( **...** ) di sebelah kanan nama aplikasi portal dan pilih **Edit**

    > Anda sekarang berada di Studio portal Power Apps. Di sinilah Anda dapat memodifikasi dan membuat konten portal.

2.  Membuat halaman baru

    -   Dari bilah perintah, pilih **Halaman baru**

    - Pilih **Halaman arahan**

3.  Di panel properti, di bagian **Tampilan** ubah **Nama** dari **Halaman baru (1)** menjadi `Building Directory`

4.  Di **Partial URL** ubah nilainya menjadi `building-directory`, tekan tombol Tab (untuk memulai penyimpanan otomatis)

    > Judul halaman sekarang seharusnya bernama **Direktori Gedung**
    
## <a name="task-3-add-static-content"></a>Tugas \#3: Menambahkan Konten Statis

1.  Menambahkan bagian ke halaman web

    - Di kanvas (area yang menampilkan halaman web), pilih bagian halaman yang bukan kolom.

    -   Di toolbelt (sebelah kiri), pilih ikon **Komponen**

    -   Pilih **Bagian dua kolom** dari area **Tata letak bagian**

2.  Menambahkan Teks Statis

    -   Di kanvas (area yang menampilkan halaman web), pilih kolom kiri

    -   Di toolbelt (sebelah kiri), pilih ikon **Komponen**

    -   Pilih **Teks** dari area **Komponen portal**

    -   Di area teks baru, masukkan teks berikut:
          ```
          The following is the building directory.
          ```
    -   Pilih kotak teks di atas yang baru saja Anda edit, dan klik **Hapus** pada bilah perintah untuk menghapus teks default.

3. Menambahkan Gambar

    -   Di kanvas (area yang menampilkan halaman web), pilih kolom kanan

    -   Di toolbelt (sebelah kiri), pilih ikon **Komponen**

    -   Pilih **Gambar** dari area **Komponen portal**

    - Di panel properti, klik **Pilih gambar**. Cari dan pilih **Pages.png**
    
    -   Di panel properti, klik menu dropdown bagian **Pemformatan** dan ubah **Lebar** menjadi 70% (pastikan untuk mengetikkan %). Anda dapat menyesuaikan ukuran gambar sesuai keinginan.

4.  Mengonfigurasi hak untuk menampilkan daftar bangunan 

    -   Dari menu sebelah kiri, klik Pengaturan (simbol roda gigi) dan pilih **Lihat pengaturan lainnya**. Ini akan membuka pengaturan tambahan di tab baru.

    -   Di menu sebelah kiri, gulir ke bawah ke **Keamanan** dan pilih **Izin Tabel**.

    -   Klik **Baru** dan tambahkan nilai berikut:

        -   **Nama**: Menampilkan Daftar Gedung
        -   **Nama Tabel**: Dari dropdown di sisi kanan pilih Gedung (bc_building)
        -   **Situs Web**: Klik pada Kaca Pembesar dan pilih situs web Anda (Pengunjung Bellows College – [nama Anda])
        -   **Jenis Akses**: Global
        -   **Hak istimewa**: Baca
    
    -   Dari menu atas, pilih **Simpan**.
    
    -   Gulir ke bawah ke bagian **Peran Web** dan **Tambahkan Peran Web yang Ada**.
    
    -   Klik kaca pembesar, pilih **Pengguna Anonim** dan klik **Tambahkan**.
    
    -   Dari menu atas, pilih **Simpan & Tutup**.
    
    -   Kembali ke tab sebelumnya.

5.  Klik **Jelajahi situs web** untuk melihat halaman sejauh ini.  Perhatikan bahwa sekarang ada opsi **Direktori Gedung** di menu utama.

    > Anda mungkin perlu mengonfigurasi browser untuk mengizinkan pop-up.

## <a name="task-4-add-a-list-component"></a>Tugas \#4: Menambahkan Komponen Daftar

1.  Arahkan ke tab sebelumnya dan lanjutkan ke langkah #2. Jika tidak tersedia, ikuti langkah-langkah di bawah ini untuk kembali ke lokasi ini.

    -   Masuk ke <https://make.powerapps.com> (Anda mungkin masih membuka tab ini)

    -   Temukan aplikasi yang memiliki **Jenis** **Portal**

    -   Klik elipsis ( **...** ) dan pilih **Edit**
    
    -   Di toolbelt (sebelah kiri), pilih opsi **Halaman** 

    -   Cari dan pilih halaman **Direktori Gedung** yang Anda buat sebelumnya
    
2.  Menambahkan komponen daftar ke halaman Direktori Gedung

    -   Pilih bagian dengan dua kolom.

    -   Di toolbelt (sebelah kiri), pilih ikon **Komponen**

    -   Pilih **Satu bagian kolom** dari area **Tata letak bagian** (bagian akan muncul di bawah gambar dan teks pada halaman web)

    -   Memilih bagian kolom baru di kanvas

    -   Di toolbelt (sebelah kiri), pilih ikon **Komponen**

    -   Pilih **Daftar** dari area **Komponen Portal** (komponen daftar akan muncul di bagian baru)
    
3.  Mengonfigurasi komponen daftar

    -   Memilih komponen daftar di kanvas

    -   Di panel properti (sebelah kanan), masukkan `Buildings List` di bidang **Nama**

    -   Di bidang **Tabel**, pilih **Gedung (bc_building)** dari daftar dropdown

    -   Di **Tampilan**, pilih **Gedung Aktif**

    -   Biarkan pengaturan lainnya diatur ke default
    
4.  Klik **Jelajahi situs web** untuk melihat halaman. 

    > Anda akan melihat daftar Gedung dari database Dataverse muncul di halaman web.

# <a name="exercise-2-change-the-portal-theme"></a>Latihan \#2: Mengubah Tema Portal

**Tujuan:** Dalam latihan ini, Anda akan membuat tema baru yang akan mengubah skema warna portal Anda. 

## <a name="task-1-apply-and-edit-a-theme"></a>Tugas 1: Menerapkan dan Mengedit Tema

1.  Arahkan ke tab sebelumnya dan lanjutkan ke langkah #2. Jika tidak tersedia, ikuti langkah-langkah di bawah ini untuk kembali ke lokasi ini.

    -   Masuk ke <https://make.powerapps.com> (Anda mungkin masih membuka tab ini)

    -   Temukan aplikasi yang memiliki **Jenis** **Portal**

    -   Klik elipsis ( **...** ) dan pilih **Edit**
    
2.  Menerapkan dan menyesuaikan tema dasar

    -   Di toolbelt (sebelah kiri), pilih ikon **Tema**
    
    - Pastikan sakelar untuk **Aktifkan tema dasar** diaktifkan.
    
    -   Pada salah satu prasetel, klik elipsis ( **...** ) dan pilih **Sesuaikan**
    
    -   Salinan tema dasar telah dibuat. 
    
    -   Di panel properti, mainkan dengan mengubah warna dan jelajahi dampak perubahan ini pada portal Anda.
    
    -   Mengganti nama tema Anda
    
3.  Pada bilah perintah, klik **Konfigurasi sinkronisasi**

Tata letak aplikasi Anda akan terlihat mirip dengan struktur berikut:

![Contoh portal](media/9-portallabresult.jpg)

# <a name="challenges"></a>Tantangan

* Buat tampilan Gedung yang berbeda yang hanya menampilkan Nama Gedung. Anda harus memilih **Jelajahi situs web** dari studio Portal untuk melihat perubahannya.
* Pada toolbelt, klik ikon **Tema** dan edit CSS tema kustom Anda.
* Buat halaman dengan komponen **Formulir** dan ubah komponen **Daftar** untuk menambahkan atau mengedit baris Dataverse dengan formulir.
* Aktifkan **Izin Entitas** di komponen **Daftar** **Pengaturan**, apa yang terjadi pada data?
* Di studio Portal, pilih ikon Editor Kode Sumber `</>` untuk melihat sumber halaman. Jika Anda merasa nyaman dengan HTML, buat beberapa modifikasi dan lihat hasilnya.
