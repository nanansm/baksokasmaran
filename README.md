# Biolink Bakso Kasmaran

Pengganti `linktr.ee/baksokasmaran`. Statis (HTML + CSS, tanpa build), pola sama seperti repo `kedainasi_sinarberkah`.

**Live: https://baksokasmaran.com** (GitHub Pages + custom domain).

## Isi

| File | Keterangan |
|---|---|
| `index.html` | Halaman biolink + Meta Pixel `2303590427123174` |
| `style.css` | Sistem visual (bar teal, tombol bayangan padat, slideshow) |
| `assets/` | Foto, logo, OG image |
| `fonts/` | Androgyne + Poppins (woff2 subset latin, self-host) |

## Desain — dari mana asalnya

Semua elemen diturunkan dari materi IG/TikTok Agustus 2026 buatan tim (Drive `AGUSTUS/FILE PUBLISH`), bukan template biolink generik:

- **Footer bar teal** berisi alamat · jam · wordmark — salinan footer materi feed.
- **Wordmark Androgyne** dari file font asli klien.
- **Tombol** pakai bayangan padat offset (bukan blur), senapas dengan gaya sticker di materi feed.
- **Slideshow 5 foto**, ganti tiap 2 detik, berulang (CSS murni, tanpa JS). Semua foto ditampilkan **utuh tanpa crop** — kanvas 3:4, sisa ruang diisi putih supaya menyatu dengan kartu.
- Latar halaman pakai foto interior yang di-blur tipis.
- Palet merah `#EB3237` + teal `#3698A5` hasil sampling piksel dari materi tim.

## Tracking

Pixel dipasang di `<head>`. Event per tombol:

| Tombol | Event |
|---|---|
| WhatsApp | `Contact` |
| Lokasi & Ulas Google | `FindLocation` |
| Menu | `ViewMenu` (custom) |
| TikTok | `ClickTikTok` (custom) |

Belum ada slug redirect ber-`Lead` seperti `sinarberkah.com/wanasibox`. Kalau iklan Agustus butuh tier intent tinggi, tinggal tambah folder `promo/index.html` dengan pola interstitial yang sama.

## SEO

- `canonical` + OG absolut + `twitter:card` + OG image 1200×630
- **JSON-LD `Restaurant`**: alamat, koordinat (-6.913934, 107.6151509), jam 07.00–19.00, `hasMenu`, `hasMap`, amenity, sameAs IG/TikTok
- `h1` terlihat berisi keyword utama + `h2` pada blok konten (halaman tidak lagi thin content — ±180 kata)
- `sitemap.xml` + `robots.txt`
- Favicon 32/64 + apple-touch-icon 180

Target keyword realistis: **brand** (bakso kasmaran, bakso kasmaran bandung) dan **long-tail** (bakso kelapa bandung, bakso dalam batok kelapa, sate jando bandung, bakso jl kalimantan bandung). Keyword umum "bakso bandung" dikuasai listicle media besar — perang di situ lewat Google Business Profile + ulasan, bukan lewat halaman ini.

⚠️ Link Maps lama (`maps.app.goo.gl/u54qgzapcljzxski8`, dipakai Linktree) **sudah mati** — diganti link CID permanen `maps.google.com/?cid=16718282620338350132`.

## Cara lihat lokal

```bash
cd ~/Documents/GitHub/baksokasmaran
python3 -m http.server 8765
# buka http://localhost:8765
```

## Deploy

`git push origin main` → live ±45 detik kemudian. Domain `baksokasmaran.com` via file `CNAME`.

## Belum diputuskan

- Jam buka: materi Agustus tertulis **07.00–19.00**, brand brief lama tertulis 10.00–19.00. Halaman ini pakai 07.00–19.00.
- Menu menunjuk folder Google Drive. Opsi berikutnya: jadikan halaman `menu/` sendiri (bisa di-index Google, lebih cepat di HP).
- Link GoFood/GrabFood/ShopeeFood belum ada datanya.
