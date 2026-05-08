# Instant Password Generator

> **Bulk Password Generator** — Generate up to 50 cryptographically secure passwords. CSV, JSON, numbered, and plain text output.
> Site operated by Kokal Operations Ltd, United Kingdom.

---

## Deployment

```
instantpasswordgenerator.org → CNAME → kokallimited.github.io/instantpasswordgener
```

Push to `main` → GitHub Pages deploys automatically.

---

## ⚠️ SEO Architecture — Individual Blog Post URLs

**Each blog post is a standalone HTML file with its own indexable URL.**

```
/blog/bulk-password-generation-active-directory.html
/blog/powershell-bulk-password-scripts.html
/blog/nist-800-63b-2025-it-admin-guide.html
/blog/csv-password-pipelines-iam-import.html
/blog/enterprise-password-reset-automation.html
/blog/entropy-length-beats-complexity.html
```

`post.json` contains **metadata only** — no full content.
`blog.html` reads post.json and renders cards that **link to** `/blog/*.html` directly.
There is **no modal or JavaScript content loading** for blog posts.

**To add a new post:**
1. Create `/blog/new-slug.html` — copy an existing post as template
2. Update `<title>`, canonical URL, OG tags, article content
3. Update Article and BreadcrumbList JSON-LD schemas
4. Add metadata entry to `post.json` with `"url": "/blog/new-slug.html"`
5. Add URL to `sitemap.xml`
6. Push — GitHub Actions regenerates sitemap automatically

---

## File Inventory

| File | Purpose |
|------|---------|
| `index.html` | Homepage + Bulk Password Generator |
| `blog.html` | Blog index — reads post.json, links to /blog/*.html |
| `/blog/bulk-password-generation-active-directory.html` | Individual indexable post URL |
| `/blog/powershell-bulk-password-scripts.html` | Individual indexable post URL |
| `/blog/nist-800-63b-2025-it-admin-guide.html` | Individual indexable post URL |
| `/blog/csv-password-pipelines-iam-import.html` | Individual indexable post URL |
| `/blog/enterprise-password-reset-automation.html` | Individual indexable post URL |
| `/blog/entropy-length-beats-complexity.html` | Individual indexable post URL |
| `contact.html` | Contact form |
| `privacy-policy.html` | UK GDPR |
| `affiliate-disclosure.html` | FTC + ASA/CAP |
| `terms.html` | England & Wales |
| `cookie-policy.html` | Cookie table + live toggle (key: `ipg-ck`) |
| `404.html` | Custom 404 |
| `post.json` | Blog metadata only — no full post content |
| `robots.txt` | GPTBot, ClaudeBot, PerplexityBot explicitly allowed |
| `llms.txt` | AI citation guidance |
| `sitemap.xml` | All URLs including all /blog/ posts |
| `README.md` | This file |
| `.github/workflows/update-sitemap.yml` | Auto-regenerates sitemap on push |
| `.github/workflows/validate-html.yml` | Validates SOP requirements on PR |

---

## Brand Identity

| Element | Value |
|---------|-------|
| Primary colour | `#8b5cf6` |
| Background | `#0d0b1a` |
| Body font | 'Inter',system-ui,sans-serif |
| Mono font | 'JetBrains Mono',monospace |
| Border radius | `8px` |
| Cookie key | `ipg-ck` (localStorage) |

---

## SOP Validation Checklist

- [ ] 15+ files present (15 core + 6 blog posts)
- [ ] Each `/blog/*.html` has canonical URL, OG tags, Article schema, BreadcrumbList
- [ ] `post.json`: 6 posts, 1 featured, all have `/blog/` url field
- [ ] `blog.html`: links to `/blog/slug.html` — no modal / no `openP()`
- [ ] `sitemap.xml`: includes all 6 `/blog/` post URLs
- [ ] `robots.txt`: GPTBot, ClaudeBot, PerplexityBot allowed
- [ ] All affiliate links: `rel="nofollow sponsored"`
- [ ] Cookie key `ipg-ck` used in localStorage
- [ ] GitHub Actions: `update-sitemap.yml` + `validate-html.yml`

---

*Operated by Kokal Operations Ltd, United Kingdom.*
