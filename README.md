# Portfolio Website - Abdurrahman Al Farisy

Website Portofolio Statis ini dibangun sebagai representasi profesional mahasiswa **Sistem Informasi Universitas Mulawarman**. Proyek ini menampilkan profil diri, keahlian teknis, dan pengalaman organisasi di **INFORSA**.

## Teknologi yang Digunakan
* **HTML5** - Struktur dasar konten web.
* **CSS3** - Custom styling dan animasi transisi.
* **Bootstrap 5.3** - Framework CSS untuk layouting responsif (Grid System), komponen Navbar, Card, dan Progress Bar.
* **Vue JS 3** - Library JavaScript untuk manajemen data statis secara reaktif (Data Binding).
* **Bootstrap Icons** - Library ikon untuk tautan media sosial.

---

## Penjelasan Fitur & Struktur Kode

### 1. Navbar
* **Fitur**: Navigasi yang menempel di bagian atas (*Sticky-top*) untuk memudahkan akses antar section.
* **Kode**: Navbar ini dibuat responsif menggunakan komponen navbar-collapse bawaan Bootstrap. Di sini terdapat fitur Dwibahasa (🇬🇧 EN / 🇮🇩 ID) yang memungkinkan pengunjung mengubah bahasa dari Inggris ke Indonesia secara instan.

Di dalam instance Vue.js, saya menyimpan objek content yang berisi kamus bahasa untuk setiap teks di website. Saat tombol bahasa diklik, method toggleLanguage() dipanggil untuk mengubah nilai variabel lang. Karena sifat reactivity dari Vue, seluruh teks di HTML yang diikat menggunakan sintaks mustache (contoh: {{ content[lang].aboutTitle }}) akan otomatis berganti bahasa secara real-time tanpa perlu memuat ulang halaman.

### 2. Section Home (Hero Section)
* **Fitur**: Bagian penyambutan utama dengan latar belakang gambar dan animasi teks. Terdapat tautan aktif ke LinkedIn dan GitHub.
* **Kode**: Bagian ini menggunakan sistem Grid Bootstrap (row dan col-lg-6) agar teks perkenalan dan foto profil berada bersebelahan di layar PC, namun otomatis menyusun ke bawah saat diakses lewat HP (Responsif).

Foto profil utama (photo.jpg) diberikan manipulasi CSS class .profile-img-container dengan efek shadow dan sedikit rotasi agar terlihat artistik dan modern. Teks sambutan memanggil data langsung dari Vue instance agar terintegrasi dengan sistem dwibahasa, memastikan pengalaman pengunjung tetap personal sesuai preferensi bahasa mereka.

### 3. Section About Me (Biografi & Skills)
* **Fitur**: Berisi biografi formal sebagai mahasiswa Sistem Informasi UNMUL dan visualisasi tingkat keahlian menggunakan progress bar.
* **Kode**: 
    * **Layout**: Menggunakan sistem Grid Bootstrap (`row` dan `col-lg`) untuk memisahkan foto profil dengan teks deskripsi.
    * **Interactivity**: Section ini dibagi menjadi dua bagian utama. Bagian kiri berisi deskripsi diri saya sebagai mahasiswa Sistem Informasi UNMUL, dan bagian kanan menampilkan keahlian teknis dalam bentuk Progress Bar.

Daripada menulis elemen HTML satu per satu untuk setiap baris skill, saya menggunakan directive v-for="skill in skills" dari Vue. Vue akan melakukan looping pada array data keahlian saya (Sistem Analisis, Database, Frontend, dll) dan otomatis me-render progresnya. Ini menerapkan prinsip Clean Code, di mana jika saya ingin menambah skill baru, saya cukup menambahkannya ke dalam array JavaScript tanpa perlu mengubah struktur HTML lagi.

### 4. Section Certificates (Organization Experience)
* **Fitur**: Menampilkan sertifikasi atau pengalaman organisasi (INFORSA) dalam bentuk kartu (Card).
* **Kode**: Dokumentasi pengalaman organisasi (seperti INFORSA) dan sertifikat ditampilkan menggunakan komponen Card dari Bootstrap yang dibungkus dengan Grid.

Meskipun saat ini menampilkan satu kartu utama (photo2.jpg), bagian ini sudah disiapkan menggunakan v-for="cert in certificates". Hal ini memudahkan saya untuk melakukan scale-up atau menambah koleksi sertifikat di masa depan hanya dengan menambah objek baru di bagian data Vue. Setiap kartu dilengkapi dengan efek CSS hover yang membuat kartu sedikit terangkat saat disentuh kursor, memberikan kesan interaktif bagi pengguna.

### 5. Footer
* **Fitur**: Bagian penutup yang berisi informasi hak cipta dan pengulangan tautan media sosial.
* **Kode**: Menggunakan utility spacing Bootstrap dan warna latar `.bg-dark`.

---

## Tampilan Section
| Section | Deskripsi Visual |
|---|---|
| **Navbar** | <img  src="https://github.com/user-attachments/assets/cce5f4e0-40b4-4112-ac8a-1cb2d9b73db4" width="100%" /> |
| **Home** | <img src="https://github.com/user-attachments/assets/7b1cf734-35ee-4b35-9cf1-c5a6a57e7f6d" width="100%" /> |
| **About** | <img src="https://github.com/user-attachments/assets/c3d9e8cd-d976-45e1-ae81-0e964a56d799" width="100%" /> |
| **Certificates** | <img src="https://github.com/user-attachments/assets/2076dd2a-cbea-4e16-9820-d5c3797af434" width="100%" /> |
| **Footer** | <img src="https://github.com/user-attachments/assets/88ad45e0-472a-47b7-aa8a-104afa1172e9"  width="100%" /> |

---

##  Struktur Folder
```text
/
├── index.html       
├── style.css        
├── README.md        
└── images/         
    ├── photo.jpg    
    └── photo2.jpg  
