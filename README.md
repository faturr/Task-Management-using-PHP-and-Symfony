# 📘 Dokumentasi Lengkap Kemampuan Aplikasi (TaskMAN)
**Versi:** 2.0 (Mei 2026)
**Teknologi:** Symfony 7, PHP 8.4, Bootstrap 5, SQLite

---

## 1. Manajemen Tugas & Proyek (Core Productivity)
Ini adalah modul utama untuk mengelola produktivitas harian dan kolaborasi tim.

### **A. Task Tracker**
- **Pembuatan Tugas:** Membuat tugas dengan judul, deskripsi, prioritas (High, Medium, Low), dan deadline.
- **Status Workflow:** Memantau progres melalui status *To Do, Doing,* dan *Done*.
- **Lampiran & Link:** Mendukung unggah gambar bukti kerja dan tautan website referensi.
- **Filter Pintar:** Menampilkan tugas berdasarkan tenggat waktu (Hari Ini, Minggu Ini, Bulan Ini).

### **B. Grand Plan (Proyek Besar) - NEW**
- **Sistem Payung:** Mengelompokkan banyak tugas ke dalam satu proyek besar (misal: "Event Rakornas").
- **Monitoring Progres:** Dashboard visual yang menampilkan persentase penyelesaian proyek secara otomatis.
- **Timeline Aktivitas:** Menggabungkan seluruh log aktivitas dari semua staf yang terlibat dalam satu halaman.

### **C. Task Marketplace (Claim System) - NEW**
- **Pendelegasian Mandiri:** Manager dapat membuat tugas "Open for Claim" tanpa pemilik.
- **Ambil Tugas:** Staf dapat memilih dan mengambil tanggung jawab atas tugas di marketplace sesuai keahlian/ketersediaan waktu mereka.

---

## 2. Kolaborasi & Komunikasi (Teamwork)
Fitur untuk memastikan tim tetap terhubung dan saling berkoordinasi.

### **A. Sistem Undangan (Invitation)**
- **Kolaborasi:** Pemilik tugas dapat mengundang user lain untuk membantu pengerjaan tugas.
- **Notifikasi:** Badge pada navigasi bar untuk memberi tahu adanya undangan baru.

### **B. Work Logs & Timeline**
- **Catatan Progres:** Setiap pengerjaan dicatat dalam log yang rapi.
- **Kalkulasi Waktu:** Sistem otomatis menghitung durasi kerja dalam menit.
- **Bukti Fisik:** Mendukung banyak lampiran (PDF, JPG, Docs) untuk setiap log kerja.

### **C. Chat & Diskusi (Circles)**
- **Direct Message (DM):** Komunikasi pribadi antar sesama pengguna.
- **Grup Chat (Circles):** Ruang diskusi khusus departemen atau proyek.
- **Real-Time Feel:** Pesan muncul otomatis tanpa refresh halaman (AJAX Polling).

---

## 3. Operasional Kantor (Office Operations)
Modul untuk mendukung kebutuhan administratif dan logistik kantor.

### **A. Kehadiran (Attendance)**
- **Absensi Digital:** Fitur Clock-In dan Clock-Out.
- **Mode Kerja:** Pilihan lokasi kerja WFO (Work From Office) atau WFH (Work From Home).
- **Validasi Foto:** Pengambilan foto saat absensi untuk verifikasi.

### **B. Pengadaan (Procurement)**
- **Pengajuan Barang:** Form pengajuan kebutuhan barang kantor (stok atau baru).
- **Alur Persetujuan:** Antrean khusus bagi Manager untuk menyetujui/menolak permintaan.
- **Serah Terima:** Pencatatan digital saat barang diserahkan ke pengguna, lengkap dengan bukti foto/dokumen.

### **C. Inventaris (Inventory)**
- **Manajemen Stok:** Memantau jumlah barang, satuan, dan riwayat keluar-masuk barang di gudang secara otomatis.

---

## 4. Administrasi & Keamanan (System Admin)
Kontrol penuh bagi administrator untuk menjaga keamanan data.

### **A. Role-Based Access Control (RBAC)**
- **ROLE_ADMIN:** Kendali penuh sistem dan manajemen user.
- **ROLE_MANAGER:** Memantau progres seluruh staf dan kategori.
- **ROLE_LOGISTICS & ROLE_PROCUREMENT:** Akses khusus untuk gudang dan persetujuan barang.
- **ROLE_USER:** Fokus pada tugas pribadi dan kolaborasi yang diizinkan.

### **B. Manajemen Pengguna**
- Tambah/Hapus user, edit peran (roles), dan fitur reset password bagi admin.

### **C. Hari Libur (Holiday Setup)**
- Konfigurasi kalender libur kantor yang terintegrasi dengan sistem.

---

## 5. Keunggulan Teknis
- **Keamanan Data:** Proteksi terhadap SQL Injection, XSS, dan CSRF secara *built-in*.
- **Kecepatan:** Navigasi super cepat menggunakan *Turbo Drive*.
- **Responsif:** Antarmuka yang nyaman diakses dari laptop maupun smartphone.
- **Penyimpanan Lokal:** Session dan Database tersimpan rapi di dalam folder proyek untuk kemudahan *backup*.

---
*Dokumen ini mencakup seluruh fitur yang aktif pada aplikasi TaskMAN per tanggal 3 Mei 2026.*
