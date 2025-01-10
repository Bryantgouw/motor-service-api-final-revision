# API GO-MORSE

GO-MORSE atau Go Motorcycle Service merupakan sebuah API (Application Programming Interface) yang dikembangkan oleh Anthony Bryant Gouw (18222033). API ini memiliki tujuan utama untuk menyediakan kebutuhan pengguna seputar motorcycle emergency service, mulai dari endpoint informasi lokasi bengkel atau tempat servis motor yang available, perhitungan biaya servis, perhitungan biaya ongkos kirim, hingga algoritma pencarian lokasi servis motor terdekat berdasarkan lokasi pengguna. API GO-MORSE dapat digunakan untuk umum.

## API Access

API GO-MORSE dapat diakses melalui link berikut :
https://gomorseapi.codebloop.my.id/api/v1

API GO-MORSE (FastAPI Documentation) dapat diakses melalui link berikut :
https://gomorseapi.codebloop.my.id/docs

## API Authentication

#### Login
Login diperlukan untuk mengenerate terhadap JWT Token yang nantinya akan digunakan untuk mengakses endpoint API lain

```http
  POST /api/v1/auth/login
```

Requested Body
```json
{
  "username": "string",
  "password": "string"
}
```

## API Endpoints

## API Errors

| Error | Deskripsi                                                                     |
| ----- | ----------------------------------------------------------------------------- |
| 400   | Bad Request (Permintaan tidak valid atau tidak sesuai format yang diharapkan) |
| 401   | Unauthorized (Tidak punya otorisasi untuk akses resources)                    |
| 422   | Unprocessable Entity (Kesalahan dalam konten)                                 |
| 404   | Not Found (Resources yang diminta tidak ditemukan di server)                  |

---

## Pembuat Aplikasi

| Nama                | NIM      |
| ------------------- | -------- |
| Anthony Bryant Gouw | 18222033 |

---

© 2025 Bryant . All rights reserved.
