# PanelVerse — Integration Guide

**Pemilik:** Member 1  
**Status:** Living document — perbarui setiap ada keputusan atau integrasi penting.

## 1. Aturan dasar

- Satu repository dan satu Laravel application.
- `main` untuk versi stabil.
- `develop` untuk integrasi.
- Setiap anggota bekerja pada feature branch miliknya.
- Semua feature branch membuka Pull Request ke `develop`.
- Jangan commit `.env`, token, password, atau kredensial.

## 2. Branch anggota

| Anggota | Branch |
|---|---|
| 1 | `feature/member-1-project-management` |
| 2 | `feature/member-2-ui-foundation` |
| 3 | `feature/member-3-homepage-catalog` |
| 4 | `feature/member-4-detail-reader` |
| 5 | `feature/member-5-database` |
| 6 | `feature/member-6-rest-api` |
| 7 | `feature/member-7-oop-architecture` |

## 3. PR checklist

- [ ] Tujuan perubahan jelas.
- [ ] Perubahan berada dalam lingkup tugas.
- [ ] Tidak ada secret atau `.env`.
- [ ] Tidak ada file duplikat atau perubahan tidak terkait.
- [ ] Migration dan schema kompatibel.
- [ ] Test/pemeriksaan relevan dijalankan.
- [ ] Screenshot/API evidence tersedia bila relevan.
- [ ] Dokumentasi diperbarui.
- [ ] Dampak ke anggota lain dijelaskan.

## 4. Integration log

| Tanggal | PR / Branch | Ringkasan | Reviewer | Status |
|---|---|---|---|---|
| | | | | Pending |

## 5. Keputusan lintas anggota

| Tanggal | Topik | Keputusan | Disetujui oleh |
|---|---|---|---|
| | Database contract | | |
| | Blade component contract | | |
| | API contract | | |
| | OOP architecture | | |

## 6. Pengujian setelah integrasi

Catat command yang benar-benar dijalankan, environment, hasil, dan masalah yang ditemukan. Jangan menandai test lulus jika belum dijalankan.
