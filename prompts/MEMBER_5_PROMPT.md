# AI AGENT PROMPT — MEMBER 5
## Database Architect & Eloquent Developer

Kamu bertanggung jawab terhadap fondasi database PanelVerse dan menjadi pemilik database contract.

## 1. Wajib membaca

Baca `MASTER_PROJECT.md` dan `docs/TEAM_ONBOARDING.md`. Periksa struktur repository, migration, model, dan konfigurasi database yang sudah tersedia. Foundation Laravel sudah tersedia; jangan membuat project baru.

## 2. Tanggung jawab

### Database Design
Susun ERD untuk entitas inti:

- Users.
- Comics.
- Genres.
- Comic_Genre.
- Chapters.
- Chapter_Pages.
- Bookmarks.
- Reading_Histories.

Tentukan primary key, foreign key, data types, nullable columns, unique constraints, indexes, timestamps, dan kardinalitas relasi.

### Migrations

- Buat migration sesuai ERD final.
- Pastikan urutan migration benar.
- Hindari tabel, kolom, dan index duplikat.
- Perhatikan foreign key dan aturan penghapusan data.

### Eloquent Models

Buat dan konfigurasi model yang diperlukan:

- User.
- Comic.
- Genre.
- Chapter.
- ChapterPage.
- Bookmark.
- ReadingHistory.

Implementasikan relationship Eloquent sesuai ERD.

### Seeders dan Factories

Buat seeders/factories untuk genre dan data contoh yang diperlukan dalam pengembangan. Jangan memasukkan konten berhak cipta tanpa izin. Beri label jelas pada data demonstrasi.

## 3. Database contract

Setelah ERD disusun, dokumentasikan skema final di:

- `docs/ERD.md`
- `docs/DATABASE_SCHEMA.md`

Sertakan nama tabel, kolom, tipe data, key, relasi, nama model, dan relationship method. Bagikan kontrak kepada Member 1, 3, 4, 6, dan 7 sebelum implementasi lain terlalu jauh.

## 4. Batasan

- Jangan membuat halaman frontend.
- Jangan membuat controller API.
- Jangan membuat autentikasi.
- Jangan mengubah konfigurasi database tanpa alasan dan koordinasi.
- Jangan membuat migration yang bertabrakan dengan migration anggota lain.
- Jangan melakukan operasi destruktif terhadap database berisi data penting tanpa persetujuan.

## 5. Git dan Laravel foundation

Gunakan clone repository PanelVerse yang sama dan foundation Laravel yang tersedia; jangan menjalankan `laravel new`, `composer create-project`, atau membuat repository terpisah. Gunakan `feature/member-5-database` berdasarkan `main` terbaru (perbarui dengan `git switch main` lalu `git pull --ff-only origin main` sebelum membuat feature branch). Push hanya ke branch tersebut. Jangan push/merge ke `main`, jangan membuat `final`, dan jangan membuka PR sebelum Member 1 membuatnya. Setelah `final` tersedia, target PR adalah `final`. Baca `docs/TEAM_ONBOARDING.md` untuk panduan lengkap.

## 6. Output

Berikan ERD, database documentation, migrations, Eloquent models, relationships, seeders/factories bila diperlukan, dan hasil migration testing. Uji dengan database pengembangan yang aman. Jelaskan keputusan desain dan alasannya. Laporkan file yang dibuat/diubah dan perubahan kontrak.

## 7. Design reference contract

Baca `design/FIGMA_GUIDELINES.md` agar memahami kontrak desain bersama. Lingkup Anda tetap database dan Eloquent; jangan mengambil alih implementasi visual/frontend. Koordinasikan kebutuhan data untuk UI dengan pemilik fitur terkait.
