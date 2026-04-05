# ⚔ RPG Auction House

A free, self-hosted auction house for your tabletop RPG campaign. Players browse gear by rarity, tags, price, and search. You manage everything through a GM panel — no backend, no database, no monthly fees.

---

## Quick Setup (GitHub Pages)

### 1. Create a GitHub repository

Go to [github.com](https://github.com) → **New repository** → give it a name (e.g. `my-auction-house`) → **Create repository**.

### 2. Upload these files

Upload all files from this folder into the root of your repository:
- `index.html` — the player-facing auction house
- `admin.html` — your GM item management panel
- `items.json` — your item data (edit this to change items)
- `images/` — folder for your item images

You can drag and drop files directly into the GitHub web interface.

### 3. Enable GitHub Pages

In your repository → **Settings** → **Pages** → under "Source", select **Deploy from a branch** → choose `main` (or `master`) → `/ (root)` → **Save**.

Your site will be live at:
```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/
```

(It may take 1–2 minutes the first time.)

---

## Managing Items

### Option A — Use the GM Panel (Recommended)

Open `admin.html` on your live GitHub Pages site, e.g.:
```
https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/admin.html
```

1. Fill in the form to add items
2. Click **Copy JSON** or **Download items.json**
3. Go to your GitHub repo → open `items.json` → click the pencil (edit) icon → paste the new JSON → **Commit changes**

### Option B — Edit items.json directly

Edit `items.json` in the GitHub web editor. Each item follows this format:

```json
{
  "id": 1,
  "name": "Blade of Eternal Frost",
  "description": "A longsword forged from glacial iron...",
  "image": "images/frost-blade.png",
  "rarity": "legendary",
  "price": 5000,
  "currency": "gp",
  "seller": "Merchant Aldric",
  "tags": ["weapon", "sword", "ice", "magic", "one-handed"],
  "stats": "+2d6 cold damage · +1 to attack rolls"
}
```

**Rarity values:** `common`, `uncommon`, `rare`, `epic`, `legendary`

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

## Item Fields Reference

| Field | Required | Description |
|-------|----------|-------------|
| `id` | Yes | Unique number for each item |
| `name` | Yes | Item name shown on the card |
| `rarity` | Yes | `common` / `uncommon` / `rare` / `epic` / `legendary` |
| `price` | Yes | Numeric price |
| `currency` | No | Defaults to `gp` |
| `seller` | No | Merchant or seller name |
| `image` | No | Path or URL to item image |
| `tags` | No | Array of tag strings for filtering |
| `description` | No | Flavour text shown in detail view |
| `stats` | No | Mechanical properties / bonuses |

---

## Tips

- **Tags are flexible** — use whatever makes sense for your game. Common examples: `weapon`, `armor`, `magic`, `consumable`, `one-handed`, `two-handed`, `fire`, `ice`, `cursed`, `rare-find`
- **Keep IDs unique** — the GM panel handles this automatically; if editing manually, just use sequential numbers
- **Images display best** at a roughly 4:3 ratio (e.g. 400×300px)
- **The admin panel** works best when loaded from the live GitHub Pages URL (not as a local file), because `Load from items.json` uses `fetch()` which requires a server
