# 🎬 React Movie App

Aplikasi web personal untuk mencari daftar film dan menyimpan film favorit, dibangun menggunakan **React** dan **Vite**. Data film diambil secara real-time menggunakan **The Movie Database (TMDB) API**, sementara daftar film favorit disimpan secara persisten di browser menggunakan **Local Storage**.

---

## ✨ Fitur Utama

- **Pencarian Film (Search):** Mencari berbagai judul film dari database TMDB secara cepat.
- **Daftar Film Favorit:** Menandai dan menyimpan film pilihan ke halaman favorit.
- **Penyimpanan Persisten (Local Storage):** Menggunakan React Hook `useEffect` untuk menyinkronkan data favorit ke `localStorage` dan melakukan `JSON.parse()` saat memuat data kembali di halaman favorit agar daftar tidak hilang saat halaman di-refresh.
- **Informasi Film Lengkap:** Menampilkan poster film, judul, tahun rilis, dan rating dari TMDB.

---

## 🛠️ Teknologi yang Digunakan

- **Frontend:** [React](https://react.dev) (Hooks: `useState`, `useEffect`)
- **Build Tool:** [Vite](https://vitejs.dev)
- **API Data Film:** [The Movie Database (TMDB) API](https://themoviedb.org)
- **Storage:** Browser Web Storage API (`localStorage`)
- **Linter:** ESLint

---

## 📁 Struktur Proyek

```text
react-movie-app/
├── public/              # Aset statis publik
├── src/                 # Komponen React, halaman (Home & Favorit), dan logika API
├── .gitignore           # Daftar file/folder yang diabaikan Git
├── eslint.config.js     # Konfigurasi ESLint
├── index.html           # Entry point HTML
├── package.json         # Daftar dependensi dan skrip proyek
├── README.md            # Dokumentasi proyek
└── vite.config.js       # Konfigurasi Vite
```

---

## 🚀 Cara Menjalankan Proyek Secara Lokal

Ikuti langkah-langkah berikut untuk menjalankan aplikasi ini di komputer Anda:

### 1. Prasyarat
- [Node.js](https://nodejs.org) (disarankan versi 18 atau terbaru)
- Akun dan **API Key** gratis dari [TMDB](https://themoviedb.org)

### 2. Clone Repositori
```bash
git clone https://github.com
cd react-movie-app
```

### 3. Instal Dependensi
```bash
npm install
```

### 4. Konfigurasi API Key TMDB
Buat file `.env` di folder utama (*root*) proyek, lalu masukkan API Key TMDB Anda (sesuaikan nama variabelnya dengan yang ada di kode Anda):
```env
VITE_TMDB_API_KEY=masukkan_api_key_tmdb_anda_di_sini
```

### 5. Jalankan Server Development
```bash
npm run dev
```
Buka browser dan kunjungi alamat lokal yang muncul di terminal (biasanya `http://localhost:5173`).

---

## 🧠 Cara Kerja Fitur Favorit

1. **Menyimpan ke Local Storage:** Setiap kali daftar film favorit berubah, `useEffect` akan otomatis menyimpan array film ke `localStorage` dalam format string menggunakan `JSON.stringify()`.
2. **Menampilkan di Halaman Favorit:** Saat halaman favorit dibuka atau di-refresh, aplikasi mengambil data dari `localStorage` dan mengubahnya kembali menjadi array objek JavaScript menggunakan `JSON.parse()` untuk dirender ke layar.
