# PanelVerse — Database Schema

**Pemilik dokumen:** Member 5  
**Status:** Draft — isi setelah ERD disepakati.

Untuk setiap tabel, catat:

- Nama tabel.
- Tujuan tabel.
- Kolom dan tipe data.
- Primary key.
- Foreign key dan aturan referensial.
- Unique constraint dan index.
- Nullable/default values.
- Relasi Eloquent dan nama method.
- Migration yang membuat atau mengubah tabel.

| Tabel | Tujuan | Model | Relasi penting | Status |
|---|---|---|---|---|
| users | Akun pengguna | User | | Pending |
| comics | Data komik | Comic | | Pending |
| genres | Kategori genre | Genre | | Pending |
| comic_genre | Pivot komik-genre | — | | Pending |
| chapters | Chapter komik | Chapter | | Pending |
| chapter_pages | Halaman chapter | ChapterPage | | Pending |
| bookmarks | Bookmark pengguna | Bookmark | | Pending |
| reading_histories | Riwayat membaca | ReadingHistory | | Pending |

**Catatan:** tabel dan kolom final harus mengikuti ERD yang telah disetujui. Jangan melakukan perubahan schema hanya dengan mengedit dokumen ini; sinkronkan juga migration, model, dan anggota yang bergantung padanya.
