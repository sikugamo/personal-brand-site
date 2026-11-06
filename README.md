# Theo Lindqvist · Personal site

A bilingual (English / 简体中文) personal brand website with three sections: **Resources**, **Articles**, and **About**.

It's a single static file (`index.html`) with no build step and no dependencies apart from Google Fonts.

## Design

- **Blue ink on porcelain** in light mode, and a **cyanotype print** in dark mode. Visitors can switch between Ink, Auto and Cyanotype in the footer.
- **The hero sentence is the navigation.** Its three highlighted phrases link to About, Articles and Resources.
- **Annotated-manuscript layout.** A narrow margin column holds labels and notes, next to a wide main column.
- **Type:** Bricolage Grotesque (display), Newsreader (reading), IBM Plex Mono (labels), with Noto Sans SC and Noto Serif SC for Chinese.

## Languages

- **Switching:** use the `EN / 中文` control in the masthead.
- **First visit:** the site follows the browser's preferred language. After that it remembers the visitor's choice.
- **Where the text lives:**
  - English is written directly in the HTML.
  - Each element with `data-i18n="key"` has a Chinese version in `UI.zh` inside the script.
  - Articles and resources carry both languages in their data objects (`en` / `zh`).

## Editing content

All content is at the bottom of `index.html`:

| What | Where |
| --- | --- |
| Article list | `ARTICLES` |
| Article full text | `BODIES.en` / `BODIES.zh`, keyed by slug |
| Resources | `RESOURCES` |
| Static page text (Chinese) | `UI.zh` |

To use your own portrait, put an `<img>` inside `.portrait`. It gets a blue duotone automatically.

## Routes

`#home`, `#articles`, `#resources`, `#about`, `#read-<slug>`

## Before launch

- Replace the placeholder name, bio, articles and resources.
- Connect the newsletter form to a provider (Buttondown, ConvertKit, …).
- Point the resource and "Elsewhere" links at real URLs.

## Deploy

Any static host works: GitHub Pages, Netlify, Vercel, Cloudflare Pages.
