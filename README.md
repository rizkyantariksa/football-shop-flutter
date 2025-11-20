# football_shop

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.

## Tugas 7
1. Jelaskan apa itu widget tree pada Flutter dan bagaimana hubungan parent-child (induk-anak) bekerja antar widget.
    Weight tree pada Flutter adalah struktur hierarkis yang menggambarkan bagaimana widget disusun di dalam aplikasi Flutter yang bertujuan untuk membangun, memperbarui, dan merender antarmuka pengguna secara efisien.

    Hubungan parent-child:
    - Parent widget
        Widget yang membungkus atau menampung widget lain yang bertanggung jawab atas tata letak, posisi, dan gaya anak-anaknya
    - Child widget
        Widget yang berada di dalam parent widget yang berperan menentukan isi atau konten visual yang ditampilkan (misalnya teks, gambar, ikon).
    - Aturan hubungan
      Satu widget biasanya memiliki satu parent dan sebuah widget bisa memiliki satu atau beberapa child, tergantung jenis widget-nya (misalnya Row, Column, dan Stack bisa memiliki banyak child).

2. Sebutkan semua widget yang kamu gunakan dalam proyek ini dan jelaskan fungsinya.
   - MaterialApp
      • Menyediakan konfigurasi global seperti tema (ThemeData), judul aplikasi (title), dan halaman awal (home).
      • Berfungsi memastikan aplikasi mengikuti gaya desain Material Design.
   - Scaffold
      • Menyediakan struktur dasar halaman seperti AppBar, body, dan area untuk floating action button atau drawer.
      • Fungsinya sebagai “kerangka” utama tampilan di setiap halaman.
   - AppBar
      • Menampilkan bilah atas aplikasi yang berisi judul (“Football Shop”).
      • Berfungsi memberikan identitas halaman dan tempat untuk menaruh aksi tambahan seperti tombol atau menu.
   - Padding
      • Memberikan jarak di sekeliling konten serta membuat tampilan lebih rapi dan tidak menempel pada tepi layar.
   - Column
      • Menyusun widget secara vertikal.
      • Berfungsi untuk menata Row, Text, dan GridView dalam satu urutan ke bawah.
   - Row
      • Menyusun widget secara horizontal.
      • Berfungsi untuk menampilkan tiga InfoCard sejajar dalam satu baris.
   - SizedBox
      • Memberikan jarak vertikal antar elemen (height: 16.0).
      • Berfungsi untuk mengatur spasi antarkomponen agar tidak terlalu rapat.
   - Center
      • Menempatkan widget anak di tengah area yang tersedia.
   - Text
      • Menampilkan teks statis, seperti nama, NPM, kelas, dan sambutan “Selamat datang di Football Shop”.
   - GridView.count
      • Menyusun daftar widget dalam bentuk grid.
      • Berfungsi untuk menampilkan tiga tombol fitur yaitu All Products, My Products, dan Create Product.
   - Material
      • Memberikan efek Material Design seperti bayangan dan respons sentuhan.
      • Digunakan di dalam ItemCard agar tombol tampak interaktif.
   - InkWell
      • Memberikan efek ripple (gelombang air) saat ditekan.
      • Berfungsi untuk menangani aksi pengguna seperti menampilkan SnackBar saat tombol diklik.
   - SnackBar
      • Menampilkan pesan singkat di bagian bawah layar setelah tombol ditekan.
      • Berfungsi untuk memberi umpan balik kepada pengguna.
   - Card
      • Menampilkan informasi dalam bentuk kotak dengan efek bayangan lembut.
      • Digunakan pada InfoCard untuk menampilkan NPM, nama, dan kelas.
   - Container
      • Berfungsi untuk mengatur ukuran, padding, dan tata letak elemen di dalam Card dan ItemCard.
   - Icon
      • Menampilkan ikon visual pada setiap tombol (store, inventory, add).
      • Membantu pengguna mengenali fungsi tombol dengan cepat.

3. Apa fungsi dari widget MaterialApp? Jelaskan mengapa widget ini sering digunakan sebagai widget root.
    MaterialApp adalah widget utama yang menyediakan kerangka dasar aplikasi Flutter dengan gaya Material Design (standar desain dari Google).

    Alasan MaterialApp sering digunakan sebagai widget root:
    - MaterialApp secara otomatis menyiapkan semua konteks global yang dibutuhkan widget lain (misalnya tema, navigator, dan lokal).
    - Hampir semua widget visual Flutter bergaya Material membutuhkan konteks dari MaterialApp agar berfungsi dengan benar (contohnya Scaffold atau AppBar).
    - Menjadi fondasi utama tempat semua widget lain disusun, memudahkan pengelolaan hierarki UI.
    - Dengan Navigator bawaan, kita bisa berpindah antar halaman tanpa perlu membuat sistem navigasi manual.
    - Memastikan seluruh bagian aplikasi punya gaya, warna, dan perilaku yang konsisten, bahkan saat proyek semakin besar.

4. Jelaskan perbedaan antara StatelessWidget dan StatefulWidget. Kapan kamu memilih salah satunya?
    StatelessWidget:
    - Widget yang tidak memiliki keadaan (state) yang bisa berubah selama aplikasi berjalan.
    - UI-nya selalu tetap kecuali terjadi rebuild dari luar (misalnya karena data parent berubah).
    - Tidak menyimpan data dinamis atau variabel yang bisa berubah seiring waktu.
    - Seluruh tampilan ditentukan sekali saat widget dibuat.
    - Digunakan ketika UI hanya menampilkan data statis atau tidak berubah selama runtime.

    StatefulWidget:
    - Widget yang memiliki state (keadaan internal) yang bisa berubah selama aplikasi berjalan.
    - Dapat menyimpan data dinamis, seperti input pengguna, animasi, atau status koneksi.
    - Memiliki dua bagian, yaitu StatefulWidget dimana struktur/widget tetap dan State yaitu bagian yang dapat berubah.
    - Saat state berubah, Flutter akan memanggil setState() untuk memperbarui UI.
    - Digunakan ketika UI perlu berubah berdasarkan interaksi pengguna atau data yang dinamis.

5. Apa itu BuildContext dan mengapa penting di Flutter? Bagaimana penggunaannya di metode build?
   BuildContext adalah objek yang merepresentasikan posisi sebuah widget di dalam widget tree.
   Secara teknis, Flutter menggunakan BuildContext untuk menemukan hubungan antar-widget seperti siapa parent-nya atau untuk mengakses data yang diwariskan dari atas pohon (seperti tema, navigator, dll).
   BuildContext sangat penting karena:
    - Menentukan letak widget dalam tree.
    - Digunakan untuk mengakses data dari parent widget melalui InheritedWidget (misalnya Theme.of(context) atau MediaQuery.of(context)).
    - Diperlukan dalam navigasi antar halaman dengan Navigator.of(context).push(...).
    - Memungkinkan komunikasi antar widget di berbagai level pohon tanpa harus meneruskan data secara manual.
   
   Penggunaan di metode build:
    - Setiap widget (baik StatelessWidget maupun StatefulWidget) memiliki metode "Widget build(BuildContext context)"
    - Parameter context disini memberikan akses ke lingkungan tempat widget itu berada.
    - Parameter ini digunakan untuk memanggil berbagai metode atau data yang bergantung pada lokasi widget di widget tree.

6. Jelaskan konsep "hot reload" di Flutter dan bagaimana bedanya dengan "hot restart".
    Hot Reload:
    - Hot Reload adalah fitur Flutter yang memungkinkan untuk melihat perubahan kode secara langsung tanpa kehilangan state (keadaan) aplikasi saat ini.
    - Hot Reload bekerja dengan cara Flutter menyuntikkan (inject) perubahan kode Dart baru ke dalam running app tanpa menghentikannya.
    - Bertujuan untuk mempercepat proses pengembangan dan eksperimen desain UI tanpa harus menjalankan ulang seluruh aplikasi.
   
    Hot Restart:
    - Hot Restart adalah proses menjalankan ulang aplikasi dari awal tanpa perlu memuat ulang seluruh engine Flutter seperti pada full restart.
    - Hot Restart bekerja dengan cara Flutter menghentikan eksekusi sementara, menghapus seluruh state aplikasi, dan menjalankan ulang fungsi main().
    - Digunakan saat perubahan kode memengaruhi state global, variabel inisialisasi, atau struktur widget tree awal yang tidak bisa diperbarui hanya dengan Hot Reload.

## Tugas 8
1. Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement() pada Flutter. Dalam kasus apa sebaiknya masing-masing digunakan pada aplikasi Football Shop kamu?
   Navigator.push():
   - Menambahkan/mendorong halaman baru di atas tumpukan (stack) halaman yang sedang aktif.
   - Halaman lama tetap ada di memori, sehingga bisa kembali ke sana menggunakan tombol Back.
   - Digunakan dalam Football Shop dengan pengguna navigasi sementara dan mungkin ingin kembali ke halaman sebelumnya.
      Contoh: Redirect dari Halaman Produk ke Halaman Detail Produk (asumsi bahwa nanti kedepannya ada fitur menampilkan detail produk berdasarkan tugas Django).
   
   Navigator.pushReplacement():
   - Mengganti halaman saat ini dengan halaman baru dan halaman lama dihapus dari stack.
   - Tidak bisa kembali ke halaman sebelumnya karena sudah digantikan.
   - Digunakan dalam Football Shop dengan navigasi menuju halaman utama atau final, dan tidak perlu kembali ke halaman sebelumnya.
      Contoh: Setelah login berhasil, pindah ke HomePage dan tidak perlu kembali ke halaman login lagi (asumsi bahwa nanti kedepannya ada fitur login berdasarkan tugas Django).

2. Bagaimana kamu memanfaatkan hierarchy widget seperti Scaffold, AppBar, dan Drawer untuk membangun struktur halaman yang konsisten di seluruh aplikasi?
   Scaffold
   - Menyediakan struktur dasar untuk setiap halaman Flutter.
   - Bertujuan menjamin setiap halaman memiliki tata letak yang seragam dan mudah diatur.
   - Mengatur berbagai komponen seperti:
      1. appBar (header/judul halaman)
      2. body (isi utama halaman)
      3. drawer (menu navigasi samping)
   
   AppBar
   - Menampilkan judul halaman, ikon navigasi, atau aksi cepat.
   - Memberi tampilan yang konsisten dan familiar di setiap halaman aplikasi.

   Drawer
   - Berfungsi sebagai menu navigasi global untuk berpindah antar halaman besar.
   - Memudahkan pengguna berpindah antar bagian aplikasi tanpa kembali ke halaman utama.

3. Dalam konteks desain antarmuka, apa kelebihan menggunakan layout widget seperti Padding, SingleChildScrollView, dan ListView saat menampilkan elemen-elemen form? Berikan contoh penggunaannya dari aplikasi kamu.
   Padding
   Padding digunakan untuk memberi jarak antar elemen UI, sehingga tampilan tidak saling berhimpitan dan lebih mudah dibaca oleh pengguna.
   Keunggulan:
   - Meningkatkan readability dan kenyamanan visual.
   - Membuat tampilan lebih simetris dan estetis.
   - Menghindari elemen menempel ke tepi layar.
   Contoh penggunaan:
     Di halaman form produk, setiap TextFormField dibungkus Padding agar jarak antar input tidak terlalu rapat.
     Ini memberi pengalaman pengisian form yang lebih nyaman dan teratur.

   SingleChildScrollView
   SingleChildScrollView memungkinkan konten digeser ke atas dan ke bawah jika tinggi elemen melebihi ukuran layar.
   Keunggulan:
   - Mencegah overflow error (elemen keluar dari layar).
   - Ideal untuk form panjang atau popup dialog dengan banyak isi.
   - Menjamin form tetap dapat diakses di layar kecil.
   Contoh penggunaan:
     Di dalam dialog konfirmasi produk tersimpan, SingleChildScrollView digunakan agar semua data produk tetap bisa dilihat meski isinya panjang sehingga tidak ada teks yang terpotong pada layar kecil.

   ListView
   ListView menampilkan sekumpulan widget dalam bentuk daftar vertikal yang bisa di-scroll.
   Keunggulan:
   - Mudah menampilkan daftar item secara dinamis.
   - Mendukung scroll otomatis tanpa perlu SingleChildScrollView.
   - Lebih efisien untuk menampilkan banyak elemen berulang
   Contoh penggunaan:
     Pada Drawer di file left_drawer.dart, ListView digunakan untuk menampilkan daftar menu navigasi seperti Home dan Add Product sehingga menu tetap bisa digulir dan mudah ditambah tanpa khawatir kelebihan panjang layar.

4. Bagaimana kamu menyesuaikan warna tema agar aplikasi Football Shop memiliki identitas visual yang konsisten dengan brand toko?
   Dalam aplikasi Football Shop, warna tema menggunakan variasi warna biru sebagai warna utama di seluruh tampilan aplikasi.
   Pemilihan warna ini dilakukan agar identitas visual aplikasi terasa konsisten dan mencerminkan karakter toko yang modern dan sporty. 
   Warna biru digunakan pada elemen-elemen utama seperti AppBar, DrawerHeader, dan komponen kartu produk, sedangkan teks berwarna putih menjaga kontras agar tetap mudah dibaca.
   Dengan penerapan yang seragam ini, setiap halaman aplikasi memiliki tampilan yang menyatu dan mudah dikenali sebagai bagian dari brand Football Shop.

## Tugas 9
1. Jelaskan mengapa kita perlu membuat model Dart saat mengambil/mengirim data JSON?
   Apa konsekuensinya jika langsung memetakan Map<String, dynamic> tanpa model (terkait validasi tipe, null-safety, maintainability)?
   Beberapa alasan mengapa kita perlu membuat model Dart (class) untuk JSON:
   - Validasi tipe data otomatis
     Dengan model, setiap field sudah punya tipe sehingga Compiler langsung memberi error kalau tipe tidak cocok.
   
   - Null-safety lebih aman
     Model memastikan field tertentu wajib ada (non-nullable). Kalau API mengirim field kosong, maka kasus tersebut harus ditangani.
   
   - Kode lebih mudah dibaca
     Model merepresentasikan struktur data dengan jelas sehinnga orang lainlebih mudah memahami bentuk respon API.
   
   - Mengurangi typo & error saat akses data
     Dengan model, data diakses lewat properti seperti user.name sehingga compiler bisa mengecek apakah field tersebut benar atau tidak.
      
   - Mendapatkan bantuan auto-complete IDE
     Saat pakai model, editor bisa menampilkan saran field. Map tidak memberikan informasi struktur sehingga tidak ada auto-suggestion.
   
   - Mendukung konversi JSON otomatis
     Tools seperti json_serializable atau freezed bisa generate fromJson, toJson, dan copyWith. Ini mengurangi boilerplate dan menjaga konsistensi.
   
   - Reusability & maintainability
     Model bisa digunakan berkali-kali seperti untuk parsing, menyimpan data, dan mengirim data kembali.
   
   Konsekuensi jika langsung memetakan Map<String, dynamic> tanpa model:
   - Tidak ada validasi tipe
     Bisa saja ada salah asumsi tipe data dan baru tahu saat runtime.

   - Null-safety jadi tidak berguna
     Pengecekan null tetap harus secara manual untuk setiap akses field.
   
   - Rentan typo
     Salah menulis key (mis. ["usrename"]) tidak terdeteksi sampai runtime.

   - Kode berantakan dan sulit dipelihara
     Parsing JSON akan tersebar dimana-mana. Ketika API berubah, maka harus mencari dan memperbaiki banyak file.

   - Lebih mudah terjadi bug tersembunyi
     Karena tidak ada class yang menjamin struktur data, error sering lewat tanpa terlihat.

2. Apa fungsi package http dan CookieRequest dalam tugas ini? Jelaskan perbedaan peran http vs CookieRequest.
   http
   Package http digunakan untuk melakukan HTTP request biasa (GET, POST, PUT, DELETE).
   Request tidak otomatis membawa cookie, session, atau authentication.
   Cocok digunakan untuk:
      - Mengambil data publik (tanpa login).
      - Mengirim form atau data JSON sederhana.
      - API yang tidak membutuhkan sesi login.

   CookieRequest
   Digunakan untuk melakukan request yang butuh login & session Django.
   Secara otomatis menyimpan cookie session dari Django, mengirim cookie tersebut di request berikutnya, serta menjaga status login tetap aktif.
   Cocok digunakan untuk:
      - Login pengguna.
      - Mengakses endpoint Django yang butuh autentikasi.
      - Mengirim data ke backend sambil tetap membawa session user.

3. Jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.
   - Menjaga status login tetap konsisten di semua halaman
     Dengan satu instance yang dibagikan, seluruh halaman akan menganggap user tetap login.

   - Menghindari kehilangan cookie atau session
     Cookie login disimpan di dalam instance. Jika membuat instance baru, maka cookie hilang sehingga user harus login ulang.
   
   - Memudahkan akses data user yang sudah login
     CookieRequest juga menyimpan informasi login seperti status login dan data user setelah login. Dengan instance tunggal, semua komponen bisa cek status login secara langsung.
   
   - Menghindari duplikasi request dan error tidak konsisten
     Kalau tiap komponen punya instansinya sendiri, maka bisa terjadi pengiriman cookie yang berbeda-beda, request tidak sinkron, ataupun perubahan state login tidak terbaca oleh komponen lain.

   - Mendukung arsitektur state management Flutter
     Setiap widget bisa akses instance yang sama, memanggil login/logout dari mana saja, serta melakukan request ke backend dengan session yang sama.
   
   - Menghindari overhead pembuatan objek berulang
     CookieRequest tidak dirancang untuk dibuat berkali-kali sehingga memakai satu instance mengurangi overhead dan menjaga performa aplikasi.

4. Jelaskan konfigurasi konektivitas yang diperlukan agar Flutter dapat berkomunikasi dengan Django. Mengapa kita perlu menambahkan 10.0.2.2 pada ALLOWED_HOSTS, mengaktifkan CORS dan pengaturan SameSite/cookie, dan menambahkan izin akses internet di Android?
   Apa yang akan terjadi jika konfigurasi tersebut tidak dilakukan dengan benar?
   Mengapa kita perlu:
   - Menambahkan 10.0.2.2 pada ALLOWED_HOSTS (Django):
     Django hanya akan menerima request dari host yang tercantum di ALLOWED_HOSTS.
     Jika tidak ditambahkan maka Django akan menolak request Flutter karena dianggap “host tidak diizinkan”.
     Ini menyebabkan aplikasi tidak bisa fetch data atau login sama sekali.

   - Mengaktifkan CORS (Cross-Origin Resource Sharing):
     CORS perlu diaktifkan agar Flutter diizinkan mengakses backend Django serta menghindari pemblokiran lintas sumber (origin mismatch).
     Jika tidak ditambahkan maka Request dari Flutter ditolak sehingga Login, fetch data, dan POST form tidak akan bekerja.

   - Mengatur SameSite dan cookie:
     Mobile apps membutuhkan cookie ini agar status login tetap terjaga dan request berikutnya membawa session yang sama.
     Jika tidak ditambahkan maka cookie tidak akan dikirim ke Flutter.
   
   - Menambahkan izin akses internet pada Android:
     Android secara default memblokir semua akses internet dari aplikasi.
     Jika tidak ditambahkan maka semua request HTTP gagal total sehingga aplikasi tidak bisa fetch data dari Django, login, maupun mengirim form atau JSON.

5. Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.
   1. User memasukkan data melalui UI Flutter
      User melakukan aksi sepreti mengetik teks, memilih opsi, menekan tombol submit, dsb.
      Flutter mengumpulkan nilai dari TextField, Dropdown, Checkbox, dsb.

   2. Flutter mengirim data ke Django melalui HTTP / CookieRequest
      Data dikirim dalam bentuk JSON, form data, atau query parameter.
   
   3. Django menerima request dan memproses data
      Di sisi backend, Django menangkap request dari Flutter, mengambil body JSON atau form data, melakukan validasi, kemudian menyimpan hasilnya ke database (jika diperlukan).

   4. Django membuat response dan mengembalikan data ke Flutter
      Setelah diproses, Django mengembalikan respons yaitu status sukses (200, 201), data JSON berisi objek baru, atau pesan error.
   
   5. Flutter menerima JSON dari Django
      Flutter mendapatkan response dalam bentuk Map<String, dynamic>.
   
   6. Flutter mengubah JSON menjadi model
      Agar lebih aman dan rapi, JSON diubah menjadi model Dart. Ini penting untuk Null-safety, validasi tipe, dan mempermudah penggunaan data.

   7. Flutter menampilkan data ke UI
      Model dart tersebut dipakai untuk meng-update state dan menampilkan UI, bisa melalui setState, Provider, Riverpod, Bloc, dsb.

6. Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.
   Register
   - User mengisi form register di Flutter
     User memasukkan username, password, dan data lain. Flutter kemudian mengambil input dari controller (textController.text).

   - Flutter mengirim data ke endpoint register Django
     Flutter mengirim data menggunakan http atau CookieRequest.
   
   - Django menerima request, membuat user
     Di Django, data diterima lalu diverifikasi. Kemudian, Django membuat user baru dan menyimpannya ke database.
   
   - Django mengirim response ke Flutter
     Django mengirim response yang biasanya berupa {"status": "success", "message": "User created"}.

   - Flutter memproses response
     Flutter menampilkan pesan sukses dan mengarahkan ke halaman login.
   
   Login
   - User mengisi form login di Flutter
      User menginput username + password. Flutter kemudian mengirim request login via CookieRequest karena login butuh cookie/session.
   
   - Flutter mengirim data login ke Django
     Request ini berfungsi untuk meminta Django melakukan proses autentikasi.
   
   - Django memvalidasi kredensial
     Django mencari user di database kemudian mengecek passwordnya. Jika passwordnya benar, Django akan membuat session baru dan mengirimkan cookie sessionid ke Flutter.
   
   - CookieRequest menyimpan cookie session
     CookieRequest secara otomatis menyimpan cookie session yang diberikan Django. Semua request berikutnya akan otomatis menyertakan cookie itu.
   
   - Django mengembalikan data user
     Respons ini biasanya dalam format JSON agar mudah diproses oleh Flutter.

   - Flutter menerima status login
     Flutter menyimpan informasi login dalam instance CookieRequest, memperbarui UI, kemudian menavigasi ke halaman menu (dashboard) yang hanya bisa diakses jika login.
   
   Logout
   - User melakukan logout di Flutter
     Flutter mengirim request logout.
   
   - Django menerima request logout
     Django Menghapus session user dari database dan juga cookie session.
   
   - CookieRequest menghapus data session lokal
     Status login pada CookieRequest berubah menjadi false. Cookie internal dihapus sehingga request selanjutnya tidak dianggap login.

   - Flutter menuju halaman login lagi
     UI menu menghilang dan user diarahkan kembali ke halaman login.

7. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).
   - Memastikan deployment proyek tugas Django kamu telah berjalan dengan baik.
      Mengecek tugas Django dan memastikan bahwa setiap fitur yang akan digunakan dalam proyek Flutter bekerja dengan baik.
   
   - Mengimplementasikan fitur registrasi akun pada proyek tugas Flutter.
     Membuat form register di Flutter dan kirim data ke endpoint Django.
   
   - Membuat halaman login pada proyek tugas Flutter.
     Menambahkan UI login dan integrasikan dengan sistem autentikasi Django.
   
   - Mengintegrasikan sistem autentikasi Django dengan proyek tugas Flutter.
     Menggunakan cookie/session dari Django untuk login, register, dan logout di Flutter.

   - Membuat model kustom sesuai dengan proyek aplikasi Django.
      Menambahkan model item sesuai dengan kebutuhan aplikasi (disesuaikan dengan tugas Django sebelumnya).

   - Membuat halaman yang berisi daftar semua item yang terdapat pada endpoint JSON di Django yang telah kamu deploy.
     Mengambil data dari endpoint Django (JSON) dan menampilkannya dalam bentuk list.

   - Membuat halaman detail untuk setiap item yang terdapat pada halaman daftar Item.
     Per item menampilkan name, price, description, thumbnail, category, dan is_featured.

   - Melakukan filter pada halaman daftar item dengan hanya menampilkan item yang terasosiasi dengan pengguna yang login.
     Buat endpoint Django baru di views.py, modifikasi Flutter untuk panggil endpoint yang berbeda, set parameter untuk switch mode.

   - Menjawab beberapa pertanyaan berikut pada README.md pada root folder (silakan modifikasi README.md yang telah kamu buat sebelumnya; tambahkan subjudul untuk setiap tugas).
      Done✅

   