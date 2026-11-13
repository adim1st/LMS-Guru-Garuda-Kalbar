# Portal Guru Garuda Kalbar — Landing Page (versi embed LearnWorlds)

Versi: v4.1 · 13 November 2026

## Isi paket

```
index.html                                  ← kode yang ditempel ke blok "Embed code" LearnWorlds
assets/img/hero/thumbnail-kalbar-1.webp     ← foto hero (latar transparan, pudar di bawah)
assets/img/pejabat/gubernur.webp            ← foto resmi Gubernur (bingkai sambutan)
assets/img/pejabat/kadisdikbud.webp         ← foto resmi Kepala Dinas Pendidikan dan Kebudayaan
assets/img/trainer/john-hendry-tafui.webp     ← avatar: Modul Wajib Spesifik Matematika
assets/img/trainer/esti-swatika-sari.webp     ← avatar: Modul Wajib Spesifik Bahasa Indonesia
assets/img/trainer/davina-adinda.webp         ← avatar: Modul Wajib Spesifik Bahasa Inggris
assets/img/trainer/samanta-elsener-3.webp     ← avatar: Modul Wajib Spesifik Bimbingan dan Konseling
assets/img/trainer/angga-liberty-pratama.webp ← avatar: Modul Wajib Spesifik Informatika/TIK
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
  buat tag/rilis di GitHub (misalnya `v3.8`) dan pakai `@v3.8` pada `baseUrl`.
- Trainer baru: tambahkan entri di `PORTAL_CONFIG.trainer` dengan kunci modul (lihat `links.modules`)
  dan path fotonya, misalnya `foto: "assets/img/trainer/nama-trainer.webp"`.
- Profil singkat trainer: isi `profil` (satu kalimat). Bila kosong, baris profil tidak ditampilkan
  Profil Davina Adinda masih berupa deskripsi peran di modul; ganti dengan profil dari CV trainer bila tersedia.
- Foto hero lain: ubah `PORTAL_CONFIG.assets.heroFoto`.
- Foto pimpinan: `PORTAL_CONFIG.assets.fotoGubernur` dan `fotoKadisdikbud` (rasio 4 : 5, 480 × 600 px). Kosong atau gagal dimuat = siluet dengan label "Foto Resmi Segera Diperbarui".
- Avatar Modul Umum diatur di `PORTAL_CONFIG.trainerRumpun` (4 path per rumpun, urutan = urutan tampil).
  Daftar yang dikosongkan menyembunyikan deretan avatar rumpun tersebut.

Format gambar: WebP (didukung semua browser modern). Avatar trainer wajib 320 × 320 px, avatar Modul Umum 240 × 240 px; foto hero 1096 × 728 px.

## Tautan modul (PORTAL_CONFIG → links → modules)

- Semua tautan modul sudah aktif: Modul Wajib Spesifik B1–B5, Modul Wajib Lintas Mapel U1–U6, dan Rumpun Modul Umum 1–5.

## Riwayat perubahan

- v4.1 (13 Nov 2026) – Profil singkat (short brief) ditambahkan pada identitas trainer 5 Modul Wajib Spesifik, sama seperti di Modul Wajib Lintas Mapel. Profil Samanta Elsener memakai kalimat yang sama dengan modul Lintas.
- v4.0 (13 Nov 2026) – Kotak "Informasi Penting": judul diubah menjadi "Informasi Penting & Ketentuan Akses Peserta"; kata "Cabang" dihapus ("didistribusikan melalui Dinas atau sekolah masing-masing"); teks dipecah menjadi dua paragraf dengan jarak antarparagraf.
- v3.9 (13 Nov 2026) – Foto avatar, nama, dan jabatan trainer ditambahkan pada 5 kartu Modul Wajib Spesifik (John Hendry Tafui, S.Pd.; Dr. Esti Swatika Sari, S.Pd., M.Hum.; Davina Adinda, S.H.; Samanta Elsener, M.Psi.; Angga Liberty Pratama, M.Pd.) dengan tampilan sama seperti Modul Wajib Lintas Mapel; 5 avatar baru dibuat dari foto layar hijau dengan latar dan bentuk avatar yang sama. Penulisan gelar diseragamkan dengan titik penutup (M.Psi., M.Pd., M.Si.). Perbaikan lebar kartu Bimbingan dan Konseling di layar ponsel (sebelumnya hanya setengah lebar).
- v3.8 (10 Nov 2026) – Tautan 6 Modul Wajib Lintas Mapel (U1–U6) diisi dengan URL kursus LMS.
- v3.7 (2 Nov 2026) – Tombol "Masuk & Mulai Pelatihan" (dan aksi "Masuk ke LMS" di chatbot) diarahkan ke https://pelatihan-guru-garuda-kalbar.learnworlds.com/profile.
- v3.6 (2 Nov 2026) – Ikon play di tengah ilustrasi stopwatch "10 Menit / Sesi" dihapus; sapaan pop-up chatbot "Ada pertanyaan seputar program? Tekan Helpdesk untuk bertanya." dihapus (tombol Helpdesk tetap).
- v3.5 (2 Nov 2026) – Copywriting 4 kartu sorotan setelah hero: 11 Modul Inti (+20 Modul Pengayaan), 10 Menit / Sesi (Materi Ringkas & Praktis), 100% Fleksibel (Akses Penuh 12 Bulan), Sertifikat Resmi (Terbit Otomatis & Terukur); ilustrasi kartu kedua diganti stopwatch 10 menit. Tautan Modul Wajib Spesifik B1–B5 dan Rumpun 1–5 diisi.
- v3.4 (27 Okt 2026) – versi sebelumnya.
