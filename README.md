# Grafik Lapi 2 — Grafik + Raw Data

Paket ini adalah revisi dari dashboard Grafik-Lapi-2. Perubahan tampilan **hanya ada di `index.html`**. Database JSON memakai struktur yang sama dengan versi sebelumnya.

## Isi paket

- `index.html` — dashboard terbaru, dengan tab **Grafik** dan **Pengaturan Data**.
- `rekap-data/rekap-listrik.json` — SALINAN DATABASE AWAL contoh hasil ekstraksi Excel untuk instalasi yang BELUM mempunyai data di repository.
- `preview-bulanan-raw.png` dan `preview-harian-raw.png` — pratinjau tampilan.

## Perubahan pada tab Grafik

- Tata letak lebih rapi dengan sumbu X/Y berlabel, skala dari nol, garis rata-rata (untuk nilai tersedia), warna panel yang bisa dipilih, grafik garis/batang, dan tooltip pada data.
- Raw data langsung di bawah grafik (tidak perlu pindah ke tab Pengaturan Data). Grafik **Harian** memperlihatkan tanggal, stand awal/akhir, pembacaan per jam, hasil kWh, dan status. Grafik **Bulanan** memperlihatkan total, jumlah hari valid/lengkap, dan status setiap bulan; tombol **Lihat harian** berpindah ke rincian bulan yang dipilih.
- **PNG + Data** mengunduh gambar berisi grafik dan tabel, bukan hanya gambar grafik.
- **CSV / CSV Raw Data** mengunduh angka sesuai periode dan panel, termasuk rincian per jam untuk harian.
- Kartu total berubah sesuai grafik: subtotal bulanan di grafik harian, subtotal tahunan pada grafik bulanan. Status *sementara, parsial, kosong,* dan *periksa* tetap dipertahankan.

## Cara memasang di GitHub

1. Buka repository `https://github.com/smartlab738-max/Grafik-Lapi-2`.
2. Ganti **hanya `index.html`** dengan yang ada di paket ini. Klik **Commit changes**.
3. **Jangan menimpa `rekap-data/rekap-listrik.json` yang sudah ada di GitHub**, agar hasil edit/input terbaru tidak hilang. Gunakan file JSON dari paket ini **hanya jika file database belum ada di repository**.
4. Buka `https://smartlab738-max.github.io/Grafik-Lapi-2/` dan refresh paksa (Ctrl + Shift + R) jika masih melihat tampilan lama.

## Menyimpan perubahan data

Tab Pengaturan Data → edit angka/tambah data → Simpan ke GitHub. Dashboard menggunakan API GitHub untuk memperbarui file `rekap-data/rekap-listrik.json` dan perlu fine-grained PAT berizin Contents: Read and write untuk repository `Grafik-Lapi-2` (dimasukkan dalam sesi halaman). Jangan masukkan token ke HTML atau JSON publik.

**Batasan penting:** angka anomali tidak otomatis diperbaiki. Status sementara bukan total final dan hari tanpa nilai tidak dianggap 0. Perubahan data di dalam draf browser tidak akan tersimpan secara online sebelum tombol Simpan ke GitHub berhasil.
