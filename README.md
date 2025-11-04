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

## Tugas 1
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