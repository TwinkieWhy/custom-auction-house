# ⚔ Auction House

Thank to Claude for vibecoding the majority of this lmao.

---

## Adding Item Images

1. Create an `images/` folder in your repository (you can upload a placeholder file to create it)
2. Upload your item images there (`.png`, `.jpg`, `.webp` all work)
3. In `items.json`, set `"image": "images/your-filename.png"`

**Tip:** You can also use external image URLs (e.g. from Imgur or a CDN) if you don't want to store images in the repo:
```json
"image": "https://i.imgur.com/XXXXXXX.png"
```

---

## Tips

- **Keep IDs unique** — the GM panel handles this automatically; if editing manually, just use sequential numbers
- **The admin panel** works best when loaded from the live GitHub Pages URL (not as a local file), because `Load from items.json` uses `fetch()` which requires a server
