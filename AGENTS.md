# AGENTS.md — GitHub Pages Portfolio

## Project Overview
This is Brij Mohan's personal portfolio and publication site built with plain HTML/CSS. It showcases professional work, research publications, blog articles, and advisory roles.

**Key traits:**
- Pure HTML/CSS (no build system, framework, or dependencies)
- Dark theme with sophisticated design system
- Mobile-responsive, semantic structure
- Self-contained pages with embedded or linked styles
- Focus on readability and professional presentation

---

## Site Structure

```
/                     Main landing page (professional bio)
/blog/                Blog articles directory
/research/            Published research & papers
  /ga3ops/            GA3Ops research publication
  /ieee-ccwc-2026/    IEEE CCWC 2026 publication
/judging/             Advisory/judging roles
/assets/              Images, badges, credentials
```

Each section has an `index.html` that serves as the hub for that section.

---

## Design System

### CSS Custom Properties (in page headers)
```css
--bg: #07090f;              /* Primary background */
--bg2: #0d1117;             /* Secondary background */
--bg3: #131922;             /* Tertiary background */
--gold: #c9a84c;            /* Primary accent (highlights, links) */
--gold-dim: #8a6e2f;        /* Muted gold for borders/badges */
--text: #e8e6e0;            /* Primary text */
--text-dim: #8a8880;        /* Muted text (secondary info) */
--text-faint: #3a3835;      /* Very faint text (decorative) */
--border: #1e2530;          /* Border color */
--accent: #1a6bff;          /* Secondary accent (blue) */
--radius: 4px;              /* Border radius */
```

### Typography
- **Serif Display:** `Playfair Display` (headings, hero titles)
- **Monospace:** `JetBrains Mono` (nav, labels, eyebrows, metadata)
- **Body:** `Lato` (article text, descriptions)
- Loaded from Google Fonts

### Common Patterns
1. **Sticky Navigation:** Links to parent (e.g., `← Research`) and home (`BM / bmdayal`)
2. **Eyebrows:** Uppercase labels above titles using JetBrains Mono + gold color
3. **Meta Grid:** Cards displaying publication metadata (grid layout with 200px min columns)
4. **Buttons:** `.btn-primary` (filled gold) and `.btn-secondary` (outlined)
5. **Placeholder Content:** `.placeholder-note` with dashed border for TODO sections

---

## Adding New Content

### Blog Post
1. Create `blog/article-slug/index.html`
2. Use the template from `/blog/index.html` as reference
3. Include hero section with title, eyebrow, and date
4. Link back to `/blog/` and `/` (home)
5. Keep max-width ~860px for readability
6. Update [blog index](blog/index.html) with link to new post

### Research Publication
1. Create `research/project-name/index.html`
2. Use template from `/research/ieee-ccwc-2026/index.html`
3. Include:
   - Paper eyebrow (conference name, year, "Peer-Reviewed")
   - Authors with author name **bold**
   - Meta grid with DOI, Journal, Year, Institutions
   - Abstract block with `.abstract-block` class
   - Links to external resources (DOI, PDF, etc.)
4. Update [research index](research/index.html) with publication card

### New Section
1. Create new directory with `index.html`
2. Implement sticky nav linking to home and parent sections
3. Use consistent color scheme and typography
4. Ensure mobile responsiveness (`@media (max-width: 768px)`)

---

## Meta Information Guidelines

All pages should include:
- `<title>` — Page title (max ~60 characters)
- `<meta name="description">` — Concise summary for search/social (max ~160 chars)
- `<meta name="viewport">` — Always include for mobile support
- Open Graph / social meta tags (optional, for sharing optimization)

Example:
```html
<meta name="description" content="VP & Principal Software Developer at LPL Financial. Agentic AI, Cloud-Native Architecture, and AI-powered product development." />
```

---

## CSS Management

**Current state:** CSS is embedded in each page `<style>` tag. If making significant changes:
- Extract repeated styles to [style.css](style.css) to reduce duplication
- Maintain the embedded approach for self-contained pages, or consolidate as needed
- Keep responsive breakpoints at `@media (max-width: 768px)`

---

## Navigation & Links

- **Home:** `/` (from anywhere, use `href="/` or relative paths like `../../`)
- **Relative links:** Use `../` for parent navigation (back links)
- **Breadcrumb pattern:** Home > Section > Subsection
- **External links:** Always include `target="_blank"` for third-party sites (DOI, GitHub, etc.)

---

## Assets & Images

Images stored in `/assets/`:
- Profile photo: `brij.jpeg`
- Credential badges: AWS certs, PMP, TOGAF, FTC, Advisory Council, etc.
- Reference in pages with `<img src="/assets/filename">`

---

## Best Practices for Agents

1. **Preserve design consistency:** Match existing color scheme, typography, and spacing
2. **Test responsiveness:** Ensure mobile layout works (max-width: 768px)
3. **Semantic HTML:** Use `<nav>`, `<section>`, `<footer>`, `<article>` appropriately
4. **Accessibility:** Include alt text for images, semantic structure, sufficient color contrast
5. **Link management:** Keep relative links working; update index pages when adding new content
6. **Metadata:** Always populate title and description for SEO
7. **Performance:** Minimize inline styles; consider consolidating CSS as the site grows
