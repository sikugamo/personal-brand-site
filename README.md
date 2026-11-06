# Kai Chen · Personal site

A bilingual (English / 简体中文) personal brand site for an AI and tech content creator. It has three sections: **Resources**, **Articles** and **About**.

It's a single static file (`index.html`) with no build step and no dependencies apart from Google Fonts.

## Design

The design takes inspiration from [oiloil.org](https://oiloil.org) without copying it.

- **Look:** a quiet white page with near-black text and lighter grey tints, system fonts, hairline rules, and small uppercase monospace labels.
- **Accents:** a periwinkle highlighter and a sparing electric-blue accent.
- **Catalog structure:** numbered sections (01 Articles, 02 Resources, 03 About, 04 Elsewhere), `2026.10.28`-style dates, and `→` / `↗` link labels.
- **Hype filter (hero):** a card that swaps an AI marketing claim for what the test actually found. It flips once on load; visitors can then toggle it and page through claims.
- **Live resource mockups:** every resource card draws a small working mockup of itself in HTML and CSS: a prompt file, an agent trace, an eval sheet, a tool database, a checklist, a course outline.
- **Copy for your LLM:** each article has a button that copies it as Markdown, ready to paste into a chat.
- **Motion:** springy hover lifts and a gentle pointer tilt. It respects `prefers-reduced-motion`.
- **Themes:** light, with a dark theme. The footer switch offers Light / Auto / Dark.

## Languages

- **Switching:** use the `EN / 中文` control in the top bar.
- **First visit:** the site follows the browser's preferred language. After that it remembers the visitor's choice.
- **Where the text lives:**
  - English is written directly in the HTML.
  - Each element with `data-i18n="key"` has a Chinese version in `UI.zh` inside the script.
  - Articles and resources carry both languages in their data objects (`en` / `zh`).

## Editing content

Everything is at the bottom of `index.html`:

| What | Where |
| --- | --- |
| Articles (topic, date, read time, EN/ZH title + summary) | `ARTICLES` |
| Article full text | `BODIES.en` / `BODIES.zh`, keyed by slug |
| Resources | `RESOURCES` |
| Topics and resource types | `TOPICS`, `TYPES` |
| Hype filter claims | `CLAIMS` |
| Resource card mockups | `SCENES` (pick one per resource with `scene`) |
| Static page text (Chinese) | `UI.zh` |
| Audience numbers | elements with `data-i18n="stat.*"` plus their `UI.zh` entries |

New articles and resources appear in the lists and counts automatically.

## Before launch

- Replace the placeholders: the name "Kai Chen", the bio, audience numbers, articles, resources, Hype filter claims and the `KC` portrait (put an `<img>` inside `.portrait`).
- Connect the newsletter form to your provider (Beehiiv, Buttondown, ConvertKit, …).
- Point resource and social links at real URLs.

## Routes

`#home`, `#articles`, `#resources`, `#about`, `#read-<slug>`

## Deploy

Any static host works: GitHub Pages (Settings → Pages → deploy from `main`), Netlify, Vercel or Cloudflare Pages.
