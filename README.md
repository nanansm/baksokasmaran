# Biolink Bakso Kasmaran

Pengganti `linktr.ee/baksokasmaran`. Statis (HTML + CSS, tanpa build), pola sama seperti repo `kedainasi_sinarberkah`.

**Status: lokal saja. Belum di-commit, belum di-push, belum ada domain.**

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

## Cara lihat lokal

```bash
cd ~/Documents/GitHub/baksokasmaran
python3 -m http.server 8765
# buka http://localhost:8765
```

## Kalau nanti dideploy (GitHub Pages)

1. Buat repo `nanansm/baksokasmaran`, push branch `main`.
2. Settings → Pages → source `main` / root.
3. Tambah file `CNAME` berisi domain, lalu DNS: 4 A record `185.199.108–111.153` + CNAME `www` → `nanansm.github.io` (mode DNS-only kalau lewat Cloudflare).
4. Ganti link Linktree di bio IG & TikTok.

## Belum diputuskan

- Domain (`baksokasmaran.com`? subdomain?) — belum dibeli.
- Jam buka: materi Agustus tertulis **07.00–19.00**, brand brief lama tertulis 10.00–19.00. Halaman ini pakai 07.00–19.00.
- Menu masih menunjuk PDF di Google Drive (sama seperti Linktree). Opsi berikutnya: jadikan halaman `menu/` sendiri.
- Link GoFood/GrabFood/ShopeeFood belum ada datanya.
