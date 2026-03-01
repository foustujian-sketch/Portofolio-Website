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
* **Kode**: Menggunakan komponen `.navbar` dari Bootstrap dengan efek `shadow` untuk memberikan kedalaman visual.

### 2. Section Home (Hero Section)
* **Fitur**: Bagian penyambutan utama dengan latar belakang gambar dan animasi teks. Terdapat tautan aktif ke LinkedIn dan GitHub.
* **Kode**: Menggunakan class `.hero-section` dengan Flexbox (`d-flex`) untuk memusatkan teks secara vertikal dan horizontal. Dilengkapi animasi CSS `@keyframes fadeIn` untuk transisi teks yang halus.

### 3. Section About Me (Biografi & Skills)
* **Fitur**: Berisi biografi formal sebagai mahasiswa Sistem Informasi UNMUL dan visualisasi tingkat keahlian menggunakan progress bar.
* **Kode**: 
    * **Layout**: Menggunakan sistem Grid Bootstrap (`row` dan `col-lg`) untuk memisahkan foto profil dengan teks deskripsi.
    * **Interactivity**: Menggunakan direktif `v-for` dari Vue JS untuk merender daftar keahlian secara dinamis dari objek data.

### 4. Section Certificates (Organization Experience)
* **Fitur**: Menampilkan sertifikasi atau pengalaman organisasi (INFORSA) dalam bentuk kartu (Card).
* **Kode**: Menggunakan komponen `.card` Bootstrap dengan efek hover CSS (`transform: translateY`) untuk memberikan kesan interaktif saat kursor diarahkan ke kartu.

### 5. Footer
* **Fitur**: Bagian penutup yang berisi informasi hak cipta dan pengulangan tautan media sosial.
* **Kode**: Menggunakan utility spacing Bootstrap dan warna latar `.bg-dark`.

---

## Tampilan Section
| Section | Deskripsi Visual |
|---|---|
| **Home** | <img src="https://github.com/user-attachments/assets/7b1cf734-35ee-4b35-9cf1-c5a6a57e7f6d" width="100%" /> |
| **About** | <img src="https://github.com/user-attachments/assets/c3d9e8cd-d976-45e1-ae81-0e964a56d799" width="100%" /> |
| **Certificates** | <img src="https://github.com/user-attachments/assets/2076dd2a-cbea-4e16-9820-d5c3797af434" width="100%" /> |

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
