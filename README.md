# Rutin — sembilan kebiasaan harian

Aplikasi web satu halaman untuk mencatat rutin harian, melihat grafiknya, dan menulis catatan singkat. Tanpa akun, tanpa server, tanpa build step. Semua data tersimpan di peramban (`localStorage`) pada perangkat yang kamu pakai.

## Isi folder

```
index.html              aplikasi lengkap (HTML + CSS + JS, tanpa dependensi build)
manifest.webmanifest    nama & ikon saat dipasang ke layar utama
sw.js                   service worker — bisa dibuka offline setelah sekali dibuka
icon-192.png            ikon
icon-512.png            ikon
icon-maskable-512.png   ikon untuk Android (safe area)
.nojekyll               mencegah GitHub Pages memproses folder dengan Jekyll
```

## Cara pakai

1. Buka aplikasinya.
2. Centang rutin yang sudah kamu lakukan hari ini — bisa di mana saja sepanjang hari.
3. Tulis satu catatan singkat di malam hari (opsional).
4. Buka **Riwayat** untuk melihat tujuh hari terakhir, konsistensi tiap rutin, dan peta 30 hari.
5. Buka **Atur** untuk menambah, mengubah, atau menghapus rutin; mengunduh cadangan; dan mengisi nama penulis.

Hari dianggap **tuntas** bila minimal 75% rutin selesai (dengan 9 rutin = 7 rutin). Angka target ini dihitung otomatis bila jumlah rutin berubah.

## Upload ke GitHub Pages

1. Buat repositori baru yang **public** (misalnya `rutin`).
2. Upload **isi** folder ini ke root repositori — `index.html` harus ada di root, bukan di dalam subfolder.
3. Buka **Settings → Pages**, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu **Save**.
4. Tunggu 1–2 menit, buka `https://<username>.github.io/rutin/`.

Aplikasi langsung jalan; tidak ada proses build.

## Catatan penting soal data

- Data tersimpan per alamat situs. `file://`, `https://username.github.io/rutin/`, dan domain sendiri adalah tiga basis data yang berbeda.
- Menghapus data peramban (atau memakai mode privat) akan menghapus riwayat.
- Selalu unduh cadangan lewat **Atur → Unduh cadangan (.json)** sebelum pindah perangkat atau mengganti alamat.
- Memasang ke layar utama membuat aplikasi bisa dibuka offline setelah satu kali dibuka online.

## Kustomisasi cepat

- Warna & tipografi: blok `:root` di dalam `<style>` pada `index.html`.
- Rutin awal: array `DEFAULT_HABITS` di dalam `<script>`.
- Nama aplikasi: `<title>`, `.brand span`, `manifest.webmanifest`, dan `apple-mobile-web-app-title`.

Dibuat dengan HTML, CSS, dan JavaScript biasa — tanpa framework, tanpa pelacak.
