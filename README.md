# NOCTELLE — situs sinematik

<p align="center"><img src="docs/preview/homepage.gif" alt="Pratinjau halaman beranda NOCTELLE" width="720"></p>

Situs HTML/CSS/JS native, tanpa build dan tanpa hosting. **Buka `index.html` langsung di browser** (Chrome/Edge/Firefox).
Semua aset (video, frame, gambar, musik, font) ada di folder lokal, jadi bisa jalan offline.

## Struktur

```
index.html                kerangka halaman, modal Intro (teks ID + EN) dan modal proyek
assets/
  css/style.css           semua gaya (token warna/font di :root)
  css/fonts.part.css      deklarasi @font-face lokal
  js/data.js              ← SEMUA COPY PROYEK & GALERI (edit di sini)
  js/portfolio.js         board halaman 2 + modal detail proyek (tab bagian, halaman, tab info)
  js/app.js               mesin pengalaman: loader, scrub frame, video, scroll per halaman, orb, mata, kursor, audio
  frames/                 150 frame halaman 1 (frame_0001–0150.webp, di-scrub dengan scroll)
  video/                  video halaman 2→3 (desktop + mobile 9:16)
  img/                    page1-bg, page3-bg, scene/ (orb & mata), thumb/, work/ (gambar proyek),
                          others/ (galeri), CREDITS.txt
  fonts/                  Cormorant Garamond & Noto Serif (woff2)
  svg/                    ikon, kursor, panah, logo/favicon
  audio/                  musik latar (ambient.mp3)
```

## Alur & state yang dibuat

1. **Loader** persen + bar → tombol "Masuki Dunia / Enter World" (memulai musik).
2. **Halaman 1** — scroll men-_scrub_ frame 1→80, lalu otomatis main ke 150; kata "portfolio" berpendar muncul.
3. **Halaman 2** — video transisi, lalu **board UX** (4 proyek inti + 5 karya pilihan, hover meredupkan node lain).
   - **Modal proyek**: tab bagian (proyek 1), panah ‹ ›, titik halaman, swipe/scroll horizontal, tombol panah keyboard,
     6 tab info (Ringkasan, Info Proyek, Fokus Inti, Bedah Desain, Kesimpulan, Kalimat Kunci), Esc untuk tutup.
4. **Halaman 3** — video putih lalu still dengan zoom pelan.
5. **Halaman 4** — orb: jejak kursor membuka lapisan lain (scratch reveal), menyentuh orb membalik terang/gelap, cincin teks berputar.
6. **Halaman 5** — transisi "page turn", mata mengikuti kursor; mata kanan = tombol **Other Projects** (modal galeri).
7. Header: **INTRO** (modal profil, tombol English Version ↔ Versi Indonesia), **PROJECTS** dropdown (UX Projects → board langsung, Others → halaman 5), **MUTE/MUSIC**.
8. Kursor emas kustom (default/hover/klik) + jejak; mobile: swipe antar halaman, kursor dimatikan, board bisa di-scroll.

## Mengganti konten

- Nama/brand: cari `NOCTELLE` dan `Mira Solenne` di `index.html` (logo SVG ada di header).
- Proyek, tahun, deskripsi, gambar: `assets/js/data.js`.
- Profil/riwayat kerja: blok `#introModal` di `index.html` (versi `data-intro-lang="id"` dan `"en"`).
- Semua nama perusahaan, sekolah, klien, dan angka adalah **fiktif/placeholder**.

## Catatan aset

- Media memakai stok Mixkit/Unsplash yang di-_grade_ agar mood-nya konsisten.
- Font utama **Noto Serif** untuk teks Indonesia, dipadukan dengan Cormorant Garamond.
- GSAP tidak dipakai; animasi ditulis dengan Web Animations API/CSS.
- Kredit media lengkap: `assets/img/CREDITS.txt`.
