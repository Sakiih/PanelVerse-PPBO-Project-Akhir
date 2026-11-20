# PanelVerse Team Onboarding

Panduan ini menyiapkan tiap anggota menjalankan Laravel foundation yang sudah ada dan bekerja pada satu repository. Contoh perintah menggunakan **Windows PowerShell**. `MASTER_PROJECT.md` adalah sumber kebenaran jika ada perbedaan dengan prompt atau catatan lain.

## A. Prerequisites

- PHP **8.3 atau lebih baru**; foundation saat ini menggunakan Laravel **13.43.0**.
- Composer (lockfile proyek dibuat dengan Composer 2.10.3).
- Node.js 22 dan NPM (lockfile proyek dibuat dengan NPM 10).
- MySQL 8 yang berjalan di komputer lokal.
- Git dan akses ke repository.
- VS Code atau editor sejenis.
- AI coding agent pilihan anggota: Codex, OpenCode, Antigravity, atau alat lain.

Versi dependency proyek terkunci di `composer.lock` dan `package-lock.json`. Ikuti versi runtime di atas dan jangan menjalankan `composer update` atau `npm install` untuk mengganti lockfile tanpa koordinasi.

## B. Clone repository

Clone repository yang sama. Contoh SSH:

```powershell
git clone git@github.com:Sakiih/PanelVerse-PPBO-Project-Akhir.git
Set-Location PanelVerse-PPBO-Project-Akhir
```

Clone/read access tidak otomatis memberi hak push. Anggota yang perlu push harus meminta pemilik repository memberi role **Write** dan menyiapkan autentikasi Git (misalnya SSH key) di komputernya. Jangan berbagi private key.

## C. Install PHP dependencies

```powershell
composer install
```

Composer membaca `composer.json` dan `composer.lock`, lalu memasang versi paket PHP yang disepakati ke folder `vendor/`. Folder `vendor/` adalah hasil generate lokal dan tidak perlu dikirim ke Git. Jika Composer melaporkan ekstensi PHP hilang, lihat Troubleshooting.

## D. Environment lokal

Pada clone baru, buat file environment lokal dan key aplikasi:

```powershell
Copy-Item .env.example .env
php artisan key:generate
```

Setiap anggota memakai `.env` dan `APP_KEY` miliknya sendiri. Jangan meminta atau menyalin APP_KEY orang lain. `.env` berisi konfigurasi lokal/rahasia dan tidak boleh dibagikan melalui Git, chat publik, atau Pull Request. Jangan menimpa `.env` yang sudah berisi konfigurasi lokal. `.env.example` adalah template bersama yang boleh berada di Git.

## E. Database MySQL lokal

Buat database bernama `panelverse` di MySQL lokal setiap anggota, misalnya melalui MySQL Workbench atau HeidiSQL. Atur `.env` lokal seperti berikut:

```dotenv
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=panelverse
DB_USERNAME=root
DB_PASSWORD=
```

Contoh tersebut mengikuti template repository. Username/password bisa berbeda pada tiap laptop; isi `DB_PASSWORD` dengan password lokal jika MySQL memerlukannya. Jangan commit nilai credential.

## F. Jalankan migration

```powershell
php artisan migrate
```

Repository saat ini memiliki migration dasar Laravel untuk users, cache, dan jobs; fitur domain akan menambah migration setelah koordinasi Member 5. Migration membuat tabel yang belum ada pada database lokal. **Jangan gunakan `php artisan migrate:fresh` tanpa persetujuan eksplisit**: perintah tersebut menghapus tabel dan data database yang dipilih.

## G. Install frontend dependencies

```powershell
npm ci
```

`npm ci` memasang versi persis yang tercatat di `package-lock.json` dan menjaga hasil install antaranggota konsisten. Perintah ini ditujukan untuk clone baru; jangan mengubah lockfile secara tidak sengaja.

## H. Build frontend

```powershell
npm run build
```

Vite membaca konfigurasi proyek dan menghasilkan file frontend build. Untuk pengembangan dengan hot reload, buka terminal PowerShell kedua dan jalankan `npm run dev`.

## I. Jalankan aplikasi

```powershell
php artisan serve
```

Buka [http://127.0.0.1:8000](http://127.0.0.1:8000). Hentikan server dengan `Ctrl+C` pada terminal yang menjalankannya. `npm run dev`, bila digunakan, berjalan di terminal terpisah dan juga dihentikan dengan `Ctrl+C`.

## J. Troubleshooting umum

| Masalah | Langkah awal |
|---|---|
| `php` tidak ditemukan | Pastikan PHP 8.3+ terpasang dan folder executable PHP masuk `PATH`. Untuk Laragon, coba terminal Laragon, lalu cek `php -v` dan `where.exe php`. |
| Composer dependency error | Cek `php -v` dan `composer -V`; pastikan PHP memenuhi `composer.json`. Jalankan `composer install` dari root yang berisi `composer.json`. Jangan langsung menjalankan `composer update`; kirim pesan error ke Member 1. |
| PHP extension missing | Baca nama extension pada error; pastikan CLI memakai `php.ini` yang benar (`php --ini`) dan aktifkan extension tersebut pada instalasi PHP lokal. Buka ulang terminal lalu cek `php -m`. |
| MySQL tidak berjalan | Mulai service MySQL lokal melalui Laragon/XAMPP/instalasi MySQL, lalu pastikan host/port di `.env` benar. |
| `Access denied` database | Periksa `DB_USERNAME`, `DB_PASSWORD`, host dan port pada `.env`; credential lokal dapat berbeda antaranggota. Jangan mengirim password ke repository. |
| `Unknown database 'panelverse'` | Buat database lokal `panelverse` di MySQL, lalu ulangi `php artisan migrate`. Jangan mengganti konfigurasi ke database orang lain. |
| `npm ci` gagal | Periksa `node -v` (versi 22) dan `npm -v`; pastikan berada di folder dengan `package-lock.json` dan akses registry berfungsi. Simpan output error untuk dibagikan. Jangan menghapus lockfile atau menggantinya dengan `npm install` sebagai jalan pintas. |
| Port 8000 sedang digunakan | Jalankan `php artisan serve --port=8001`, lalu buka URL yang ditampilkan Artisan. |
| Migration error | Periksa database aktif, `.env`, dan pesan error lengkap; jalankan `php artisan migrate:status` untuk melihat migration. Koordinasikan perubahan schema dengan Member 5. Jangan gunakan `migrate:fresh` atau menghapus database untuk mengatasi error. |

## Git Onboarding

### Alur branch resmi

- `main` adalah baseline bersama dan versi utama repository.
- Setiap anggota bekerja pada satu feature branch sesuai namanya di bawah.
- `final` adalah branch integrasi sementara yang **hanya dibuat Member 1** setelah semua pekerjaan siap diajukan. Jangan membuatnya lebih awal.
- Tidak ada branch `develop` dalam workflow ini.
- Anggota boleh push feature branch masing-masing. Sebelum branch `final` tersedia, belum perlu membuat Pull Request.
- Setelah `final` dibuat oleh Member 1, setiap anggota membuka PR dari feature branch masing-masing dengan target `final`.
- Jangan membuat PR ke `main`, jangan push langsung ke `main`, dan jangan membuat/merge ke `final` selain melalui peran integrasi Member 1.

### Nama feature branch

| Anggota | Branch |
|---|---|
| 1 | `feature/member-1-project-management` |
| 2 | `feature/member-2-ui-foundation` |
| 3 | `feature/member-3-homepage-catalog` |
| 4 | `feature/member-4-detail-reader` |
| 5 | `feature/member-5-database` |
| 6 | `feature/member-6-rest-api` |
| 7 | `feature/member-7-oop-architecture` |

### Mulai pekerjaan

Di clone baru, perbarui `main`, lalu buat feature branch sendiri. Contoh Member 4:

```powershell
git switch main
git pull --ff-only origin main
git switch -c feature/member-4-detail-reader
```

Ganti nama branch dengan branch resmi anggota. Jika branch milikmu sudah ada secara lokal, gunakan `git switch feature/member-4-detail-reader` (tanpa `-c`) setelah memperbarui `main`; jangan membuat branch duplikat. Sebelum mulai, `git status` untuk memastikan perubahan lokal aman.

### Commit dan push

Stage file lingkup pekerjaan yang sudah ditinjau, buat commit, lalu push ke branch milikmu. Contoh:

```powershell
git status
git add resources/views/path-file-yang-diubah.blade.php
git commit -m "feat: implement comic reader"
git push -u origin feature/member-4-detail-reader
```

Gunakan path file yang benar-benar kamu ubah; jika menggunakan `git add .`, periksa `git status` dahulu dan pastikan `.env`, credential, serta file sementara tidak ikut di-stage. Push pertama memakai `-u`; push berikutnya dapat memakai `git push` saat masih berada di branch tersebut.

### Istilah Git

- **Clone:** membuat salinan repository ke komputer sendiri.
- **Pull:** mengambil dan menggabungkan commit remote ke branch lokal saat ini. `git pull --ff-only origin main` memperbarui `main` tanpa membuat merge commit lokal.
- **Branch:** jalur kerja terpisah agar perubahan anggota tidak bercampur sebelum review.
- **Commit:** rekaman perubahan lokal dengan pesan yang menjelaskan pekerjaan.
- **Push:** mengirim commit branch lokal ke GitHub.
- **Pull Request (PR):** permintaan untuk meninjau dan menggabungkan perubahan antarbranch di GitHub. Dalam workflow ini target feature PR adalah `final`, hanya setelah branch itu dibuat.
- **Merge:** menggabungkan perubahan PR ke branch target setelah review. Member 1 mengelola merge ke `final` dan integrasi `final` ke `main`.

### Kapan PR dibuat

Sebelum `final` ada, push feature branch dan koordinasikan progres kepada Member 1; jangan menargetkan `main`. Ketika semua feature siap, Member 1 membuat `final` berdasarkan `main` terbaru dan mengumumkannya. Setiap anggota lalu membuka PR feature → `final`. Setelah PR ditinjau dan integrasi diuji, Member 1 membuka PR `final` → `main`, lalu mengelola merge ke `main`. Tidak ada anggota yang melakukan push langsung ke `main`.

## AI Agent onboarding

Berikan kepada AI Agent:

1. `MASTER_PROJECT.md`.
2. Prompt anggota yang sesuai (`prompts/MEMBER_1_PROMPT.md` sampai `MEMBER_7_PROMPT.md`).
3. `docs/TEAM_ONBOARDING.md` untuk aturan repository/Git.
4. `design/FIGMA_GUIDELINES.md` untuk tugas UI; `design/ASSET_MANIFEST.md` bila tugas memakai aset/referensi.

Instruksi ini berlaku untuk Codex, OpenCode, Antigravity, dan AI coding agent lainnya. Agent harus memeriksa repository dan status Git, memakai Laravel foundation yang ada, tidak menjalankan `laravel new`/`composer create-project`, tidak membuat repository terpisah, tidak mengambil alih pekerjaan anggota lain, mengikuti kontrak bersama, dan melaporkan file serta pemeriksaan/test yang benar-benar dijalankan. Jangan pernah mengklaim test, push, merge, atau PR berhasil jika belum dilakukan.

## Koordinasi kontrak dan kepemilikan

- **Member 5** memiliki database contract (ERD, tabel, kolom, relasi, migration).
- **Member 7** memiliki arsitektur OOP/SOLID; koordinasikan interface/service dengan Member 6.
- **Member 6** membangun backend/API sesuai database contract dan arsitektur yang disepakati.
- **Member 2** memiliki Blade foundation; Member 3 dan 4 menggunakan layout dan reusable components yang disepakati.
- **Member 1** mengelola koordinasi dan integrasi final.

Jangan membuat dua kontrak berbeda untuk entitas, tabel, route, atau interface yang sama. Jika keputusan belum ditetapkan, tulis usulan dan koordinasikan kepada Member 1 serta pemilik kontrak terkait sebelum implementasi yang bergantung padanya.
