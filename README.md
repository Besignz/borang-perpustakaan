# 📚 Sistem Manajemen Perpustakaan (Koleksi Buku Digital)

Aplikasi web (*Single Page Application*) modern berbasis web statis untuk mengelola entri dan pendataan koleksi buku perpustakaan secara terpusat. Aplikasi ini dirancang dengan antarmuka berselera modern (*Modern Dashboard Style*) menggunakan kombinasi warna *Slate/Deep Blue*, tata letak responsif, serta sistem notifikasi berbasis **Modal Dialog Interaktif**.

---

## ✨ Fitur Utama

Aplikasi ini mengadopsi konsep tata kelola data yang dinamis secara langsung di sisi klien (*client-side*) dengan fitur sebagai berikut:

1. **Dashboard Beranda (Analitik Real-time)**
   * Menampilkan metrik total judul buku yang terdaftar dan akumulasi seluruh stok eksemplar buku.
   * Dilengkapi dengan komponen *Manual Guideline* atau Panduan Alur Penggunaan sistem bagi pengguna awam.
2. **Formulir Input Data Buku (Tambah Buku)**
   * Input data komprehensif: Kode Buku, ISBN, Judul, Pengarang, Penerbit, Tahun Terbit, Kategori, Stok, Nomor Rak, dan Keterangan.
   * **Auto Code Generator:** Membuat kode buku otomatis berformat standar ilmiah (`BK-[Tahun]-[Nomor Urut]`).
   * **Stok Counter Interaktif:** Tombol tambah ($+$) dan kurang ($-$) untuk mempermudah pengaturan jumlah buku fisik.
   * **Validasi Sisi Klien:** Memeriksa kelengkapan kolom wajib (bertanda `*`), duplikasi kode buku, dan format tahun secara instan.
3. **Daftar Koleksi Buku**
   * Menampilkan visualisasi data dalam bentuk tabel yang rapi, padat, dan *scannable*.
   * Dilengkapi dengan badge kategori dinamis dan tombol aksi hapus (*trash icon*) yang interaktif.
4. **Modul Pencarian Fleksibel**
   * Fitur pencarian teks dinamis dengan metode pencarian global (semua kolom) atau pencarian spesifik berbasis filter kategori (Judul, Kode, Pengarang, Kategori).
5. **Sistem Modal Dialog Terintegrasi**
   * Menggantikan notifikasi *toast* melayang dengan *popup* modal di tengah layar.
   * Dilengkapi animasi kompresi skala (*scale-up pop*), efek latar belakang buram (*backdrop-filter blur*), serta perubahan tema warna otomatis (sukses/peringatan).

---

## 🛠️ Teknologi yang Digunakan

Aplikasi ini dibangun murni menggunakan teknologi bawaan peramban web (*native*) tanpa memerlukan dependensi *framework* yang berat:
* **HTML5:** Struktur semantik standar web yang aksesibel.
* **CSS3 (Custom Variables & Flexbox/Grid):** Manajemen gaya visual modern, variabel tema warna premium, serta fleksibilitas tata letak responsif.
* **Tabler Icons:** CDN pustaka grafis ikon vektor yang tajam dan seragam.
* **Vanilla JavaScript (ES6+):** Logika manipulasi DOM, manajemen *state array data*, sistem navigasi tab, dan algoritma penanganan modal.

---

## 🚀 Cara Menjalankan Aplikasi

Aplikasi ini bersifat portabel dan tidak membutuhkan instalasi server lokal (seperti XAMPP/Node.js). Anda dapat menjalankannya langsung di perangkat komputer atau gawai Anda:

1. Unduh atau salin seluruh kode dari file `borang_data_buku_perpustakaan.html`.
2. Simpan berkas tersebut dengan ekstensi `.html` di penyimpanan lokal komputer Anda.
3. Klik ganda (*double click*) pada berkas tersebut, atau klik kanan lalu pilih **Open With** dan pilih peramban web (*browser*) favorit Anda (seperti Google Chrome, Mozilla Firefox, Microsoft Edge, atau Safari).
4. Aplikasi siap digunakan secara penuh.

---

## 📂 Struktur Logika Kode

* `dataBuku`: *Array* global bertipe objek yang bertindak sebagai database lokal sementara untuk menampung rekaman data buku.
* `showView(v)`: Fungsi arsitektur navigasi utama untuk memindahkan visibilitas halaman secara instan tanpa melakukan muat ulang (*reload page*).
* `genKode()`: Fungsi otomatisasi pembangkit kode unik buku perpustakaan.
* `pemicuModal(tipe, judul, pesan)`: Mesin utama untuk memanggil, mengatur teks, dan mengubah palet visual komponen *modal popup overlay* di layar.
* `simpanData()`: Handler pengeksekusi validasi aturan bisnis form sebelum menyuntikkan data baru ke dalam database objek array.
