# Architecture

Single-file static site. No build pipeline.

## Files

| File | Purpose |
|---|---|
| `index.html` | Self-contained dashboard. All HTML, CSS, JS, and content inline. |
| `Span Image.jpeg` | Banner image used under the KPI strip. |
| `README.md` | Repo overview + live site link. |
| `ARCHITECTURE.md` | This file. |

## Stack

- **Hosting**: GitHub Pages (Apple internal, branch: `main`)
- **Design system**: Apple Bridge (CSS variables for light/dark; SF Pro typography)
- **Theme**: System-preference auto-detect on load; manual toggle button in hero
- **No dependencies**: Zero CDNs, zero JS frameworks, no `fetch()` calls

## Sections (in order)

1. Hero (title links to McCombs Exec Ed)
2. Repo-meta pill (version badge + last-updated date + GitHub link)
3. KPI strip (3 cards) + banner image
4. § 01 Program Overview *(collapsed by default)*
5. § 02 The Learning Arc — 6 module cards *(collapsed by default)*
6. § 03 Faculty *(collapsed by default)*
7. § 04 Seth's Detailed Session Notes — 10 lecture cards *(open by default)*
8. § 05 What I Can Apply Monday — 10 numbered takeaways *(collapsed)*
9. § 06 Cohort Ratings *(collapsed)*
10. § 07 What Past Attendees Said *(collapsed)*
11. § 08 Logistics & Credentials *(collapsed)*
12. Footer

## Interactivity

- All §1–§8 sections are wrapped in `<details>` for CSS-only collapse/expand
- Each section header shows a black "Expand" pill (white "Collapse" when open) — inverted in dark mode
- Theme toggle in the hero supports manual light/dark override; system preference is respected on load

## Conventions

- Apple Bridge color tokens only (no raw hex in body content)
- 4px spacing grid (4, 8, 12, 16, 24, 32, 48px)
- External links suffixed with `↗`
- All section headings carry stable IDs (`#s1` through `#s8`) for deep-linking
