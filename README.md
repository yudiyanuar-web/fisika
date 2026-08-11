# 🔬 Simulasi Fisika Interaktif

Website simulasi fisika interaktif bergaya PhET untuk jenjang **SD, SMP, dan SMA**, disusun dengan struktur navigasi 3 tingkat: **Beranda → Topik → Jenjang**. Setiap simulasi jenjang dilengkapi Lembar Kerja Siswa (LKS) dan panduan guru.

## 🧭 Struktur Navigasi

```
index.html  (Beranda: daftar semua topik)
   │
   ├── gerak-gaya/index.html  (Topik: daftar jenjang SD/SMP/SMA)
   │      ├── sd/index.html   → simulasi + tombol lompat ke SMP, SMA, dan Beranda
   │      ├── smp/index.html  → simulasi + tombol lompat ke SD, SMA, dan Beranda
   │      └── sma/index.html  → simulasi + tombol lompat ke SD, SMP, dan Beranda
   │
   └── rangkaian-listrik/index.html  (Topik: daftar jenjang SD/SMP/SMA)
          ├── sd/index.html
          ├── smp/index.html
          └── sma/index.html
```

Di setiap halaman simulasi jenjang, ada dua elemen navigasi:
- **Breadcrumb** di bagian atas (`🏠 Beranda › Nama Topik › Jenjang`) — klik "🏠 Beranda" untuk langsung kembali ke halaman utama.
- **Badge jenjang** di pojok kanan atas (SD / SMP / SMA) — jenjang yang sedang aktif ditandai warna, sedangkan jenjang lain berupa tombol yang langsung membuka simulasi jenjang tersebut.

## 📁 Struktur Folder Lengkap

```
simulasi-fisika/
├── index.html                              # 🏠 Beranda
├── README.md                                # Panduan ini
├── gerak-gaya/
│   ├── index.html                           # Halaman topik (pilih jenjang)
│   ├── sd/index.html + worksheet/*.docx
│   ├── smp/index.html + worksheet/*.docx
│   └── sma/index.html + worksheet/*.docx
└── rangkaian-listrik/
    ├── index.html                           # Halaman topik (pilih jenjang)
    ├── sd/index.html + worksheet/*.docx
    ├── smp/index.html + worksheet/*.docx
    └── sma/index.html + worksheet/*.docx
```

## ➕ Menambahkan Topik Baru di Kemudian Hari

1. Buat folder baru di root, misalnya `optik/`, dengan sub-folder `sd/`, `smp/`, `sma/` di dalamnya (masing-masing berisi `index.html` simulasi + folder `worksheet/`).
2. Buat `optik/index.html` sebagai halaman topik (bisa disalin dan disesuaikan dari `gerak-gaya/index.html`).
3. Di setiap `sd/index.html`, `smp/index.html`, `sma/index.html` topik baru tersebut, tambahkan breadcrumb dan badge jenjang yang saling terhubung (ikuti pola yang sama seperti pada topik Gerak & Gaya atau Rangkaian Listrik).
4. Tambahkan satu kartu baru di `index.html` (Beranda) yang menautkan ke `optik/index.html`, dan hapus kartu "Segera hadir" yang sesuai jika ada.

## 🚀 Cara Menaruh di GitHub & Menghubungkan Domain Sendiri

### 1. Buat Repository di GitHub
1. Masuk ke [github.com](https://github.com) → **New repository**.
2. Beri nama (misalnya `simulasi-fisika`), pilih **Public**, lalu **Create repository**.

### 2. Unggah Seluruh Folder
- Cara mudah: buka repository → **Add file → Upload files** → seret **seluruh isi** folder `simulasi-fisika/` (file `index.html` di root, `README.md`, serta folder `gerak-gaya/` dan `rangkaian-listrik/`) → **Commit changes**.
- Atau via terminal:
  ```bash
  git init
  git add .
  git commit -m "Simulasi Fisika Interaktif - struktur Beranda/Topik/Jenjang"
  git branch -M main
  git remote add origin https://github.com/NAMA-USER/NAMA-REPO.git
  git push -u origin main
  ```

### 3. Aktifkan GitHub Pages
1. Di repository, buka **Settings → Pages**.
2. Pada **Source**, pilih branch `main` dan folder `/ (root)` → **Save**.
3. Setelah 1–2 menit, situs aktif di: `https://NAMA-USER.github.io/NAMA-REPO/`

### 4. Menghubungkan Domain Sendiri
1. Di **Settings → Pages → Custom domain**, ketik domain kamu (misalnya `fisika.namadomainmu.com`) → **Save** (GitHub otomatis membuat file `CNAME`).
2. Di panel DNS penyedia domain kamu, tambahkan:
   - **Subdomain** (misalnya `fisika.namadomainmu.com`): **CNAME record** → `NAMA-USER.github.io`
   - **Domain utama** (misalnya `namadomainmu.com`): **A record** ke 4 IP GitHub Pages:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
3. Tunggu propagasi DNS, lalu centang **Enforce HTTPS** di Settings → Pages.

Setelah aktif, seluruh situs bisa diakses dengan struktur:
- `https://domainmu.com/` → Beranda (pilih topik)
- `https://domainmu.com/gerak-gaya/` → pilih jenjang topik Gerak & Gaya
- `https://domainmu.com/gerak-gaya/sd/` → simulasi jenjang SD
- (pola yang sama berlaku untuk `rangkaian-listrik/` dan topik-topik baru nanti)

## 📝 Lisensi & Penggunaan
Bebas digunakan dan dimodifikasi untuk keperluan pembelajaran di sekolah maupun pribadi.
