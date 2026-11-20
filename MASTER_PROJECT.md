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
| Laravel 13 | Backend framework |
| PHP | Bahasa pemrograman |
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
7. Sebelum bekerja, perbarui branch dari `develop` sesuai prosedur tim.
8. Gunakan Pull Request menuju `develop`.
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

## 12. Git Workflow

Branch utama:

- `main`: versi stabil yang siap didemonstrasikan.
- `develop`: branch integrasi seluruh fitur.

Feature branches:

- `feature/member-1-project-management`
- `feature/member-2-ui-foundation`
- `feature/member-3-homepage-catalog`
- `feature/member-4-detail-reader`
- `feature/member-5-database`
- `feature/member-6-rest-api`
- `feature/member-7-oop-architecture`

Alur kerja:

1. Pastikan branch `develop` terbaru.
2. Buat atau perbarui feature branch masing-masing.
3. Kerjakan hanya lingkup tugas yang disepakati.
4. Jalankan pemeriksaan dan pengujian yang relevan.
5. Commit dengan pesan yang menjelaskan perubahan.
6. Push feature branch ke GitHub.
7. Buat Pull Request dari feature branch menuju `develop`.
8. Berikan deskripsi, screenshot bila relevan, hasil test, dan catatan integrasi.
9. Member 1 melakukan review; pemilik kontrak terkait ikut memeriksa bila perubahan menyentuh kontraknya.
10. Merge hanya setelah konflik dan pemeriksaan diselesaikan.
11. Setelah `develop` stabil dan diuji, integrasikan ke `main`.

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
- Pull Request dibuat menuju `develop`.
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
