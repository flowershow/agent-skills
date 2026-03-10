---
name: site-setup
description: >-
  Set up a Flowershow site's config.json: title, navbar, social links, footer,
  theme, and features. Use when initializing or updating Flowershow site config.
compatibility: Designed for Claude Code (or similar products)
metadata:
  author: flowershow
  version: "1.0"
---

# Flowershow Site Setup

Guide the user through creating or updating `config.json` in their Flowershow content root. Check for an existing config first — read and offer to update it, or create a new one.

Walk the user through each section, asking for preferences. Don't dump all questions at once.

## Config options

### Site basics

- `title`: Site name (browser tab, footer copyright)
- `description`: Meta description for SEO

### Theme

Available: `default`, `lessflowery`, `superstack`, `leaf`, `letterpress`

### Navbar (`nav`)

- `nav.logo`: Emoji (e.g. `"🧶"`) or image path (e.g. `"logo.jpeg"`)
- `nav.title`: Text next to logo
- `nav.links`: Array of `{ "name", "href" }`. Supports one level of dropdowns via `{ "name", "links": [...] }`
- `nav.social`: Array of `{ "label", "href" }`. Labels: `bluesky`, `discord`, `facebook`, `github`, `instagram`, `linkedin`, `mastodon`, `pinterest`, `reddit`, `spotify`, `substack`, `telegram`, `threads`, `tiktok`, `twitter`, `whatsapp`, `youtube`. Omit `label` for a globe icon.

### Footer (`footer`)

Social links from `nav.social` appear in the footer automatically. Optional navigation columns:

```json
"footer": { "navigation": [
  { "title": "Column Title", "links": [{ "name": "Link", "href": "/path" }] }
]}
```

### Additional features

- `showEditLink` (bool): "Edit this page" link to GitHub. Requires public repo.
- `showSidebar` (bool): Left sidebar with site structure
- `analytics`: Google Analytics 4 ID (e.g. `"G-XXXXXXXXXX"`)

## Complete example

```json
{
  "title": "My Site",
  "description": "A short site description.",
  "theme": "lessflowery",
  "showEditLink": true,
  "nav": {
    "logo": "🌸",
    "title": "My Site",
    "links": [
      { "href": "/about", "name": "About" }
    ],
    "social": [
      { "label": "github", "href": "https://github.com/org/repo" },
      { "label": "youtube", "href": "https://youtube.com/@channel" }
    ]
  }
}
```

Only include fields the user has provided values for. Don't add empty arrays or placeholder values.

After writing the config, show the user and ask if they'd like to adjust anything.
