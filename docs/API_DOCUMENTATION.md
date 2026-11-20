# PanelVerse — REST API Documentation

**Prefix:** `/api/v1`  
**Pemilik implementasi:** Member 6  
**Koordinasi kontrak:** Member 1, 5, dan 7  
**Status:** Draft — perbarui setelah endpoint diimplementasikan dan diuji.

## Konvensi

- Dokumentasikan method, path, autentikasi, parameter, request body, response, dan status code.
- Gunakan JSON secara konsisten.
- Catat aturan authorization untuk resource privat.
- Jangan mendokumentasikan endpoint sebagai selesai sebelum diuji.

## Endpoint awal

| Method | Path | Auth? | Deskripsi | Status |
|---|---|---|---|---|
| GET | `/api/v1/comics` | Tidak | Daftar komik | Planned |
| GET | `/api/v1/comics/{slug}` | Tidak | Detail komik | Planned |
| GET | `/api/v1/comics/{slug}/chapters` | Tidak | Daftar chapter | Planned |
| GET | `/api/v1/chapters/{id}` | Tidak | Detail chapter | Planned |
| GET | `/api/v1/chapters/{id}/pages` | Tidak | Halaman chapter | Planned |
| GET | `/api/v1/genres` | Tidak | Daftar genre | Planned |
| POST | `/api/v1/register` | Tidak | Registrasi | Planned |
| POST | `/api/v1/login` | Tidak | Login | Planned |
| POST | `/api/v1/logout` | Ya | Logout | Planned |
| GET | `/api/v1/user` | Ya | Profil pengguna | Planned |
| GET | `/api/v1/bookmarks` | Ya | Bookmark pengguna | Planned |
| POST | `/api/v1/bookmarks` | Ya | Tambah bookmark | Planned |
| DELETE | `/api/v1/bookmarks/{id}` | Ya | Hapus bookmark | Planned |
| GET | `/api/v1/reading-history` | Ya | Riwayat membaca | Planned |

## Format response awal

```json
{
  "success": true,
  "message": "Comics retrieved successfully",
  "data": []
}
```

Sesuaikan format final bila tim menetapkan envelope berbeda. Pastikan seluruh endpoint konsisten.

## Endpoint detail

Tambahkan bagian per endpoint di bawah ini setelah implementasi:

### [Nama endpoint]

- **Method & path:**
- **Authentication:**
- **Authorization:**
- **Query/path parameters:**
- **Request body:**
- **Success response:**
- **Error responses:**
- **Test evidence:**
