# STPKU Pangkalan Bun — Handoff Document

**Tanggal:** 24 Juni 2026
**Status:** Phase 1 Complete

---

## Project Summary

Website static STP Khoiru Ummah Pangkalan Bun — sekolah Islam tahfizh di Kalimantan Tengah. Rebuild dari WordPress ke Astro + Cloudflare Pages.

**Goal:** Landing page DonasiKU dengan target Rp 195.000.000 untuk IQC & HIT 2026.

```
GitHub: https://github.com/ginkdigital/stpkupbun
Live URL: https://stpkupbun.pages.dev
```

---

## Completed ✅

### Website
- [x] Astro 7.x + Tailwind v4
- [x] Landing page `/`
- [x] DonasiKU `/donasiku`
- [x] JSON-LD schema
- [x] Sitemap
- [x] robots.txt
- [x] Responsive design
- [x] Islamic aesthetic (emerald + gold)

### Design
- [x] Logo KU mark as signature
- [x] Emerald #1a6b4a + Gold #c9a84c
- [x] Dark/light contrast
- [x] Amiri + Plus Jakarta Sans fonts
- [x] Scroll animations

---

## Pending Tasks

### High Priority
1. **Submit sitemap ke Google Search Console**
   - Add property: `https://stpkupbun.pages.dev`
   - Submit: `https://stpkupbun.pages.dev/sitemap-index.xml`

2. **Redirect 301 WordPress → Astro**
   - Hubungi admin WordPress
   - Setup di .htaccess atau plugin Redirection

3. **Copy image assets** ke `/public`
   - Source: `ImageKU/`

### Medium Priority
4. **Blog + 19 Artikel** — Blueprint ada di masco_19_artikelseo.json
5. **AIKU Generator** — Cloudflare Access protection

---

## Tech Stack

```
Astro: 7.x
Tailwind CSS: v4
Cloudflare Pages
```

## Key Files

| File | Purpose |
|------|---------|
| src/layouts/BaseLayout.astro | Nav + footer |
| src/pages/index.astro | Landing page |
| src/pages/donasiku.astro | Donation page |
| src/styles/global.css | Theme |

## Workflow

```bash
npm run dev      # Dev server
npm run build    # Production build
git push main    # Auto-deploy Cloudflare
```

---

## Reference Files

```
../MascoKU/Brief_Build_Astro_STPKU_CloudflarePages.md
../MascoKU/masco_19_artikelseo.json
../ImageKU/ (assets)
```

---

**Created:** 24 Juni 2026
**By:** GINK Digital × Claude Code
