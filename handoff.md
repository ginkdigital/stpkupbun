# STPKU Pangkalan Bun — Handoff Document

**Tanggal:** 24 Juni 2026
**Status:** Phase 1 + Blog Complete

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

### Blog (NEW)
- [x] Content Collection setup (Astro v7 glob loader)
- [x] `/blog` index page
- [x] `/blog/[slug]` dynamic pages
- [x] 3 sample articles published
- [x] Nav link to Blog added
- [x] Image assets copied (IQC.jpg, HIT.jpg, Logo KU.png)

### Image Assets
- [x] `public/images/Donasi/IQC.jpg`
- [x] `public/images/Donasi/HIT.jpg`
- [x] `public/images/Copy of Logo KU.png`

---

## Pending Tasks

### High Priority
1. **Submit sitemap ke Google Search Console**
   - Add property: `https://stpkupbun.pages.dev`
   - Submit: `https://stpkupbun.pages.dev/sitemap-index.xml`

2. **Redirect 301 WordPress → Astro**
   - Hubungi admin WordPress
   - Setup di .htaccess atau plugin Redirection
   - Note: User perlu akses ke WordPress lama

3. **Write 16 remaining articles** dari masco_19_artikelseo.json
   - Blueprint ada di `../MascoKU/masco_19_artikelseo.json`
   - Sudah ada 3 sample posts (draft 1, 2, 3)
   -剩下 16 articles

### Medium Priority
4. **AIKU Generator** — Cloudflare Access protection
5. **Full image copy** dari ImageKU/ ke public/

### Low Priority
6. **Performance** — Lazy loading, font optimization
7. **Analytics** — Cloudflare Analytics
8. **OG images** untuk blog posts
