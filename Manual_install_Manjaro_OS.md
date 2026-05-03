# 🚀 Panduan Deployment & Migrasi TaskMAN (Versi Lengkap)
**Terakhir Diperbarui:** Minggu, 3 Mei 2026
**Target OS:** Manjaro/Arch Linux (atau Linux lainnya)

Panduan ini disusun berdasarkan pengalaman migrasi nyata untuk menghindari error driver dan perizinan.

---

## 1. Persiapan Server (Sistem Operasi)
Pastikan semua modul PHP yang dibutuhkan sudah terinstall. Di Manjaro/Arch, jalankan:
```bash
sudo pacman -S php php-sqlite php-intl composer
```

## 2. Konfigurasi PHP (`php.ini`)
Ini langkah krusial agar database dan composer tidak error.
1. Buka file konfigurasi: `sudo nano /etc/php/php.ini`
2. **Aktifkan Driver:** Cari dan hapus tanda titik koma (`;`) pada:
   ```ini
   extension=pdo_sqlite
   extension=sqlite3
   extension=intl
   ```
3. **Keamanan (Opsi):** Jika ingin Composer berjalan lancar tanpa batasan, Anda bisa menambahkan `/usr/bin/` ke `open_basedir` atau mengosongkannya (hanya untuk lokal).

## 3. Instalasi Dependency (Composer)
Jika sistem Anda menerapkan `open_basedir`, gunakan perintah bypass ini agar tidak error:
```bash
php -d open_basedir= /usr/bin/composer install --no-dev --optimize-autoloader
```
*Gunakan `--no-dev` hanya jika ingin aplikasi berjalan di mode Produksi (Live).*

## 4. Konfigurasi Lingkungan (`.env.local`)
Buat file `.env.local` di root proyek:
```env
APP_ENV=prod
APP_SECRET=masukkan_kode_acak_disini
DATABASE_URL="sqlite:///%kernel.project_dir%/data/database.sqlite"
```
**PENTING:** Jika Anda menginstall tanpa paket development (`--no-dev`), maka `APP_ENV` **WAJIB** diset ke `prod`.

## 5. Persiapan Database & Aset
Jalankan perintah ini secara berurutan:
1. **Migrasi Database:** `php bin/console doctrine:migrations:migrate --no-interaction`
2. **Kompilasi Aset (PENTING):** `php bin/console asset-map:compile`
3. **Bersihkan Cache:** `php bin/console cache:clear`

## 6. Pengaturan Izin Folder (Permissions)
Agar fitur upload dan login tidak error, jalankan:
```bash
chmod -R 775 var/ public/uploads/ data/
```

## 7. Menjalankan Server di Jaringan Lokal (IP)
Agar aplikasi bisa diakses oleh perangkat lain (HP/Laptop) di IP `192.168.1.63`:
```bash
symfony serve -d --listen-ip=0.0.0.0
```
*   **Akses Lokal:** `http://localhost:8000`
*   **Akses IP:** `http://192.168.1.63:8000`

## 8. Troubleshooting (Masalah Umum)
- **Error: "could not find driver"** -> Ulangi Langkah 2, pastikan `pdo_sqlite` aktif.
- **Error: "DebugBundle not found"** -> Terjadi karena `APP_ENV` masih `dev` padahal paket dev tidak diinstall. Pastikan `APP_ENV=prod` di `.env.local`.
- **Error: "open_basedir restriction"** -> Gunakan prefix `php -d open_basedir= ` saat menjalankan command.

---
*TaskMAN v2.0 - Sistem Manajemen Kantor Mandiri*
