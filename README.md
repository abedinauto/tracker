# Belanja Aku

App penjejak perbelanjaan peribadi — satu fail `index.html`, tanpa build.

## Ciri
- Bajet bulanan dengan papan kapur, bar kemajuan & baki
- Kategori belanja/pendapatan dengan ikon, warna & bajet setiap kategori
- Carta kategori, belanja harian & trend 6 bulan
- Cari & tapis transaksi, salin CSV
- Bawa baki ke bulan depan, sorok transaksi akan datang, mod gelap
- Sandaran & pulih JSON

## Guna
Live: https://abedinauto.github.io/tracker/

## Storan data
- **Log masuk (Tetapan → Akaun awan):** data disimpan di Supabase (`transactions`, `settings`).
  Row Level Security memastikan setiap pengguna hanya boleh baca/tulis data sendiri.
- **Tanpa log masuk:** data disimpan dalam pelayar (localStorage). Bila log masuk kali pertama,
  app tawarkan untuk pindahkan data tempatan ke awan.

Kunci `sb_publishable_...` dalam `index.html` memang selamat untuk didedahkan — akses dikawal oleh RLS.

### Tetapan Supabase yang perlu
Authentication → URL Configuration:
- Site URL: `https://abedinauto.github.io/tracker/`
- Redirect URLs: `https://abedinauto.github.io/tracker/`
