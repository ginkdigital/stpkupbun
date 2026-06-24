# STPKU Pangkalan Bun — Handoff Document

**Tanggal:** 24 Juni 2026
**Status:** Phase 1 + Blog Complete
**Live URL:** https://stpkupbun.pages.dev

---

## Yang Sudah Selesai

### Website
- [x] Astro 7.x + Tailwind v4
- [x] Landing page `/`
- [x] DonasiKU `/donasiku`
- [x] Blog `/blog`
- [x] 3 blog posts published
- [x] JSON-LD schema (EducationalOrganization + DonateAction)
- [x] Sitemap auto-generated
- [x] robots.txt
- [x] Responsive design
- [x] Islamic aesthetic (emerald + gold)

### Blog System
- [x] Content Collection dengan Astro v7 glob loader
- [x] `/blog` — listing semua artikel
- [x] `/blog/[slug]` — artikel individual dengan styled prose
- [x] 3 sample articles dari blueprint masco_19_artikelseo.json

### Assets
- [x] `public/images/Donasi/IQC.jpg`
- [x] `public/images/Donasi/HIT.jpg`
- [x] `public/images/Copy of Logo KU.png`

### Navigation
- [x] Link ke Blog ditambahkan di nav

---

## Pending Tasks

### High Priority
1. **Submit sitemap ke Google Search Console**
   - Property: `https://stpkupbun.pages.dev`
   - Sitemap: `https://stpkupbun.pages.dev/sitemap-index.xml`
   - Steps: search.google.com → Add Property → Submit sitemap

2. **Redirect 301 WordPress → Astro**
   - Butuh akses admin WordPress lama
   - Setup di .htaccess atau plugin Redirection
   - Redirect semua URL lama ke URL baru

3. **16 remaining articles** (3 dari 19 sudah)
   - Blueprint: `MascoKU/masco_19_artikelseo.json`
   - Articles done: #1 (parenting), #2 (knowing-vs-being), #3 (testimoni)

### Medium Priority
4. **AIKU Generator** — Cloudflare Access protection
5. **Copy remaining images** dari ImageKU/ ke public/
6. **OG images** untuk blog posts

### Low Priority
7. **Performance** — Lazy loading, font optimization
8. **Analytics** — Cloudflare Analytics

---

## Tech Stack

```
Astro: 7.x
Tailwind CSS: v4 (via @tailwindcss/vite)
Content: Markdown files (glob loader)
Hosting: Cloudflare Pages
```

---

## File Structure

```
stpkupbun/
├── src/
│   ├── content.config.ts          # Astro v7 content config
│   ├── content/
│   │   └── blog/                 # 3 markdown articles
│   ├── layouts/
│   │   └── BaseLayout.astro      # Nav, footer, scripts
│   ├── pages/
│   │   ├── index.astro           # Landing page
│   │   ├── donasiku.astro        # Donation page
│   │   └── blog/
│   │       ├── index.astro        # Blog listing
│   │       └── [slug].astro       # Blog post
│   └── styles/
│       └── global.css             # Theme + animations
├── public/
│   ├── favicon.svg
│   ├── robots.txt
│   └── images/
│       ├── Donasi/
│       │   ├── IQC.jpg
│       │   └── HIT.jpg
│       └── Copy of Logo KU.png
├── astro.config.mjs
└── package.json
```

---

## Deployment

```bash
git push main    # Auto-deploy Cloudflare Pages
```

URL akan ter-update dalam ~1-2 menit setelah push.

---

## Reference Files

```
MascoKU/masco_19_artikelseo.json  # Blueprint 19 artikel (3 done)
MascoKU/Brief_Build_Astro_STPKU_CloudflarePages.md
ImageKU/                            # Source gambar (sudah dicopy sebagian)
```

---

**Created:** 24 Juni 2026
**Updated:** 24 Juni 2026 (Blog phase complete)
**By:** GINK Digital × Claude Code
