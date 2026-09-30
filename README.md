# AMAR STR V4 — Vercel + Supabase

Website React sederhana dengan API serverless Vercel dan PostgreSQL/Auth Supabase.

## Struktur

```text
amar-str-vercel/
├── public/
│   └── index.html
├── api/
│   └── [...path].js
├── supabase/
│   └── supabase.sql
├── .env.example
├── .gitignore
├── package.json
├── vercel.json
└── README.md
```

## Deploy

1. Buat project Supabase.
2. Buka Supabase SQL Editor dan jalankan `supabase/supabase.sql`.
3. Aktifkan Google Provider di Supabase Authentication.
4. Push folder ini ke GitHub.
5. Import repository ke Vercel.
6. Tambahkan environment variables dari `.env.example` di Vercel:
   - `SUPABASE_URL`
   - `SUPABASE_ANON_KEY`
   - `SUPABASE_SERVICE_ROLE_KEY`
7. Deploy.

## Admin pertama

Buat akun biasa terlebih dahulu, lalu di Supabase SQL Editor jalankan:

```sql
update public.profiles
set role='admin'
where username='USERNAME_ANDA';
```

## Google Login

Atur Google OAuth di Supabase Authentication. Tambahkan domain deployment Vercel pada URL/redirect yang diizinkan sesuai konfigurasi Supabase.

## Keamanan

Jangan commit `.env` atau `SUPABASE_SERVICE_ROLE_KEY`. `.gitignore` sudah disiapkan untuk mencegah file tersebut ikut ter-upload.

STOR hanya menerima alamat email/TXT. Aplikasi tidak meminta atau menyimpan password Gmail, OTP, cookie/session, recovery code, atau kredensial akun.
