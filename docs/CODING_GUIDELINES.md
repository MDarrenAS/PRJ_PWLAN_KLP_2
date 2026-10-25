# Coding Guidelines

Panduan ini berlaku untuk perubahan pada Signify. Utamakan perubahan yang kecil, jelas, konsisten dengan pola di sekitarnya, dan disertai pengujian untuk perilaku yang berubah.

## Prinsip umum

- Pahami implementasi dan konvensi file terkait sebelum mengubah kode.
- Gunakan nama variabel, fungsi, dan komponen yang deskriptif.
- Hindari perubahan yang tidak berkaitan dengan tujuan pekerjaan.
- Jangan commit file `.env`, kredensial, token, atau data sensitif.
- Perbarui dokumentasi yang terdampak oleh perubahan fitur atau konfigurasi.

## Backend — PHP dan Laravel

- Ikuti struktur Laravel yang sudah ada; gunakan controller, request, model, dan migration yang sesuai tanggung jawabnya.
- Berikan type hint parameter dan return type pada method.
- Gunakan kurung kurawal untuk seluruh struktur kontrol.
- Validasi input dan terapkan otorisasi di sisi server.
- Hindari query berulang yang tidak perlu; gunakan relasi dan eager loading saat sesuai.
- Buat atau perbarui tes untuk perubahan perilaku yang bermakna.
- Format kode PHP dengan Laravel Pint: `vendor/bin/pint --dirty --format agent`.

## Frontend — React dan TypeScript

- Ikuti pola halaman Inertia yang sudah ada di `resources/js/pages` dan gunakan kembali komponen yang tersedia.
- Pertahankan type safety; hindari `any` dan type assertion yang tidak diperlukan.
- Gunakan Wayfinder untuk memanggil route atau action Laravel dari frontend; jangan menanam URL route secara manual.
- Tangani status loading, validasi, dan kegagalan request dengan jelas.
- Jalankan pemeriksaan frontend yang relevan, seperti `npm run check` dan `npm run types:check`.

## Database dan Supabase

- Untuk perubahan database Laravel, buat migration Laravel dan ikuti konvensi migration yang sudah ada.
- `docs/supabase_schema.sql` ditujukan untuk PostgreSQL di Supabase; jangan menganggapnya sebagai migration Laravel.
- Terapkan kebijakan Row Level Security dan batasi akses data berdasarkan identitas serta peran pengguna.
- Jangan menaruh secret Supabase atau service-role key di frontend maupun repository.
- Perhitungan nilai kuis dan perubahan data sensitif harus divalidasi di sisi server.

## Commit message

Gunakan format:

```text
<type>: <ringkasan singkat dalam bentuk perintah>
```

Gunakan huruf kecil untuk `<type>` dan ringkasan yang singkat, spesifik, serta tanpa titik di akhir. Tipe yang digunakan:

- `feat:` — menambahkan fitur.
- `fix:` — memperbaiki bug.
- `docs:` — mengubah dokumentasi.
- `style:` — perubahan format atau tampilan tanpa perubahan perilaku.
- `refactor:` — merapikan struktur tanpa mengubah perilaku.
- `test:` — menambah atau memperbarui tes.
- `chore:` — pemeliharaan atau konfigurasi pendukung.

Contoh:

```text
feat: tambahkan pencarian kamus isyarat
fix: validasi jawaban kuis sebelum disimpan
docs: tambahkan panduan kontribusi
```

Jangan gabungkan perubahan yang tidak berkaitan dalam satu commit. Jika perubahan membutuhkan konteks tambahan, tambahkan body commit setelah satu baris kosong.
