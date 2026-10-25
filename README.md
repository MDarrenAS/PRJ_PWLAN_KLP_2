# Signify

Signify adalah website yang dirancang untuk membantu pembelajaran Sistem Isyarat Bahasa Indonesia (SIBINDO). Aplikasi ini dibangun dengan Laravel dan React melalui Inertia.js. Skema Supabase untuk kebutuhan pembelajaran tersedia di [`docs/supabase_schema.sql`](docs/supabase_schema.sql).

> Repository ini masih menggunakan Laravel React starter kit sebagai fondasi. Kamus isyarat, materi, kuis, dan pelacakan progres merupakan ruang lingkup produk yang direncanakan, bukan klaim bahwa seluruh fitur tersebut sudah tersedia.

## Teknologi

- PHP 8.3+ (sesuai constraint Composer) dan Laravel 13
- React 19, TypeScript, dan Inertia.js 3
- Kotlin untuk pengembangan aplikasi Android
- SQLite sebagai konfigurasi database lokal bawaan
- Supabase PostgreSQL sebagai target skema pembelajaran opsional

## Anggota tim

| Anggota | NIM | Peran | Tanggung Jawab |
| --- | --- | --- | --- |
| Alifah Putri Rhandiny | 245150401111047 | Frontend Developer | Membangun tampilan dan interaksi pengguna. |
| Aryanti Puspita Sari | 245150400111068 | UI/UX Designer dan Frontend Developer | Merancang desain dan alur aplikasi serta membangun tampilan dan interaksi pengguna. |
| Muhammad Darren Achilles Setiawan | 245150401111049 | Backend Developer | Membangun server, database, dan API. |
| A. Muh. Abduh Dzaky | 245150407111039 | Backend Developer | Membangun server, database, dan API. |

## Persiapan lokal

Pastikan PHP, Composer, Node.js, dan npm tersedia, lalu jalankan dari direktori proyek:

```bash
composer setup
composer dev
```

`composer setup` memasang dependensi, menyiapkan `.env`, membuat application key, menjalankan migrasi Laravel, memasang dependensi frontend, dan membangun aset. `composer dev` menjalankan lingkungan pengembangan Laravel. Jangan membagikan atau memasukkan `.env` ke commit.

## Supabase

File [`docs/supabase_schema.sql`](docs/supabase_schema.sql) adalah skema PostgreSQL untuk Supabase. Untuk membuat tabel skema tersebut, tinjau file lalu jalankan melalui SQL Editor pada proyek Supabase yang sesuai.

Skema ini mengacu pada `auth.users` Supabase dan bukan migrasi Laravel. Aplikasi saat ini dikonfigurasi menggunakan SQLite lokal; menghubungkan aplikasi Laravel ke Supabase memerlukan konfigurasi koneksi dan integrasi autentikasi yang sesuai. Jangan menjalankan skema ini terhadap database produksi tanpa meninjau dampaknya terlebih dahulu.

## Struktur dokumentasi

- [`docs/CODING_GUIDELINES.md`](docs/CODING_GUIDELINES.md) — konvensi kontribusi dan format commit.
- [`docs/supabase_schema.sql`](docs/supabase_schema.sql) — skema database Supabase.

## Pemeriksaan kode

```bash
npm run check
npm run types:check
composer lint
php artisan test
```
