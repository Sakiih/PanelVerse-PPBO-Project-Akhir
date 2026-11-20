# PanelVerse — PBO Team Prompt Pack

Paket ini berisi dokumen induk dan tujuh prompt AI Agent untuk proyek Shinigami-inspired clone bernama **PanelVerse**.

## Isi paket

- `MASTER_PROJECT.md` — sumber kebenaran bersama untuk tujuan, teknologi, fitur, PBO, SOLID, database, API, pembagian tim, dan workflow Git.
- `prompts/MEMBER_1_PROMPT.md` sampai `prompts/MEMBER_7_PROMPT.md` — instruksi khusus untuk masing-masing anggota.
- `docs/` — template dokumen yang akan diisi dan dipelihara selama pengembangan.

## Cara menggunakan

1. Masukkan seluruh isi paket ke root repository PanelVerse.
2. Pastikan `MASTER_PROJECT.md` berada tepat di root repository.
3. Bagikan prompt sesuai nomor anggota. Jangan tertukar.
4. Setiap anggota memberikan `MASTER_PROJECT.md` dan prompt khususnya kepada AI Agent.
5. Setiap Agent harus memeriksa repository dan branch sebelum mengedit kode.
6. Sepakati database contract, UI contract, API contract, dan OOP architecture sebelum pengembangan paralel terlalu jauh.
7. Anggota bekerja pada feature branch masing-masing dan membuka Pull Request menuju `develop`.
8. Member 1 melakukan review dan integrasi.

## Pembagian anggota

| Anggota | Prompt | Tugas |
|---|---|---|
| 1 | `prompts/MEMBER_1_PROMPT.md` | Project Manager, Analyst & Integrator |
| 2 | `prompts/MEMBER_2_PROMPT.md` | UI/UX & Blade Foundation |
| 3 | `prompts/MEMBER_3_PROMPT.md` | Homepage, Catalog & Search |
| 4 | `prompts/MEMBER_4_PROMPT.md` | Comic Detail, Chapter & Reader |
| 5 | `prompts/MEMBER_5_PROMPT.md` | Database & Eloquent |
| 6 | `prompts/MEMBER_6_PROMPT.md` | Backend, Authentication & REST API |
| 7 | `prompts/MEMBER_7_PROMPT.md` | OOP Architect & SOLID |

## Catatan integrasi penting

Pembagian tugas membagi **tanggung jawab**, bukan membagi aplikasi menjadi tujuh project. Semua anggota harus bekerja di repository dan Laravel application yang sama.

Sebelum fitur dikembangkan secara penuh, tim perlu mengesahkan:

- ERD dan nama tabel/kolom dari Member 5.
- Layout dan nama Blade components dari Member 2.
- Endpoint, autentikasi, dan format API dari Member 6.
- Kontrak interface, service, repository, dan dependency injection dari Member 7.

MASTER_PROJECT adalah rancangan awal. Keputusan final yang telah disetujui tim harus dicatat kembali di dokumen induk agar semua anggota memakai versi kontrak yang sama.

## Git branches

- `main`: versi stabil.
- `develop`: integrasi.
- `feature/member-1-project-management`
- `feature/member-2-ui-foundation`
- `feature/member-3-homepage-catalog`
- `feature/member-4-detail-reader`
- `feature/member-5-database`
- `feature/member-6-rest-api`
- `feature/member-7-oop-architecture`

Jangan commit `.env`, token, password, atau kredensial ke repository.
