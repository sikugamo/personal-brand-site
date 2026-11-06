# Kai Chen · Personal site

A bilingual (English / 简体中文) personal brand site for an AI and tech content creator. It has three sections: **Resources**, **Articles** and **About**.

It's a single static file (`index.html`) with no build step and no dependencies apart from Google Fonts.

## Design

- **Embedding-map hero.** The opening screen is a live, draggable 3D point cloud. Every article and resource is a glowing point, clustered by topic (Agents, Models, Tools, Tutorials). Hover a point to see its title, click to open it, and use the legend to highlight one cluster.
- **Topic colours run through the whole site.** Each topic has its own hue, used on covers, tags, filters and the map.
- **Generative covers.** Every article and resource gets a gradient cover with a topic icon, seeded from its slug. No image files are needed.
- **Dark-first, with a light theme.** The footer has a Dark / Auto / Light switch.
- **Type:** Archivo, set extra-wide for headlines; Hanken Grotesk for body text; JetBrains Mono for labels and code; Noto Sans SC for Chinese.

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
| Static page text (Chinese) | `UI.zh` |
| Audience numbers | elements with `data-i18n="stat.*"` plus their `UI.zh` entries |

New articles and resources appear on the map, in the lists and in the counts automatically.

## Before launch

- Replace the placeholders: the name "Kai Chen", the bio, audience numbers, articles, resources and the `KC` avatar (put an `<img>` inside `.avatar > div`).
- Connect the newsletter form to your provider (Beehiiv, Buttondown, ConvertKit, …).
- Point resource and social links at real URLs.

## Routes

`#home`, `#articles`, `#resources`, `#about`, `#read-<slug>`

## Deploy

Any static host works: GitHub Pages (Settings → Pages → deploy from `main`), Netlify, Vercel or Cloudflare Pages.
