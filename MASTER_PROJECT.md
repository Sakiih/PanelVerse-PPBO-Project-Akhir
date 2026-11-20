# MASTER PROJECT — PANELVERSE

**Project:** Shinigami-inspired Clone  
**Project Name:** PanelVerse  
**Project Type:** Web-based Manga, Manhwa & Manhua Reading Platform  
**Framework:** Laravel 13  
**Language:** PHP  
**Database:** MySQL 8  
**Architecture:** MVC + Service Layer + Repository Pattern (where justified)  
**Development Method:** Collaborative Git Workflow

> Dokumen ini adalah sumber kebenaran bersama (*single source of truth*) untuk seluruh anggota dan AI Agent. Jika prompt anggota berbeda dengan dokumen ini, ikuti dokumen induk dan koordinasikan perubahan dengan Member 1.

---

## 1. Project Overview

PanelVerse adalah platform membaca komik digital yang dikembangkan sebagai proyek mata kuliah Pemrograman Berorientasi Objek (PBO). Aplikasi mengadaptasi kebutuhan dan alur umum platform seperti Shinigami, tetapi implementasi, kode, identitas visual, dan aset harus dibuat sendiri atau menggunakan aset yang memang berizin.

Platform menyediakan fitur katalog, pencarian, detail komik, daftar chapter, reader, akun pengguna, bookmark, riwayat membaca, pengelolaan konten, dan REST API.

Fokus proyek bukan hanya menghasilkan aplikasi yang berfungsi, tetapi juga menerapkan empat pilar PBO dan SOLID secara nyata serta dapat dijelaskan saat demonstrasi atau presentasi.

## 2. Project Objectives

1. Membangun aplikasi web menggunakan Laravel 13.
2. Menerapkan Abstraction, Inheritance, Encapsulation, dan Polymorphism.
3. Menerapkan SOLID Principles secara relevan.
4. Menggunakan database relasional MySQL.
5. Mengimplementasikan REST API.
6. Membuat kode modular, mudah diuji, dan mudah dikembangkan.
7. Mengembangkan satu aplikasi melalui satu repository GitHub dengan tujuh feature branches.

## 3. Technology Stack

| Teknologi | Penggunaan |
|---|---|
| Laravel 13.43.0 | Foundation framework yang tersedia di repository |
| PHP 8.3+ | Bahasa pemrograman |
| MySQL 8 | Database |
| Eloquent ORM | Interaksi database |
| Blade | Server-rendered frontend |
| HTML5 | Markup |
| CSS3 | Styling |
| Tailwind CSS | UI styling sesuai konfigurasi proyek |
| JavaScript | Interaksi sisi client |
| REST API | Komunikasi data |
| Composer | Dependency management |
| Git & GitHub | Version control dan kolaborasi |
| Postman / EchoAPI | Pengujian API |

Gunakan versi dependency yang kompatibel dengan Laravel 13 dan versi PHP yang dipasang pada komputer tim. Jangan menambah framework atau mengganti teknologi inti tanpa persetujuan tim.

## 3.1 Laravel Foundation

Repository ini sudah berisi satu Laravel application foundation. Gunakan `artisan`, `composer.json`, `composer.lock`, `package.json`, dan `package-lock.json` yang tersedia. Jangan menjalankan `laravel new`, `composer create-project`, atau membuat repository/project Laravel kedua. Foundation saat ini memuat migration dasar Laravel untuk users, cache, dan jobs; fitur domain dan migration tambahannya dikerjakan sesuai kepemilikan kontrak tim.

Versi runtime yang tercatat saat panduan ini disusun: Laravel 13.43.0, PHP 8.3.36, Composer 2.10.3, Node.js 22.23.4, NPM 10.9.9. Dependency dikunci oleh `composer.lock` dan `package-lock.json`; jangan memperbarui lockfile tanpa alasan dan koordinasi.

## 4. Core Features

### 4.1 Public Features
- Homepage.
- Katalog komik.
- Pencarian komik.
- Filter genre dan jenis komik.
- Detail komik.
- Daftar chapter.
- Reader komik.
- Pagination.

### 4.2 User Features
- Register.
- Login.
- Logout.
- Profil pengguna.
- Bookmark.
- Riwayat membaca.

### 4.3 Admin Features
- Dashboard admin.
- CRUD komik.
- CRUD genre.
- CRUD chapter.
- Pengelolaan halaman chapter.
- Pengelolaan pengguna sesuai hak akses.

### 4.4 REST API
API menyediakan akses data dan operasi yang diperlukan aplikasi sesuai autentikasi dan otorisasi. Endpoint awal ada pada Bagian 9 dan dapat disempurnakan melalui koordinasi tim.

## 5. Object-Oriented Programming Requirements

Implementasi empat pilar PBO harus nyata, relevan, dan dapat ditelusuri pada kode aplikasi. Jangan menambahkan class hanya untuk memenuhi checklist.

### 5.1 Abstraction
Gunakan abstract class atau interface untuk mendefinisikan kontrak atau perilaku umum ketika memang dibutuhkan.

Contoh kandidat: kontrak repository, service contract, atau abstraksi perilaku domain.

### 5.2 Inheritance
Gunakan pewarisan jika terdapat hubungan *is-a* yang benar secara konseptual. Jangan memaksakan semua jenis komik menjadi subclass hanya agar terlihat menerapkan inheritance.

### 5.3 Encapsulation
Gunakan `private`, `protected`, dan `public` secara tepat; lindungi keadaan internal object; validasi perubahan data melalui method yang sesuai; dan hindari akses langsung yang tidak diperlukan.

### 5.4 Polymorphism
Gunakan interface atau abstract class dengan beberapa implementasi yang dapat dipertukarkan. Tunjukkan bagaimana client menggunakan kontrak umum tanpa harus mengetahui class implementasi konkretnya.

## 6. SOLID Principles

Perhatikan lima prinsip berikut:

1. **Single Responsibility Principle (SRP):** satu class memiliki satu alasan utama untuk berubah.
2. **Open/Closed Principle (OCP):** perilaku dapat diperluas tanpa terus mengubah kode stabil yang sudah ada.
3. **Liskov Substitution Principle (LSP):** implementasi turunan dapat menggantikan abstraksi induknya tanpa merusak perilaku yang diharapkan.
4. **Interface Segregation Principle (ISP):** interface tidak memaksa implementor menyediakan method yang tidak dibutuhkannya.
5. **Dependency Inversion Principle (DIP):** modul tingkat tinggi bergantung pada abstraksi, bukan implementasi konkret secara langsung.

Penerapan setiap prinsip harus dapat ditunjukkan melalui class, interface, alur pemanggilan, dan alasan desain.

## 7. Architecture Guidelines

Gunakan struktur konseptual berikut sesuai kebutuhan:

| Komponen | Tanggung jawab |
|---|---|
| Models | Representasi data dan relasi Eloquent |
| Controllers | Menerima HTTP request dan mengembalikan response |
| Services | Business logic yang dipisahkan dari controller |
| Repositories | Abstraksi akses data jika memberi manfaat nyata |
| Interfaces | Kontrak untuk implementasi yang dapat dipertukarkan |
| Form Requests | Validasi input |
| API Resources | Format serialisasi response API |
| Policies / Middleware | Otorisasi dan kontrol akses |

Gunakan dependency injection dan Laravel Service Container. Jangan menaruh seluruh business logic di Controller. Jangan pula membuat Service dan Repository untuk setiap model secara otomatis tanpa kebutuhan yang jelas.

## 8. Database Contract — Initial Proposal

Entitas inti yang direncanakan:

1. `users`
2. `comics`
3. `genres`
4. `comic_genre` (pivot)
5. `chapters`
6. `chapter_pages`
7. `bookmarks`
8. `reading_histories`

Relasi konseptual awal:

- User memiliki banyak bookmark.
- User memiliki banyak reading history.
- Comic memiliki banyak chapter.
- Chapter memiliki banyak chapter pages.
- Comic memiliki banyak genre.
- Genre dapat dimiliki banyak comic.

**Member 5 adalah pemilik database contract** dan bertanggung jawab mengusulkan ERD serta skema final. Setelah disepakati, anggota lain wajib mengikuti nama tabel, kolom, key, dan relasi yang terdokumentasi. Perubahan skema harus dibahas sebelum migration diubah.

## 9. API Contract — Initial Proposal

Prefix API: `/api/v1`

| Method | Endpoint | Tujuan |
|---|---|---|
| GET | `/comics` | Daftar komik |
| GET | `/comics/{slug}` | Detail komik |
| GET | `/comics/{slug}/chapters` | Daftar chapter |
| GET | `/chapters/{id}` | Detail chapter |
| GET | `/chapters/{id}/pages` | Halaman chapter |
| GET | `/genres` | Daftar genre |
| POST | `/register` | Registrasi |
| POST | `/login` | Autentikasi |
| POST | `/logout` | Logout |
| GET | `/user` | Pengguna terautentikasi |
| GET | `/bookmarks` | Bookmark pengguna |
| POST | `/bookmarks` | Tambah bookmark |
| DELETE | `/bookmarks/{id}` | Hapus bookmark |
| GET | `/reading-history` | Riwayat membaca |

Endpoint tambahan, metode autentikasi, bentuk response, pagination, dan aturan akses harus disepakati Member 1, 5, 6, dan 7 serta didokumentasikan di `docs/API_DOCUMENTATION.md`.

## 10. Team Division

| Anggota | Peran | Tanggung jawab utama |
|---|---|---|
| 1 | Project Manager, Analyst & Integrator | Analisis, dokumentasi, koordinasi, review, integrasi |
| 2 | UI/UX & Blade Foundation | Layout, navbar, footer, komponen reusable, styling global |
| 3 | Homepage, Catalog & Search | Homepage, katalog, pencarian, filter, pagination |
| 4 | Comic Detail, Chapter & Reader | Detail komik, chapter listing, reader, navigasi chapter |
| 5 | Database & Eloquent | ERD, migration, model, relasi, seeder, database contract |
| 6 | Backend, Authentication & REST API | Auth, validasi, authorization, API routes/controllers/resources |
| 7 | OOP Architect & SOLID | Abstraction, interface, service, repository, DI, SOLID, UML |

## 11. Integration Contract

Semua anggota bekerja pada **satu Laravel application dan satu repository**.

Aturan integrasi:

1. Jangan membuat repository GitHub terpisah untuk setiap modul.
2. Jangan membuat Laravel project baru di branch masing-masing.
3. Semua perubahan berada dalam struktur proyek yang sama.
4. Jangan mengubah nama tabel, kolom, model, atau relationship tanpa koordinasi.
5. Jangan membuat ulang file yang dimiliki anggota lain.
6. Gunakan namespace, naming, formatting, dan pola response yang konsisten.
7. Sebelum bekerja, perbarui `main` terbaru lalu buat/beralih ke feature branch resmi anggota.
8. Push pekerjaan ke feature branch masing-masing. Setelah Member 1 membuat `final`, ajukan Pull Request menuju `final`.
9. Sertakan ringkasan file yang dibuat/diubah, cara pengujian, dan kebutuhan integrasi.
10. Jika terjadi konflik, koordinasikan; jangan menghapus pekerjaan anggota lain untuk menyelesaikan konflik.
11. Hindari mengedit file bersama pada waktu bersamaan tanpa koordinasi.
12. Jangan commit file rahasia seperti `.env`, token, password, atau kredensial.

### Pemilik kontrak

| Kontrak | Pemilik | Pihak yang harus berkoordinasi |
|---|---|---|
| Database / ERD | Member 5 | Members 3, 4, 6, 7 |
| UI / Blade components | Member 2 | Members 3, 4 |
| API contract | Member 6 bersama Member 1 | Members 3, 4, 7 |
| OOP architecture | Member 7 bersama Member 1 | Members 5, 6 |
| Integration | Member 1 | Semua anggota |

## 12. Git Branch Strategy

Tim **tidak menggunakan branch `develop`**. `main` adalah baseline bersama dan versi utama repository. Setiap anggota bekerja pada feature branch yang ditetapkan. `final` adalah branch integrasi sementara yang hanya dibuat dan dikelola Member 1 ketika seluruh pekerjaan siap diintegrasikan.

Feature branches resmi:

- `feature/member-1-project-management`
- `feature/member-2-ui-foundation`
- `feature/member-3-homepage-catalog`
- `feature/member-4-detail-reader`
- `feature/member-5-database`
- `feature/member-6-rest-api`
- `feature/member-7-oop-architecture`

Workflow anggota:

1. Clone repository yang sama. Clone access tidak otomatis memberikan hak push; pemilik repository harus memberikan role Write.
2. `git switch main`, lalu `git pull --ff-only origin main` sebelum memulai pekerjaan.
3. Buat atau gunakan feature branch resmi anggota berdasarkan `main` terbaru.
4. Kerjakan hanya lingkup dan kontrak yang disepakati.
5. Periksa perubahan, jalankan pemeriksaan relevan, lalu commit.
6. Push hanya ke feature branch milik sendiri. Dilarang push langsung ke `main`.
7. Sebelum Member 1 membuat `final`, anggota belum perlu membuka Pull Request. Jangan membuka PR ke `main`.
8. Setelah Member 1 mengumumkan branch `final`, buka PR feature branch → `final` dengan ringkasan, hasil pemeriksaan, screenshot/API evidence bila relevan, dan catatan integrasi.
9. Member 1 melakukan review/merge PR ke `final`; pemilik kontrak terkait ikut meninjau perubahan yang menyentuh kontraknya.
10. Setelah integrasi diuji, Member 1 membuat PR `final` → `main` dan mengelola merge ke `main`.

Anggota selain Member 1 dilarang membuat branch `final` atau menggabungkan pekerjaan ke `main`. Jangan membuat branch `develop`.

Contoh commit:

- `feat: create comic catalog`
- `feat: implement chapter reader`
- `feat: add comic migrations`
- `feat: implement authentication API`
- `refactor: implement repository abstraction`
- `fix: correct comic relationship`

## 13. Definition of Done

Pekerjaan dinyatakan selesai apabila:

- Fitur sesuai tanggung jawab anggota.
- Kode mengikuti struktur dan kontrak proyek.
- Tidak merusak fitur anggota lain.
- Tidak memiliki error yang diketahui pada lingkup perubahan.
- Validasi dan otorisasi berjalan sesuai kebutuhan.
- Database dan relasi mengikuti database contract.
- API memberikan status dan response yang sesuai jika relevan.
- Pengujian relevan telah dijalankan dan hasilnya dicatat.
- Perubahan sudah di-commit dan di-push.
- Pull Request fitur ditargetkan ke `final` setelah branch tersebut dibuat Member 1; PR `final` → `main` dikelola Member 1.
- Dokumentasi pekerjaan diperbarui.

## 14. AI Agent Rules

Setiap AI Agent wajib:

1. Membaca `MASTER_PROJECT.md` sebelum coding.
2. Membaca prompt anggota yang ditugaskan.
3. Memeriksa struktur repository dan status Git sebelum mengubah file.
4. Memastikan versi Laravel dan dependency dari repository, bukan mengasumsikan.
5. Tidak mengasumsikan file, class, route, tabel, atau komponen sudah tersedia.
6. Tidak mengubah pekerjaan anggota lain tanpa persetujuan.
7. Tidak mengganti teknologi, arsitektur, naming, atau kontrak secara sepihak.
8. Tidak menghapus kode yang tidak berada dalam lingkup tugas.
9. Menjelaskan penerapan PBO dan SOLID jika perubahan menyentuh bagian tersebut.
10. Menjalankan pengujian yang masuk akal dan melaporkan hasil sebenarnya.
11. Melaporkan file yang dibuat/diubah, keputusan teknis, asumsi, masalah, dan pekerjaan yang belum selesai.
12. Tidak mengklaim test, push, atau merge berhasil jika tindakan tersebut belum benar-benar dilakukan.

Jika menemukan kebutuhan yang bertentangan dengan kontrak bersama, hentikan perubahan pada bagian yang berkonflik dan laporkan kepada Member 1.

## 15. Project Principles

- **Consistency before complexity.**
- **Integration before individual perfection.**
- **Understand the code, don't just generate the code.**
- Build one integrated application, not seven separate implementations.

## 16. DESIGN REFERENCE CONTRACT

1. `design/` is the official source of visual references and shared design guidance for PanelVerse. Consult `design/FIGMA_GUIDELINES.md` and `design/ASSET_MANIFEST.md` before visual implementation.
2. Every AI Agent must understand `design/FIGMA_GUIDELINES.md` and honor the scope of its assignment.
3. Members implementing frontend must inspect the references relevant to their assigned pages. Member 4 must note that no reader UI screenshot has yet been verified; comic-page samples are content, not UI references.
4. Do not create a design that conflicts with a relevant reference without Member 1's approval. When a reference is missing or ambiguous, coordinate the decision with Member 1 and Member 2.
5. Communicate design changes to the team and record shared decisions in this document or the design guidance as appropriate.
6. Do not delete original assets without approval. Organized copies do not replace the originals.

## 17. Local Development Setup

Gunakan PHP 8.3+, Composer, Node.js 22/NPM, dan MySQL 8 lokal. Panduan setup Windows PowerShell, konfigurasi `.env`, database, migration, build, server, troubleshooting, dan penjelasan konsep Git tersedia di `docs/TEAM_ONBOARDING.md`. Jangan membagikan `.env` atau APP_KEY. Jangan menggunakan `migrate:fresh` tanpa persetujuan karena perintah itu menghapus tabel dan data.

## 18. Team Onboarding

Setiap anggota wajib membaca dokumen ini dan prompt khususnya. `docs/TEAM_ONBOARDING.md` menjelaskan cara clone, menyiapkan foundation lokal, menjalankan aplikasi, dan menggunakan Git. Setiap AI Agent juga harus menerima `MASTER_PROJECT.md`, prompt anggota terkait, dan panduan onboarding. Untuk pekerjaan UI, baca `design/FIGMA_GUIDELINES.md`; baca `design/ASSET_MANIFEST.md` saat memakai referensi/aset.

## 19. Collaboration Rules

1. Satu repository dan satu Laravel application untuk seluruh anggota.
2. Pertahankan pembagian tanggung jawab di Bagian 10; perubahan lingkup memerlukan persetujuan Member 1.
3. Member 5 memiliki database contract; Member 7 arsitektur OOP/SOLID; Member 6 backend/API yang mengikuti keduanya; Member 2 Blade foundation; Members 3 dan 4 menggunakan foundation itu.
4. Jangan menetapkan kontrak entitas, tabel, route, interface, atau komponen yang bertentangan. Usulkan dan koordinasikan keputusan yang belum ditetapkan kepada Member 1 dan pemilik kontrak terkait sebelum implementasi dependen.
5. Jangan mengambil alih atau menimpa pekerjaan anggota lain. Komunikasikan perubahan yang memengaruhi tim.
6. Jangan commit `.env`, credential, token, atau file rahasia. Jangan membagikan rahasia di chat atau PR.
7. Jangan push langsung ke `main`; hanya Member 1 membuat/mengelola `final` dan integrasi menuju `main`.

## 20. Integration Process

1. Setiap anggota push hasil ke feature branch resminya dan melaporkan kesiapan kepada Member 1. PR ditunda sampai `final` tersedia.
2. Setelah pekerjaan siap, Member 1 memastikan `main` terbaru, membuat `final` berdasarkan `main`, lalu mengumumkan bahwa PR dapat dibuka.
3. Setiap anggota membuka PR feature → `final`; Member 1 meninjau dan menggabungkan setelah konflik, kontrak, dokumentasi, dan pemeriksaan relevan ditangani.
4. Member 1 menguji hasil integrasi di `final` dan mencatat perubahan/masalah.
5. Setelah siap, Member 1 membuka PR `final` → `main`, menyelesaikan review, lalu menggabungkan integrasi. Anggota lain tidak membuat PR menuju `main` dan tidak menggabungkan ke `main`.
