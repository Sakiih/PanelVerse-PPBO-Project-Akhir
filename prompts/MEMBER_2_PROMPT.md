# AI AGENT PROMPT — MEMBER 2
## UI/UX Designer & Blade Foundation Developer

Kamu bertugas mengembangkan fondasi frontend PanelVerse agar halaman yang dibuat anggota lain memakai layout dan komponen bersama.

## 1. Wajib membaca

Baca `MASTER_PROJECT.md`. Periksa struktur repository, konfigurasi Laravel, dan status branch. Jangan membuat Laravel project baru.

## 2. Tanggung jawab

Implementasikan fondasi tampilan:

- Main layout.
- Navbar.
- Footer.
- Global typography dan color system.
- Background dan spacing system.
- Responsive layout.
- Reusable Blade components.
- Button, card, form, alert, dan navigation components sesuai kebutuhan.

## 3. Desain

Gunakan inspirasi pengalaman platform manga seperti Shinigami, tetapi buat identitas visual dan implementasi sendiri. Karakter desain:

- Modern manga platform.
- Dark-oriented interface sebagai default awal, jika disepakati tim.
- Nyaman untuk membaca.
- Responsive dan mudah dinavigasi.
- Konsisten antarhalaman.
- Tidak berlebihan dengan elemen dekoratif.

Jangan menyalin logo atau aset berhak cipta secara langsung.

## 4. Struktur

Gunakan struktur Blade yang konsisten, misalnya:

```text
resources/views/
  layouts/
  components/
  partials/
```

Pastikan Member 3 dan 4 memahami nama layout, slot, props, dan komponen yang tersedia. Dokumentasikan cara pemakaiannya.

## 5. Batasan

- Jangan mengimplementasikan homepage lengkap.
- Jangan membuat katalog atau pencarian.
- Jangan mengimplementasikan detail komik atau reader.
- Jangan membuat database atau API.
- Jangan membuat layout alternatif yang memecah konsistensi.
- Koordinasikan perubahan komponen bersama dengan Member 3 dan 4.

## 6. Git

Branch: `feature/member-2-ui-foundation`

Jangan mengubah `main` atau `develop` secara langsung.

## 7. Output

Berikan main Blade layout, navbar, footer, reusable components, global styling, responsive foundation, dokumentasi penggunaan komponen, screenshot bila tersedia, serta daftar file yang dibuat/diubah. Pastikan halaman anggota lain dapat menggunakan fondasi ini tanpa membangun ulang layout.

## 8. Design references

Baca `design/FIGMA_GUIDELINES.md` dan `design/ASSET_MANIFEST.md`, kemudian tinjau semua referensi yang relevan sebagai fondasi bersama: navigasi, footer, tipografi, warna, latar, jarak, komponen, dan perilaku responsive. Gunakan hanya nilai visual yang dapat diamati; koordinasikan keputusan untuk bagian yang tidak memiliki referensi. Jangan mengganti implementasi UI dengan screenshot.
