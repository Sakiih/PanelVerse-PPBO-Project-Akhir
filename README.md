# PanelVerse

PanelVerse adalah platform web membaca manga, manhwa, dan manhua untuk proyek akhir mata kuliah Pemrograman Berorientasi Objek. Proyek ini terinspirasi oleh kebutuhan umum layanan baca komik, tetapi implementasi dan identitas visualnya dikembangkan sendiri.

**Status:** Laravel foundation tersedia; pengembangan fitur tim dimulai melalui feature branches. Aplikasi ditujukan untuk penggunaan lokal dalam tugas kuliah, bukan deployment publik.

**Repository:** [Sakiih/PanelVerse-PPBO-Project-Akhir](https://github.com/Sakiih/PanelVerse-PPBO-Project-Akhir)

## Teknologi

- Laravel 13.43.0, PHP 8.3+, MySQL 8
- Composer 2.10.3, Node.js 22, NPM
- Blade, Tailwind CSS sesuai konfigurasi, JavaScript, Vite
- REST API

## Mulai secara lokal

Lihat [panduan onboarding](docs/TEAM_ONBOARDING.md) untuk langkah Windows PowerShell yang lengkap. Ringkasnya: clone repository, jalankan `composer install`, buat `.env` lokal dan APP_KEY, siapkan database `panelverse`, jalankan migration, pasang dependency frontend dengan `npm ci`, build, lalu jalankan `php artisan serve`.

```powershell
git clone git@github.com:Sakiih/PanelVerse-PPBO-Project-Akhir.git
Set-Location PanelVerse-PPBO-Project-Akhir
composer install
Copy-Item .env.example .env
php artisan key:generate
# Atur koneksi MySQL lokal pada .env, lalu:
php artisan migrate
npm ci
npm run build
php artisan serve
```

Jangan commit `.env` atau credential. Lihat [Git dan aturan kerja](docs/TEAM_ONBOARDING.md#git-onboarding) sebelum membuat branch.

## Sumber konteks proyek

- [MASTER_PROJECT.md](MASTER_PROJECT.md) — sumber kebenaran proyek, kontrak, tanggung jawab, dan alur integrasi.
- [docs/TEAM_ONBOARDING.md](docs/TEAM_ONBOARDING.md) — setup, troubleshooting, dan Git untuk anggota.
- [design/FIGMA_GUIDELINES.md](design/FIGMA_GUIDELINES.md) dan [design/ASSET_MANIFEST.md](design/ASSET_MANIFEST.md) — acuan implementasi visual dan inventaris referensi.
- [CHANGELOG_TEMPLATE.md](CHANGELOG_TEMPLATE.md) — format catatan perubahan.

## Pembagian anggota

| Anggota | Prompt | Tanggung jawab |
|---|---|---|
| 1 | [MEMBER_1_PROMPT.md](prompts/MEMBER_1_PROMPT.md) | Project Manager, System Analyst & Integrator |
| 2 | [MEMBER_2_PROMPT.md](prompts/MEMBER_2_PROMPT.md) | UI/UX & Blade Foundation |
| 3 | [MEMBER_3_PROMPT.md](prompts/MEMBER_3_PROMPT.md) | Homepage, Comic Catalog & Search |
| 4 | [MEMBER_4_PROMPT.md](prompts/MEMBER_4_PROMPT.md) | Comic Detail, Chapter & Reader |
| 5 | [MEMBER_5_PROMPT.md](prompts/MEMBER_5_PROMPT.md) | Database Architect & Eloquent |
| 6 | [MEMBER_6_PROMPT.md](prompts/MEMBER_6_PROMPT.md) | Backend, Authentication & REST API |
| 7 | [MEMBER_7_PROMPT.md](prompts/MEMBER_7_PROMPT.md) | OOP Architect & SOLID |

Semua anggota menggunakan repository dan Laravel application yang sama. Pull Request fitur ditargetkan ke `final` setelah Member 1 membuat branch tersebut; jangan membuka PR menuju `main`.
