# Belanja Aku

App penjejak perbelanjaan peribadi — satu fail `index.html`, tanpa build.

## Ciri
- **Input cepat — taip atau cakap** ("nasi lemak 5", "grab 12.50 semalam", "5 ringgit 20 sen"): jumlah, tarikh & kategori dikesan automatik (belajar dari transaksi lepas), dengan Ubah / Batal
- Butang mic (suara, Bahasa Melayu) — jika pelayar tak sokong, guna mic papan kekunci
- Kad bajet: jumlah belanja, status (Bawah bajet / Hampir had / Lebih bajet), penanda hari dalam bulan, baki & boleh belanja/hari
- Ringkasan Hari ini / 7 hari / Purata sehari, senarai transaksi terkini, leret ke kiri untuk padam
- Tema Emas (hitam-emas), Gelap atau Kertas
- Bajet bulanan, bar kemajuan, baki & amaran unjuran terlebih bajet
- Kategori belanja/pendapatan dengan ikon, warna & bajet setiap kategori
- Kategori **bayaran balik (refund)** — ditolak daripada belanja, bukan ditambah
- **Bil berulang** — tanda transaksi "Ulang setiap bulan", app ingatkan & rekod bulan depan
- Carta kategori (tekan untuk lihat transaksi), belanja harian (tekan bar) & trend 6 bulan
- Carian merentas semua bulan, tapis jenis/kategori, salin CSV
- Padam dengan **Batal (undo)**
- Bawa baki ke bulan depan, abaikan transaksi akan datang
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
