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

```https
  POST /api/v1/auth/login
```

Requested Body
```json
{
  "username": "string",
  "password": "string"
}
```

*Asumsi username dan password static. Gunakan Username = user dan Password = gomorse123.

Example Response Body
```json
{
  "jwt_token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHBpcmF0aW9uIjoxNzM2NTI2NDI2LCJpc3N1ZWRfYXQiOjE3MzY1MjYxMjYsInVzZXJfaWQiOiJ1c2VyIn0.zHSMosYG0gvmFlqB55_NKyzCNja1nRDVmdhNKJJqnDw"
}
```

## API Endpoints

*Asumsi API Key static. Gunakan x-api-key = gomorse123

#### Get Service Locations (All)
Mendapatkan seluruh tempat servis atau bengkel motor yang available

```https
  GET /api/v1/service-locations
```
Headers
| Parameter | Value    | 
| :-------- | :------- | 
| `x-api-key`      | API KEY | 
| `Authorization` | bearer {JWT Token} |

#### Get Service Locations (Spesific Location ID)
Mendapatkan tempat servis atau bengkel motor yang available berdasarkan location ID

```https
  GET /api/v1/service-locations/{loc_id}
```

Headers
| Parameter | Value    | 
| :-------- | :------- | 
| `x-api-key`      | API KEY | 
| `Authorization` | bearer {JWT Token} |

#### Get Ongkir Fee Calculation
Mendapatkan hasil perhitungan dari ongkos kirim berdasarkan total jarak dan tipe kendaraan untuk servis yang dipilih

```https
  GET /api/v1/ongkir-fee-calculation
```

Headers
| Parameter | Value    | 
| :-------- | :------- | 
| `x-api-key`      | API KEY | 
| `Authorization` | bearer {JWT Token} |

#### Post Service Fee Calculation
Mendapatkan hasil perhitungan dari biaya servis berdasarkan tipe servis yang digunakan dan biaya tambahan yang harus dikeluarkan

```https
  POST /api/v1/service-fee-calculation
```

Headers
| Parameter | Value    | 
| :-------- | :------- | 
| `x-api-key`      | API KEY | 
| `Authorization` | bearer {JWT Token} |

#### Get Nearest Store
Mendapatkan lokasi servis motor atau bengkel terdekat berdasarkan input lokasi pengguna saat ini

```https
  GET /api/v1/nearest-store
```

Headers
| Parameter | Value    | 
| :-------- | :------- | 
| `x-api-key`      | API KEY | 
| `Authorization` | bearer {JWT Token} |

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
