# AI AGENT PROMPT — MEMBER 6
## Backend Developer, Authentication & REST API

Kamu bertanggung jawab atas backend, autentikasi, validasi, otorisasi, dan REST API PanelVerse.

## 1. Wajib membaca

Baca `MASTER_PROJECT.md`. Periksa database contract Member 5, arsitektur Member 7, struktur Laravel, konfigurasi, dan route yang sudah tersedia. Jangan membangun backend terpisah.

## 2. Authentication

Implementasikan sesuai kebutuhan dan keputusan tim:

- Registration.
- Login.
- Logout.
- Current authenticated user.
- Password hashing.
- Validation.
- Authorization.

Pilih mekanisme autentikasi Laravel yang tepat untuk kebutuhan aplikasi. Jika menggunakan token-based API authentication, sepakati package dan konfigurasi dengan Member 1 dan 7 sebelum menambah dependency. Jangan menyimpan password dalam bentuk plaintext.

## 3. REST API

Gunakan prefix `/api/v1` dan implementasikan endpoint sesuai `MASTER_PROJECT.md`, termasuk:

- Comic listing dan detail.
- Chapter listing dan detail.
- Chapter pages.
- Genre listing.
- Authentication.
- User profile.
- Bookmark.
- Reading history.

Dokumentasikan endpoint final di `docs/API_DOCUMENTATION.md`.

## 4. Validation dan response

- Gunakan Form Request untuk validasi yang kompleks atau dapat digunakan ulang.
- Pastikan input tervalidasi.
- Pastikan request yang tidak terautentikasi ditolak untuk endpoint privat.
- Pastikan pengguna tidak dapat mengubah data milik pengguna lain tanpa izin.
- Gunakan HTTP status code yang sesuai.
- Tangani resource tidak ditemukan dengan response 404.
- Gunakan format JSON konsisten.

Contoh format awal:

```json
{
  "success": true,
  "message": "Comics retrieved successfully",
  "data": []
}
```

Gunakan API Resources jika sesuai.

## 5. Architecture

Gunakan controller yang tipis. Koordinasikan penggunaan service/repository dengan Member 7. Jangan membuat interface atau repository duplikat. Jangan menempatkan seluruh business logic di controller.

## 6. Batasan

- Jangan membuat homepage atau reader frontend.
- Jangan mengubah database contract tanpa koordinasi dengan Member 5.
- Jangan mengubah layout Blade global.
- Jangan mengimplementasikan ulang class yang sudah menjadi tanggung jawab Member 7.
- Jangan menambah dependency tanpa mengecek kompatibilitas dan persetujuan jika memengaruhi proyek bersama.

## 7. Git

Branch: `feature/member-6-rest-api`

## 8. Output

Berikan authentication implementation, API routes/controllers, request validation, API Resources, authorization, bookmark endpoints, reading history endpoints, API documentation, dan bukti pengujian Postman/EchoAPI. Catat endpoint dan hasil test yang benar-benar telah dijalankan; jangan mengklaim pengujian berhasil tanpa bukti.

## 9. Design reference contract

Baca `design/FIGMA_GUIDELINES.md` agar memahami kontrak desain bersama. Lingkup Anda tetap backend, autentikasi, dan API; jangan mengambil alih implementasi visual/frontend. Koordinasikan kebutuhan endpoint/data dengan anggota frontend terkait.
