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
**Fitur:** Navigasi yang menempel di bagian atas (*Sticky-top*) untuk memudahkan akses antar section.

**Penjelasan Kode:** Navbar ini dibuat responsif menggunakan komponen `navbar-collapse` bawaan Bootstrap. Di sini terdapat fitur **Dwibahasa (🇬🇧 EN / 🇮🇩 ID)** yang bisa mengubah dari bahasa Inggris ke bahasa Indonesia, begitupun sebaliknya. Di dalam instance **Vue.js**, saya menyimpan objek `content` yang berisi kamus bahasa Inggris dan Indonesia. 

Saat tombol bahasa diklik, method `toggleLanguage()` dipanggil untuk mengubah nilai variabel `lang`. Karena sifat *reactivity* dari Vue, seluruh teks di HTML yang diikat menggunakan sintaks *mustache* (contoh: `{{ content[lang].role }}`) akan otomatis berganti bahasa saat itu juga secara instan.

### 2. Hero Section (Perkenalan Diri)
**Fitur:** Bagian penyambutan utama dengan latar belakang gambar dan animasi teks. Terdapat tautan aktif ke LinkedIn dan GitHub.

**Penjelasan Kode:** Bagian ini menggunakan sistem Grid Bootstrap (`row` dan `col-lg-6`) agar teks dan foto profil berada bersebelahan di layar PC, namun otomatis menyusun ke bawah saat diakses lewat HP. 

Foto profil diberikan manipulasi CSS class `.rounded-4` dan `.shadow-lg` agar terlihat modern dan menonjol dari latar belakang gelap. Teks deskripsi memanggil data langsung dari Vue instance agar terintegrasi dengan sistem dwibahasa, serta ditambahkan `style="white-space: pre-line;"` di HTML agar format *enter/line-break* dari data JavaScript tetap terbaca.

### 3. About Me (Biografi & Skills)
**Fitur:** Berisi biografi formal sebagai mahasiswa Sistem Informasi UNMUL dan visualisasi tingkat keahlian menggunakan progress bar.

**Penjelasan Kode:** Section ini dibagi menjadi dua bagian utama. Kolom kiri untuk deskripsi personal, dan kolom kanan untuk menampilkan *tech stack* ("Weapon of Choice"). 

Daripada menulis elemen HTML satu per satu untuk setiap logo teknologi, saya memakai *directive* `v-for="weapon in weapons"` dari Vue. Vue akan melakukan *looping* pada array data keahlian saya (Java, Kotlin, Python, TensorFlow, dll) dan otomatis me-render *grid* logo tersebut. Jika nanti saya belajar atau menguasai teknologi baru, saya cuma perlu menambahkannya ke dalam *array* JavaScript, dan tampilan HTML akan otomatis menyesuaikan. *Clean code!*

### 4. Certificates Gallery (Organization Experience)
**Fitur:** Menampilkan sertifikasi atau pengalaman organisasi (INFORSA) dalam bentuk kartu (Card).

**Penjelasan Kode:** Koleksi sertifikat ditampilkan menggunakan komponen **Card** dari Bootstrap yang dibungkus dengan Grid `row-cols`. Sama seperti bagian skills, *card* ini dirender secara dinamis menggunakan `v-for="cert in certificates"`. 

Meskipun saat ini menampilkan satu kartu utama (`photo2.jpg`), bagian ini sudah disiapkan menggunakan `v-for="cert in certificates"`. Hal ini memudahkan saya untuk melakukan *scale-up* atau menambah koleksi sertifikat di masa depan hanya dengan menambah objek baru di bagian data Vue. Setiap kartu dilengkapi dengan efek CSS *hover* yang membuat kartu sedikit terangkat saat disentuh kursor, memberikan kesan interaktif bagi pengguna.

### 5. Footer
**Fitur:** Bagian penutup yang berisi informasi hak cipta dan pengulangan tautan media sosial.

**Penjelasan Kode:** Menggunakan utility spacing Bootstrap dan warna latar `.bg-dark`.

---

## Tampilan Section

| Section | Deskripsi Visual |
| :--- | :--- |
| **Navbar** | <img src="https://github.com/user-attachments/assets/cce5f4e0-40b4-4112-ac8a-1cb2d9b73db4" width="100%" /> |
| **Home** | <img src="https://github.com/user-attachments/assets/7b1cf734-35ee-4b35-9cf1-c5a6a57e7f6d" width="100%" /> |
| **About** | <img src="https://github.com/user-attachments/assets/c3d9e8cd-d976-45e1-ae81-0e964a56d799" width="100%" /> |
| **Certificates** | <img src="https://github.com/user-attachments/assets/2076dd2a-cbea-4e16-9820-d5c3797af434" width="100%" /> |
| **Footer** | <img src="https://github.com/user-attachments/assets/88ad45e0-472a-47b7-aa8a-104afa1172e9" width="100%" /> |

---

## Struktur Folder Proyek
```text
/
├── index.html       # Struktur Utama & Logika Vue JS
├── style.css        # Styling Custom & Animasi
├── README.md        # Dokumentasi Proyek
└── images/          # Folder Aset Gambar
    ├── photo.jpg    # Foto Profil Utama
    └── photo2.png   # Dokumentasi INFORSA
