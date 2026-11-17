# Grafik Lapi 2 — Website Rekap Listrik

Paket untuk repository GitHub **smartlab738-max/Grafik-Lapi-2**. Terdiri atas website statis dan JSON data awal dari Excel yang Anda kirim. Tidak memerlukan MySQL atau PHP.

## Struktur yang perlu di-upload ke GitHub

```text
Grafik-Lapi-2/
├── index.html
└── rekap-data/
    └── rekap-listrik.json
```

**Repository:** https://github.com/smartlab738-max/Grafik-Lapi-2

**Alamat website setelah GitHub Pages aktif:** https://smartlab738-max.github.io/Grafik-Lapi-2/

## Cara upload

1. Ekstrak ZIP ini. Di repository GitHub pilih **Add file > Upload files** (atau **uploading an existing file** jika repository masih kosong).
2. Seret `index.html` dan folder `rekap-data` sekaligus agar hierarki folder dipertahankan. Pastikan file JSON berada dalam `rekap-data/`, bukan di root.
3. Pilih **Commit changes** ke branch `main`.
4. Masuk **Settings > Pages > Build and deployment**, pilih **Deploy from a branch**, branch **main**, direktori **/(root)**, lalu **Save**.
5. Buka alamat website dan muat ulang setelah terbit.

## Mengisi dan menyimpan data

- Pilih tahun/bulan dan panel.
- Gunakan **Tambah / Edit Pembacaan Meter** untuk memasukkan tanggal, jam, dan stand terbaru. Input pada tanggal tahun baru akan menambah pilihan tahun otomatis.
- Koreksi per hari langsung dari tabel. Pilih **Unduh JSON** untuk backup.
- Untuk menyimpan perubahan **online**, buat token GitHub fine-grained dengan repository **Grafik-Lapi-2** saja dan izin **Repository permissions > Contents: Read and write**. Masukkan token di **Pengaturan Penyimpanan GitHub**, klik **Aktifkan Token**, lalu **Simpan ke GitHub**. Anda tidak perlu mengetik path manual.
- Token tidak disimpan permanen di HTML/JSON/browser storage. Jangan pernah mengunggah atau membagikan token. Jika token lama pernah dibagikan, cabut terlebih dahulu.

Data awal JSON berukuran lebih dari 1 MB. Website menyertakan cara membaca blob GitHub untuk memeriksa versi file sebelum menyimpan, sehingga tidak tanpa sengaja menimpa revisi lain.

**Peringatan:** Jika di repository sudah ada `rekap-data/rekap-listrik.json` dengan data lebih baru, jangan overwrite dengan file awal ini. Pertahankan database terbaru.

## Tahun/NTP

Tahun historis berdasarkan tanggal pada file Excel; tahun berjalan berdasarkan jam komputer (umumnya disinkronkan via NTP). Browser tidak mengakses NTP langsung.

## Mode lokal

Karena membaca JSON via `fetch`, jalankan pada GitHub Pages atau server lokal. Jangan dibuka dengan skema `file://` bila ingin data bisa dimuat.
