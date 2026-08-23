# assets.web.aviviscakes

Remote content for [web.aviviscakes](https://github.com/itzikbuktshin/web.aviviscakes). The site
bundles its own copy of everything here and fetches these files at runtime only when
`VITE_REMOTE_ENABLED=true`; a fetch failure falls back to the bundled copy.

## Layout

| Path | Served as |
| --- | --- |
| `config/assets.config.json` | `VITE_REMOTE_CONFIG_URL` — image slot catalog |
| `config/assets.schema.json` | `VITE_REMOTE_SCHEMA_URL` — schema the config is validated against |
| `locale/{en,he}.json` | `VITE_REMOTE_LOCALES_BASE` — UI strings, deep-merged onto the bundled locale |
| `fonts/` | static font files (see below) |

## Fonts

`fonts/KedmiTallHebrew-Regular.{woff2,ttf}` — **Kedmi Tall Hebrew**, the Hebrew display face used
by the site. A tall, condensed, heavy face (`usWeightClass` 800, 1000 upem). Prefer the `woff2`
(4.8 KB); the `ttf` (10.4 KB) is the source and a fallback for very old browsers.

Coverage is Hebrew-only: the 27 Hebrew letters (including final forms), maqaf, geresh/gershayim,
digits and common punctuation — **no Latin letters and no niqqud**. Always declare it ahead of a
Latin-capable fallback so mixed text still renders:

```css
font-family: 'Kedmi Tall Hebrew', 'Heebo', Arial, sans-serif;
```

Because the repo is public, the files can be served straight off jsDelivr:

```
https://cdn.jsdelivr.net/gh/itzikbuktshin/assets.web.aviviscakes@main/fonts/KedmiTallHebrew-Regular.woff2
```
