# 🧈 Little Butter Icons — Zed Icon Theme Extension

A candy-colored file icon theme with family-based color coding, designed as the companion to the [Little Butter theme](https://github.com/ikun-Lg/little-butter-theme).

This repository is the Zed port of the icon set from the [lggbond-theme for VS Code](https://github.com/ikun-Lg/LG-Theme-for-vscode).

## ✨ Contents

- **139 file extensions** mapped (js/ts/py/go/rs/java/c/...)
- **61 special filenames** matched exactly (README.md / Dockerfile / Makefile / .gitignore / vite.config.ts / ...)
- **71 SVG icons**, grouped by candy family colors:

| Family | Color | Covers |
| --- | --- | --- |
| 🧈 web | Warm gold | html / vue / svelte / astro / jsx / tsx / css / scss / graphql |
| 🍓 doc | Pink brown | md / txt / pdf / doc |
| 🟣 style | Purple | sass / less / config files |
| 🟢 systems | Green | python / go / rust / c / swift |
| 🔵 data | Blue | json / xml / sql / csv / yaml / toml |

## 🚀 Install

This is an icon theme designed to be used together with the `little-butter-theme` color theme. Install both:

1. Install **Little Butter Icons** from the Zed extensions page, or use **zed: install dev extension** and select this folder.
2. Install [little-butter-theme](https://github.com/ikun-Lg/little-butter-theme) the same way.

Then enable the icon theme in your `settings.json`:

```jsonc
{
  "theme": "Little Butter",                 // or "Little Butter Flat"
  "file_icons": "Little Butter Icons"
}
```

## 📁 Structure

```
little-butter-icons/
├── extension.toml      # extension manifest (id=little-butter-icons)
├── icon_theme.json     # Zed icon theme manifest (schema v0.3.0)
├── icons/              # 71 SVG icons
├── README.md
└── LICENSE             # MIT
```

## 🛠️ Development

Icon theme changes hot-reload automatically in Zed. Validate the manifest:

```bash
python3 -m json.tool icon_theme.json
```

## 📄 License

MIT © lggbond
