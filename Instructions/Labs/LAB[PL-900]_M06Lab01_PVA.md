---
lab:
  title: 'Lab 8: Cara membangun chatbot dasar'
  module: 'Module 6: Intro to Power Virtual Agents'
ms.openlocfilehash: ed1611f4b1450093a6e95cbb9df7ad7fdc040e86
ms.sourcegitcommit: ef58c858463b890e923ef808b1d43405423943fd
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/27/2022
ms.locfileid: "137898940"
---
# <a name="module-6-intro-to-power-virtual-agents"></a>Modul 6: Pengantar Power Virtual Agents
## <a name="lab-how-to-build-a-basic-chatbot"></a>Lab: Cara membangun chatbot dasar

# <a name="scenario"></a>Skenario

Bellows College adalah organisasi pendidikan dengan beberapa gedung di kampus. Kunjungan kampus saat ini dicatat dalam jurnal kertas. Informasi tidak diambil secara konsisten, dan tidak ada sarana untuk mengumpulkan dan menganalisis data tentang kunjungan di seluruh kampus.

Seperti kebanyakan organisasi, Bellows College dengan cepat menanggapi kekhawatiran dengan informasi yang salah tentang COVID-19, praktik terbaik, jadwal, dan sebagainya. Di lab ini, Anda akan membangun chatbot Power Virtual Agent yang akan mengarah ke halaman Pusat Pengendalian Penyakit dengan pertanyaan dan jawaban terkait status pandemi saat ini. Perguruan tinggi akan menginginkan pengaturan ini sehingga dapat disematkan di situs portal mereka, serta tersedia secara ad hoc karena departemen membuat rencana pembukaan kembali mereka sendiri.

## <a name="high-level-steps"></a>Langkah-langkah tingkat tinggi

Kita akan mengikuti uraian di bawah ini untuk membangun Power Virtual Agent:

  - Mendaftar untuk percobaan Power Virtual Agent

  - Membangun bot menggunakan FAQ

  - Menguji bot

  - Mengubah pesan pembuka default

  - Menerbitkan bot

  - **Tantangan Bonus:** Menyematkan bot di portal Anda

## <a name="prerequisites"></a>Prasyarat

Berikut ini telah diidentifikasi sebagai persyaratan yang harus Anda terapkan untuk menyelesaikan proyek:

  - Penyelesaian **Modul 0 Lab 0 - Memvalidasi lingkungan lab**

  - Penyelesaian **Modul 2 Lab 1 - Pengantar Microsoft Dataverse**

  - Latihan bonus saja: Penyelesaian **Modul 6 Lab 4 - Pengantar Portal Power Apps** 

## <a name="things-to-consider-before-you-begin"></a>Hal-hal yang perlu dipertimbangkan sebelum memulai

Bot bisa sangat berguna dalam banyak skenario berbeda. Berdasarkan apa yang Anda ketahui sejauh ini tentang Bellows College, pertimbangkan di mana lagi di organisasi bot dapat berguna.

# <a name="exercise-1-sign-up-for-pva-and-create-a-new-bot"></a>Latihan \#1: Mendaftar ke PVA dan Membuat Bot Baru

Dalam latihan ini, Anda akan mendaftar untuk percobaan Power Virtual Agents.

1.  Menavigasikan ke [Power Virtual Agents](https://powerva.microsoft.com/)

2.  Klik **Mulai Percobaan**.

3.  Masuk, jika diperlukan.

4. Jendela **Buat bot baru** akan muncul.

5. Masukkan **Bot Krisis** untuk **Nama** dan pilih bahasa.

6. Pilih lingkungan Latihan Anda untuk membuat bot dan klik **Buat**. Tunggu hingga bot dibuat. Klik **Jelajahi bot** jika diminta.

7. Uji bot. Ketik **Halo** di kotak pesan dan klik **Kirim**. Bot akan menyambut Anda dan memberi tahu apa yang bisa dilakukannya.

8. Tutup **Obrolan**.

9. Pilih **Topik**. Bot dilengkapi dengan beberapa contoh topik pengguna dan beberapa topik sistem. Pesan pembuka default datang dari topik sistem.

> Pada latihan berikutnya, Anda akan membuat topik Anda sendiri dari situs FAQ CDC. Jangan keluar dari jendela browser ini.

# <a name="exercise-2-create-topics"></a>Latihan \#2: Membuat Topik

Dalam latihan ini, Anda akan menghasilkan topik dari situs FAQ CDC.

1.  Di tab baru, navigasikan ke situs [FAQ CDC](https://www.cdc.gov/coronavirus/2019-ncov/faq.html) dan periksa apa yang ada di situs tersebut. Anda akan menghasilkan topik Anda dari FAQ ini.

2.  Salin URL.

3.  Kembali ke Power Virtual Agents dan pastikan Anda masih memiliki **Topik** yang dipilih.

4.  Pilih tab **Disarankan**, di bawah **Topik**.

5.  Klik **Mulai.**

6. Tempel URL yang Anda salin di kotak teks **Tautkan ke konten online** dan klik **Tambahkan**. Perhatikan bahwa jika Anda menyalin URL lengkap, https:// akan dicantumkan dua kali. Pastikan bahwa URL hanya mencantumkan protokol satu kali.

7.  Klik **Mulai** dan tunggu. Proses ini memerlukan waktu beberapa menit.

8.  Anda akan mendapatkan beberapa topik yang disarankan yang dibuat untuk Anda. Klik untuk membuka salah satu topik yang disarankan.

9. Anda akan melihat frasa pemicu dan balasan bot. **Klik Tambahkan ke topik.**
    
10. Topik yang disarankan akan ditambahkan ke topik Anda. Pilih semua topik yang disarankan dan klik **Tambahkan ke topik** 

    > Anda dapat memilih semua topik dengan menggunakan ikon di sebelah kiri kolom Nama. Jika Anda menerima pesan kesalahan, coba lagi.

11. Setelah topik yang Disarankan telah ditambahkan, pilih tab **Yang Ada**. Anda akan melihat topik baru dengan status yang diatur ke Nonaktif.

12. Gunakan tombol dwiarah di kolom **Status** untuk mengubah beberapa topik menjadi **Aktif**. 

13. Tulis frasa pemicu untuk salah satu topik yang telah Anda aktifkan sehingga Anda dapat mengujinya nanti.

> Jangan keluar dari jendela browser ini.

# <a name="exercise-3-test-topics"></a>Latihan \#3: Topik Pengujian

Dalam tugas ini, Anda akan menguji topik yang Anda tambahkan.

1.  Klik **Uji bot Anda** di bagian kiri bawah.

2.  Klik **Reset**.

3.  Ketik frasa pemicu yang Anda rekam dari tugas sebelumnya dan klik **Kirim**.

4.  Bot akan memberi Anda informasi yang benar dan menanyakan apakah bot telah menjawab pertanyaan Anda. Klik **Ya**.

5.  Bot akan menanyakan tingkat keberhasilan dalam menjawab pertanyaan. Berikan peringkat yang sangat baik.

6.  Bot akan menanyakan apakah bot dapat membantu Anda dengan hal yang lainnya. Klik **Tidak, terima kasih**.

7.  Bot akan mengakhiri sesi obrolan.

8.  Ketik **halo** dan klik **Kirim**.

9.  Bot akan menyambut Anda dan memberi tahu apa yang bisa dilakukannya. Bot Anda sekarang dapat membantu pengguna dengan FAQ COVID-19, jadi Anda perlu mengubah pesan pembuka di tugas berikutnya. Jangan keluar dari jendela browser ini.

# <a name="exercise-4-change-the-greeting"></a>Latihan \#4: Mengganti Pesan Pembuka

Dalam tugas ini, Anda akan mengubah pesan pembuka menjadi spesifik tentang COVID-19.

1.  Pastikan Anda telah memilih **Topik** dan memilih tab **Yang Ada**.

2.  Ciutkan bagian **Topik Pengguna**.

3.  Klik untuk membuka topik **Pesan Pembuka** dari Topik Sistem. Anda juga dapat menggunakan kotak pencarian untuk **Mencari topik yang ada**.

4.  Topik pesan pembuka memiliki 52 frasa pemicu, klik **Buka kanvas penulisan**.

5.  Mengganti pesan pertama dan mengganti dengan `Hi, I’m a virtual agent. I can tell you about how COVID-19 spreads, how to protect yourself, preparing your home and family for COVID-19, symptoms, testing, and more.`

6.  Klik **Simpan**.

7.  Klik **Uji Bot** jika bot Anda masih terbuka. Klik **Atur Ulang** untuk mengatur ulang obrolan.

8.  Ketik halo dan klik **Kirim**.

9.  Bot sekarang akan membalas dengan pesan pembuka baru.

# <a name="exercise-5-publish-the-bot"></a>Latihan \#5: Menerbitkan Bot

Dalam latihan ini, Anda akan menerbitkan bot.

1.  Pilih **Terbitkan** di bilah navigasi kiri.

2.  Klik **Terbitkan**.

3.  Klik **Terbitkan** lagi dan tunggu hingga penerbitan selesai.

4.  Luaskan **Kelola** di bilah navigasi kiri dan pilih **Saluran**.

5.  Anda akan mendapatkan daftar saluran yang tersedia tempat Anda dapat menerbitkan bot. Pilih **Situs web demo**.

6.  Mengubah pesan selamat datang menjadi `Try my COVID-19 FAQ bot.`

7.  Masukkan yang berikut ini di **Pembuka percakapan**:
    ```
     “Who is at higher risk for serious illness from COVID-19”
     “What does more severe illness mean”
     “What is the CDC doing about COVID-19”
    ```
    
8.  Klik **Simpan**.

9.  Salin **URL**.

> Anda dapat membagikan URL dengan kolega dan mendapatkan umpan balik dari mereka. 

10.  Mulai jendela atau tab browser baru dan navigasikan ke URL yang Anda salin. Situs web demo akan terlihat seperti gambar di bawah ini.

11. Mulai mengobrol dengan bot.  
    
Setelah selesai, bot Anda yang diterbitkan akan terlihat seperti ini:

![Situs web demo bot - cuplikan layar](./media/8-image1.png)

# <a name="challenges"></a>Tantangan 
* Sematkan chatbot Anda di portal Pengunjung Bellows College (informasi selengkapnya tentang cara melakukan hal ini di bawah **Tambahkan bot ke Power Apps** [di sini](https://docs.microsoft.com/en-us/power-virtual-agents/publication-connect-bot-to-web-channels).)
