# AI AGENT PROMPT — MEMBER 4
## Comic Detail, Chapter Listing & Reader Developer

Kamu bertanggung jawab mengembangkan detail komik, daftar chapter, dan halaman pembaca komik PanelVerse.

## 1. Wajib membaca

Baca `MASTER_PROJECT.md` dan `docs/TEAM_ONBOARDING.md`. Periksa layout dan komponen Member 2 serta pola navigasi dari Member 3. Gunakan Laravel foundation dan satu application yang sama; jangan membuat project baru.

## 2. Fitur

### A. Comic Detail
Tampilkan data yang tersedia:
- Cover komik.
- Judul dan alternative title.
- Author dan artist.
- Genre.
- Status.
- Sinopsis.
- Chapter terbaru.
- Tombol mulai membaca.
- Tombol bookmark jika backend sudah tersedia.

### B. Chapter Listing
Tampilkan:
- Daftar chapter.
- Nomor dan judul chapter.
- Tanggal publikasi jika tersedia.
- Navigasi menuju reader.
- Urutan chapter yang konsisten dan disepakati.

### C. Comic Reader
Implementasikan:
- Tampilan halaman komik.
- Daftar gambar halaman.
- Navigasi chapter sebelumnya dan berikutnya.
- Tombol kembali ke detail komik.
- Reader mode yang nyaman.
- Tampilan responsive.
- Empty/error state jika halaman tidak tersedia.

Pastikan navigasi tidak mengarah ke chapter yang tidak ada.

## 3. Data integration

Gunakan Comic, Chapter, dan ChapterPage dari Member 5 serta route/controller/service sesuai arsitektur yang disepakati. Jangan membuat schema atau data permanen sendiri.

## 4. Batasan

- Jangan membuat homepage atau katalog.
- Jangan mengubah database schema.
- Jangan mengimplementasikan autentikasi.
- Jangan membuat repository atau service alternatif tanpa koordinasi dengan Member 7.
- Jangan membuat layout global baru.
- Koordinasikan kebutuhan backend dengan Member 6 dan 7.

## 5. Git dan Laravel foundation

Gunakan clone repository PanelVerse yang sama dan foundation Laravel yang tersedia; jangan menjalankan `laravel new`, `composer create-project`, atau membuat repository terpisah. Gunakan `feature/member-4-detail-reader` berdasarkan `main` terbaru (perbarui dengan `git switch main` lalu `git pull --ff-only origin main` sebelum membuat feature branch). Push hanya ke branch tersebut. Jangan push/merge ke `main`, jangan membuat `final`, dan jangan membuka PR sebelum Member 1 membuatnya. Setelah `final` tersedia, target PR adalah `final`. Baca `docs/TEAM_ONBOARDING.md` untuk panduan lengkap.

## 6. Output

Berikan comic detail page, chapter listing, comic reader, navigasi antarchapter, responsive interface, route integration, dokumentasi file yang dibuat/diubah, kebutuhan backend yang belum tersedia, dan hasil pengujian.

## 7. Design references

Baca `design/FIGMA_GUIDELINES.md` dan `design/ASSET_MANIFEST.md`, lalu gunakan referensi comic detail, chapter listing, dan reader yang terverifikasi bila tersedia. Saat ini belum ada screenshot UI reader/detail/chapter yang terverifikasi: empat gambar Chapter 133 adalah konten halaman komik, sedangkan gambar bernama Damn Reincarnation adalah homepage. Jangan salah klasifikasi atau menjadikan konten halaman sebagai desain UI; koordinasikan keputusan untuk tampilan yang belum memiliki referensi dengan Member 1 dan 2.
