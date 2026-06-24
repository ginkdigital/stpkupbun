# STP Khoiru Ummah Pangkalan Bun Website

## Project Overview

Website static untuk STP Khoiru Ummah Pangkalan Bun — sekolah Islam tahfizh di Kalimantan Tengah. Project ini membangun ulang website dari WordPress ke Astro + Cloudflare Pages untuk kontrol penuh dan performa optimal.

**Target utama:** Landing page fundraising DonasiKU dengan goal Rp 195.000.000 untuk program IQC (Islamic Quiz Competition) dan HIT (Halaqah Intensive Training) 2026.

```
Repository: https://github.com/ginkdigital/stpkupbun
Live URL: https://stpkupangkalanbun.pages.dev
```

## Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| Astro | 7.x | Static Site Generator |
| Tailwind CSS | v4 | Styling (via @tailwindcss/vite) |
| @astrojs/sitemap | 3.x | Auto-generated sitemap |
| Cloudflare Pages | - | Deployment target |

## Pages

| Page | Path | Status | Description |
|------|------|--------|-------------|
| Beranda | `/` | ✅ | Landing page utama dengan hero, info sekolah, program |
| DonasiKU | `/donasiku` | ✅ | Landing page fundraising dengan progress tracker |
| Blog | `/blog` | ⏳ | Daftar artikel SEO |
| Blog Post | `/blog/[slug]` | ⏳ | Template artikel individual |
| AIKU Generator | `/aiku-nisa-generator` | ⏳ | Tools internal (proteksi Cloudflare Access) |

## Design System

### Colors (Tailwind CSS Custom)

```css
/* Primary */
--emerald-600: #1a6b4a   /* Tombol utama, heading */
--emerald-500: #2d8a61   /* Hover state */
--emerald-100: #e8f4ef   /* Background pale */

/* Accent */
--gold-500: #c9a84c      /* Badge, highlight */
--gold-300: #f0d98a       /* Hover */
--gold-100: #fdf8ec       /* Background pale */

/* Text */
--ink: #1a1f1c           /* Primary text */
--ink-muted: #4a5550      /* Secondary text */
--ink-faint: #8a9890      /* Tertiary text */

/* Background */
--cream: #faf7f2         /* Main background */
--white: #ffffff

/* Utility */
--wa: #25D366            /* WhatsApp CTA */
--red-progress: #dc4a3d  /* Progress "kurang" */
--border: rgba(26, 107, 74, 0.15)
```

### Fonts

```html
<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Amiri:ital,wght@0,400;0,700;1,400&family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
```

| Usage | Font |
|-------|------|
| Headings, Arabic text | `Amiri` (serif) |
| Body text | `Plus Jakarta Sans` (sans-serif) |

### Components

| Class | Usage | Styles |
|-------|-------|---------|
| `.geo-bg` | Background pattern | SVG geometric Islamic pattern |
| `.reveal` | Scroll animation | fade-up on viewport entry |
| `.animate-fade-up` | Hero animation | staggered fade-in |
| `.progress-bar-fill` | Progress bar | gradient emerald→gold, 1.5s transition |

## Data Institution (Hardcoded)

Data ini di-hardcode di `src/layouts/BaseLayout.astro` dan digunakan di seluruh halaman.

```javascript
const institution = {
  name: "STP Khoiru Ummah Pangkalan Bun",
  shortName: "STPKU",
  tagline: "Sekolah Penghafal Al-Qur'an dan Pemimpin Masa Depan",
  address: "Pangkalan Bun, Kotawaringin Barat, Kalimantan Tengah",
  phone: "klikaja.app/tanyakupbun",
  wa: "https://wa.me/6281234567890",
  bank: "Bank Syariah Indonesia (BSI)",
  rekening: "7148055488",
  atasNama: "Megawati Apriani",
  stats: {
    tahun: "8",
    santo: "51",
    asatidz: "11"
  }
}
```

### Koordinat & Geo

```
Latitude: -2.6833
Longitude: 111.6167
Postal Code: 74112
```

## SEO Configuration

### robots.txt
```
User-agent: *
Allow: /
Disallow: /aiku-nisa-generator/
Sitemap: https://stpkupangkalanbun.pages.dev/sitemap-index.xml
```

### JSON-LD Schema (DonasiKU)

EducationalOrganization + DonateAction schema di `src/pages/donasiku.astro`.

### Sitemap

Auto-generated oleh `@astrojs/sitemap` → `/sitemap-index.xml`

## Pending Tasks

### High Priority
1. **Blog + 19 Artikel** — Setup Content Collections, migrate 19 artikel dari masco_19_artikelseo.json
2. **Submit sitemap ke GSC** — Google Search Console verification
3. **Redirect 301** — WordPress lama → Astro baru

### Medium Priority
4. **AIKU Generator Page** — Tools internal dengan Cloudflare Access protection
5. **Image Assets** — Copy logo dan gambar dari ImageKU/ ke public/

### Low Priority
6. **Performance Optimization** — Image lazy loading, font optimization
7. **Analytics** — Cloudflare Analytics atau alternatif

## Reference Files

### Brief & Task Files
```
../MascoKU/Brief_Build_Astro_STPKU_CloudflarePages.md  - Spesifikasi teknis lengkap
../MascoKU/masco_19_artikelseo.json                    - Blueprint 19 artikel blog
../MascoKU/Task15_Artikel_Pilar_DonasiKU.md            - Konten pilar DonasiKU
../MascoKU/Task16_GEO_Schema_Markup_DonasiKU.md         - JSON-LD schema markup
../MascoKU/Task17_Jadwal_19_Artikel_SEO.md            - Jadwal publikasi artikel
../MascoKU/Task18_OnPage_SEO_Internal_Linking.md      - SEO internal linking
```

### Design Reference
```
../MascoKU/donasiku_page.html   - Reference HTML lengkap dari slugpost.com
```

### Aset Gambar
```
../ImageKU/                         - Folder source gambar
  Copy of Logo KU.png              - Logo hexagonal hijau
  Copy of STP Khoiru Ummah Pangkalan Bun.jpg  - Logo dengan teks
  Copy of flayer SPMB.jpg          - Poster SPMB SD
  Donasi/IQC.jpg, HIT.jpg         - Gambar program donasi
```

## Project Structure

```
stpkupbun/
├── src/
│   ├── layouts/
│   │   └── BaseLayout.astro      # Main layout (nav + footer + scripts)
│   ├── pages/
│   │   ├── index.astro          # Landing page
│   │   ├── donasiku.astro       # Donation page
│   │   └── blog/
│   │       ├── index.astro      # Blog listing (pending)
│   │       └── [slug].astro     # Article template (pending)
│   ├── content/
│   │   └── blog/                # Markdown articles (pending)
│   └── styles/
│       └── global.css           # Tailwind + custom theme
├── public/
│   ├── favicon.svg
│   ├── robots.txt
│   └── images/                  # Optimized images (pending)
├── astro.config.mjs
├── tailwind.config.js           # (Astro v4 auto-detect)
├── package.json
└── CLAUDE.md                    # This file
```

## Workflow

### Daily Development
```bash
# 1. Start dev server
npm run dev

# 2. Build for production
npm run build

# 3. Preview build
npm run preview
```

### Deployment
- Push ke `main` branch → auto-deploy ke Cloudflare Pages
- URL: `stpkupangkalanbun.pages.dev`

### Content Update
1. Edit `.astro` files untuk page changes
2. Add markdown files ke `src/content/blog/` untuk artikel baru
3. Push → Cloudflare auto-rebuild

## Notes

- Website masih dalam development (Task #51 selesai ✅)
- Data donasi masih hardcoded — belum ada CMS/database
- AIKU Generator menggunakan Cloudflare Access untuk proteksi
- Logo dan gambar belum di-copy ke `/public` — masih referensi path eksternal
