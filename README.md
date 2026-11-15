# Belanja Aku

App penjejak perbelanjaan peribadi — satu fail `index.html`, tanpa build.

## Ciri
- Bajet bulanan dengan papan kapur, bar kemajuan, baki & amaran unjuran terlebih bajet
- Kategori belanja/pendapatan dengan ikon, warna & bajet setiap kategori
- Kategori **bayaran balik (refund)** — ditolak daripada belanja, bukan ditambah
- **Bil berulang** — tanda transaksi "Ulang setiap bulan", app ingatkan & rekod bulan depan
- Carta kategori (tekan untuk lihat transaksi), belanja harian (tekan bar) & trend 6 bulan
- Carian merentas semua bulan, tapis jenis/kategori, salin CSV
- Padam dengan **Batal (undo)**
- Bawa baki ke bulan depan, abaikan transaksi akan datang, mod gelap
- Sandaran & pulih JSON
- Boleh dipasang ke skrin utama (Add to Home Screen)

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
