# STP Khoiru Ummah Pangkalan Bun Website

## Project Overview

Website static untuk STP Khoiru Ummah Pangkalan Bun — sekolah Islam tahfizh di Kalimantan Tengah. Project membangun ulang website dari WordPress ke Astro + Cloudflare Pages dengan desain yang purposeful dan distinctive.

**Target:** Landing page fundraising DonasiKU dengan goal Rp 195.000.000 untuk program IQC (Islamic Quiz Competition) dan HIT (Historical Islamic Trip) 2026.

```
Repository: https://github.com/ginkdigital/stpkupbun
Live URL: https://stpkupbun.pages.dev
```

## Design Philosophy

Mengikuti prinsip **frontend-design** skill:
- **Signature Element** — Logo KU mark sebagai visual anchor
- **Boldness in ONE place** — Hero headline saja bold, sisanya restrained
- **Structure = Truth** — Layout purposeful, setiap section punya meaning
- **Islamic Identity** — Geometric star pattern, gold accent, emerald primary
- **Dark/Light Contrast** — Ink dark sections ↔ white content sections

## Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| Astro | 7.x | Static Site Generator |
| Tailwind CSS | v4 | Styling (via @tailwindcss/vite) |
| @astrojs/sitemap | 3.x | Auto-generated sitemap |
| Cloudflare Pages | - | Deployment target |

## Pages

| Page | Path | Status |
|------|------|--------|
| Beranda | `/` | ✅ Selesai |
| DonasiKU | `/donasiku` | ✅ Selesai |
| Blog | `/blog` | ⏳ Pending |
| Blog Post | `/blog/[slug]` | ⏳ Pending |
| AIKU Generator | `/aiku-nisa-generator` | ⏳ Pending |

## Design System

### Color Palette

```css
/* Primary - Emerald (Hijau Islami) */
--emerald-600: #1a6b4a   /* Main buttons, headings */
--emerald-500: #2d8a61   /* Hover states */
--emerald-100: #e8f4ef     /* Light backgrounds */

/* Accent - Gold (Emas) */
--gold-500: #c9a84c        /* Highlights, badges */
--gold-300: #f0d98a        /* Hover */
--gold-100: #fdf8ec        /* Light backgrounds */

/* Dark (Ink) - Background utama */
--ink: #1a1f1c              /* Dark sections */
--ink-muted: #4a5550        /* Text on light */
--ink-faint: #8a9890        /* Tertiary text */

/* Utility */
--wa: #25D366               /* WhatsApp green CTA */
--red-progress: #dc4a3a     /* Progress "kurang" */
```

### Typography

| Usage | Font | Weight |
|-------|------|--------|
| Headings | Amiri (serif) | 700 (bold) |
| Arabic text | Amiri (serif) | 400 (normal) |
| Body | Plus Jakarta Sans | 400-600 |
| Labels | Plus Jakarta Sans | 600-700 (semibold-bold) |

### Visual Hierarchy

```
┌─────────────────────────────────┐
│  NAV (dark)                      │
│  [KU logo] STPKU  [Donasi Now]  │
├─────────────────────────────────┤
│  HERO (islamic-pattern)          │
│         KU MARK                  │  ← Signature element
│    Headline (bold ONE place)     │
│    Stats bar                     │
│    [CTA Button]                 │
├─────────────────────────────────┤
│  SECTION (white bg)              │  ← Content truth
│  School info, stats grid         │
├─────────────────────────────────┤
│  SECTION (dark bg)               │
│  Program cards                   │
├─────────────────────────────────┤
│  SECTION (emerald bg)            │
│  Progress tracker               │
├─────────────────────────────────┤
│  FOOTER (dark)                  │
│  Minimal copyright               │
└─────────────────────────────────┘
```

### Components

| Class | Purpose |
|-------|---------|
| `.islamic-pattern` | Hero background dengan radial gradient + subtle pattern |
| `.section-light` | White background sections (ink text) |
| `.reveal` | Scroll-triggered fade-up animation |
| `.animate-fade-up` | Hero staggered entrance |
| `.progress-card` | Progress bar container |
| `.progress-bar-fill` | Animated progress fill |

## Data Institution

Hardcoded di `src/layouts/BaseLayout.astro` dan page files:

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

### Geo Data
```
Latitude: -2.6833
Longitude: 111.6167
Postal Code: 74112
```

## SEO

### robots.txt
```
User-agent: *
Allow: /
Disallow: /aiku-nisa-generator/
Sitemap: https://stpkupbun.pages.dev/sitemap-index.xml
```

### JSON-LD Schema

EducationalOrganization + DonateAction di `src/pages/donasiku.astro`

## Pending Tasks

### High Priority
1. **Blog + 19 Artikel** — Content Collections + markdown dari masco_19_artikelseo.json
2. **Submit sitemap ke GSC** — Google Search Console
3. **Redirect 301** — WordPress lama → stpkupbun.pages.dev

### Medium Priority
4. **AIKU Generator** — Cloudflare Access protection
5. **Image Assets** — Copy dari ImageKU/ ke public/

### Low Priority
6. **Performance** — Lazy loading, font optimization
7. **Analytics** — Cloudflare Analytics

## Reference Files

### Brief & Task
```
../MascoKU/Brief_Build_Astro_STPKU_CloudflarePages.md
../MascoKU/masco_19_artikelseo.json
../MascoKU/Task15_Artikel_Pilar_DonasiKU.md
../MascoKU/Task16_GEO_Schema_Markup_DonasiKU.md
```

### Design Reference
```
../MascoKU/donasiku_page.html   - Reference HTML dari slugpost.com
```

### Aset
```
../ImageKU/                    - Source gambar
  Logo KU.png                 - Logo hexagonal
  Donasi/IQC.jpg, HIT.jpg    - Program images
```

## Project Structure

```
stpkupbun/
├── src/
│   ├── layouts/
│   │   └── BaseLayout.astro     # Nav, footer, scripts
│   ├── pages/
│   │   ├── index.astro          # Landing page
│   │   ├── donasiku.astro       # Donation page
│   │   └── blog/
│   │       ├── index.astro     # (pending)
│   │       └── [slug].astro    # (pending)
│   ├── content/
│   │   └── blog/               # (pending)
│   └── styles/
│       └── global.css          # Tailwind + theme
├── public/
│   ├── favicon.svg
│   └── robots.txt
├── astro.config.mjs
├── package.json
└── CLAUDE.md
```

## Workflow

### Development
```bash
npm run dev      # Dev server
npm run build    # Production build
npm run preview  # Preview build
```

### Deployment
- Push ke `main` → auto-deploy Cloudflare Pages
- URL: `https://stpkupbun.pages.dev`

## Notes

- Desain mengikuti frontend-design principles
- Dark/light contrast untuk visual hierarchy
- Data masih hardcoded (belum CMS)
- AIKU Generator pakai Cloudflare Access
- Logo/gambar perlu di-copy ke /public
