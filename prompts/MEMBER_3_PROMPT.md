# AI AGENT PROMPT — MEMBER 3
## Homepage, Comic Catalog & Search Developer

Kamu bertanggung jawab mengembangkan homepage dan katalog komik PanelVerse.

## 1. Wajib membaca

Baca `MASTER_PROJECT.md` dan `docs/TEAM_ONBOARDING.md`. Periksa repository serta implementasi Member 2 sebelum mengubah file. Gunakan Laravel foundation, layout, dan reusable components yang sudah disepakati; jangan membuat project baru.

## 2. Fitur yang harus dibuat

### Homepage
- Featured atau hero section.
- Latest updates.
- Popular comics.
- Recommended comics jika data tersedia.
- Comic cards.

### Comic Catalog
- Daftar komik.
- Pagination.
- Filter genre.
- Filter jenis komik.
- Filter status jika field tersedia.

### Search
- Pencarian berdasarkan judul.
- Form pencarian.
- Hasil pencarian.
- Empty state ketika tidak ada hasil.

## 3. Data integration

Gunakan model Comic dan relasi Genre dari Member 5. Gunakan data database, bukan hardcoded dummy data untuk implementasi final. Jika database belum siap, data sementara boleh dipakai hanya untuk pengembangan UI dan harus ditandai serta didokumentasikan.

Gunakan slug untuk navigasi menuju halaman detail apabila slug telah ditetapkan dalam database contract.

## 4. UI/UX

- Gunakan layout dan komponen Member 2.
- Buat tampilan responsive.
- Pastikan cover memiliki rasio konsisten.
- Sediakan empty/error state yang sesuai.
- Pertahankan aksesibilitas dasar dan label form yang jelas.

## 5. Batasan

- Jangan mengimplementasikan halaman detail komik.
- Jangan membuat chapter reader.
- Jangan mengubah database schema.
- Jangan membuat layout global baru.
- Jangan membuat endpoint API sendiri tanpa koordinasi dengan Member 6.
- Jangan mengubah file milik anggota lain di luar kebutuhan yang disepakati.

## 6. Git dan Laravel foundation

Gunakan clone repository PanelVerse yang sama dan foundation Laravel yang tersedia; jangan menjalankan `laravel new`, `composer create-project`, atau membuat repository terpisah. Gunakan `feature/member-3-homepage-catalog` berdasarkan `main` terbaru (perbarui dengan `git switch main` lalu `git pull --ff-only origin main` sebelum membuat feature branch). Push hanya ke branch tersebut. Jangan push/merge ke `main`, jangan membuat `final`, dan jangan membuka PR sebelum Member 1 membuatnya. Setelah `final` tersedia, target PR adalah `final`. Baca `docs/TEAM_ONBOARDING.md` untuk panduan lengkap.

## 7. Output

Berikan homepage, comic catalog, search, genre filter, pagination, reusable comic card bila belum tersedia, route integration, dokumentasi file yang diubah, dan hasil pengujian. Pastikan halaman menggunakan database contract yang disepakati.

## 8. Design references

Baca `design/FIGMA_GUIDELINES.md` dan `design/ASSET_MANIFEST.md`. Untuk pekerjaan visual, fokus pada `design/references/homepage/` dan `design/references/catalog/` (termasuk pencarian). Jangan mengambil alih detail komik, reader, atau halaman lain. Ikuti referensi yang ada; bila perilaku atau tampilan tidak terlihat jelas, koordinasikan dengan Member 1 dan Member 2. Screenshot bukan pengganti implementasi UI.
