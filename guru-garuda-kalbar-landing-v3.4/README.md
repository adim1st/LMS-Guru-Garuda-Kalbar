# Portal Guru Garuda Kalbar — Landing Page (versi embed LearnWorlds)

Versi: v3.4 · 27 Oktober 2026

## Isi paket

```
index.html                                  ← kode yang ditempel ke blok "Embed code" LearnWorlds
assets/img/hero/thumbnail-kalbar-1.webp     ← foto hero (latar transparan, pudar di bawah)
assets/img/pejabat/gubernur.webp            ← foto resmi Gubernur (bingkai sambutan)
assets/img/pejabat/kadisdikbud.webp         ← foto resmi Kepala Dinas Pendidikan dan Kebudayaan
assets/img/trainer/samanta-elsener-1.webp   ← avatar: Komunikasi Efektif (Conversational Intelligence)
assets/img/trainer/samanta-elsener-2.webp   ← avatar: Kesejahteraan Psikologis Guru
assets/img/trainer/m-noor-fitriyanto.webp   ← avatar: Pemanfaatan KA untuk Media Pembelajaran
assets/img/trainer/tri-marfuah.webp         ← avatar: Strategi Pembelajaran Aktif
assets/img/trainer/amelia-febriani.webp     ← avatar: Motivasi Belajar & Masa Depan Murid
assets/img/trainer/ayoe-sutomo.webp         ← avatar: Penanganan Murid Berperilaku Menantang
assets/img/trainer-umum/rumpun-1-1.webp … rumpun-1-4.webp   ← avatar trainer Rumpun 1 (Pengembangan Diri & Produktivitas)
assets/img/trainer-umum/rumpun-2-1.webp … rumpun-2-4.webp   ← avatar trainer Rumpun 2 (Komunikasi, Public Speaking & Kemitraan)
assets/img/trainer-umum/rumpun-3-1.webp … rumpun-3-4.webp   ← avatar trainer Rumpun 3 (Kepemimpinan & Kerja Tim)
assets/img/trainer-umum/rumpun-4-1.webp … rumpun-4-4.webp   ← avatar trainer Rumpun 4 (Kesejahteraan & Literasi Keuangan)
assets/img/trainer-umum/rumpun-5-1.webp … rumpun-5-4.webp   ← avatar trainer Rumpun 5 (Literasi Digital, Data & Inovasi AI)
```

## Langkah pemasangan

1. Unggah seluruh isi paket ini ke repositori GitHub **publik** (struktur folder `assets/` jangan diubah).
2. Buka `index.html`, cari `PORTAL_CONFIG` → `assets` → `baseUrl`, lalu isi dengan tautan repositori.
   Disarankan memakai CDN jsDelivr (gratis, cepat, khusus repo publik):

   ```js
   baseUrl: "https://cdn.jsdelivr.net/gh/USERNAME/REPO@main/",
   ```

   Ganti `USERNAME` dan `REPO`. Bila file berada di subfolder repo, tambahkan foldernya,
   misalnya `.../REPO@main/landing/`.
3. Salin seluruh isi `index.html` ke blok **Embed code** di LearnWorlds.

Selama `baseUrl` kosong, gambar dicari relatif terhadap halaman. Ini berfungsi bila `index.html` dibuka
langsung dari folder paket atau GitHub Pages, tetapi tidak di LearnWorlds. Jika gambar gagal dimuat,
halaman tetap rapi: hero kembali ke ilustrasi mockup video dan avatar trainer kembali ke inisial nama.

## Mengganti atau menambah foto

- Mengganti foto: timpa file dengan nama yang sama, lalu unggah ulang ke repo.
- jsDelivr menyimpan cache cabang `@main` selama beberapa waktu. Agar perubahan langsung tampil,
  buat tag/rilis di GitHub (misalnya `v3.4`) dan pakai `@v3.4` pada `baseUrl`.
- Trainer baru: tambahkan entri di `PORTAL_CONFIG.trainer` dengan kunci modul (lihat `links.modules`)
  dan path fotonya, misalnya `foto: "assets/img/trainer/nama-trainer.webp"`.
- Foto hero lain: ubah `PORTAL_CONFIG.assets.heroFoto`.
- Foto pimpinan: `PORTAL_CONFIG.assets.fotoGubernur` dan `fotoKadisdikbud` (rasio 4 : 5, 480 × 600 px). Kosong atau gagal dimuat = siluet dengan label "Foto Resmi Segera Diperbarui".
- Avatar Modul Umum diatur di `PORTAL_CONFIG.trainerRumpun` (4 path per rumpun, urutan = urutan tampil).
  Daftar yang dikosongkan menyembunyikan deretan avatar rumpun tersebut.

Format gambar: WebP (didukung semua browser modern). Avatar trainer wajib 320 × 320 px, avatar Modul Umum 240 × 240 px; foto hero 1096 × 728 px.
