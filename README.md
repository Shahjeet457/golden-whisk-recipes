# The Golden Whisk — Food Recipe Website

A self-contained static recipe site. No build step and no npm install needed.

## How to open

Option A (recommended): run a tiny local server from this folder:

```bash
cd /workspace/recipe-website
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser.

Option B: open `index.html` directly in a browser. Everything works except that some browsers restrict `localStorage` on `file://` pages, so favourites may not persist that way.

## Features

- Hero search that filters live by recipe title, description, or ingredient
- Filter chips: All, Breakfast, Mains, Desserts, Vegetarian, and Quick (under 30 min) — combinable with search
- 12 complete recipes in `app.js` with time, difficulty, rating, servings, quantities, and numbered steps
- Click any card for the full recipe; use the servings −/+ scaler and ingredient amounts recalculate automatically
- Heart a recipe to save it as a favourite (persisted in `localStorage`), then use “Favourites only” to view just those
- Esc key / backdrop click / × closes the recipe modal; responsive layout for phone and desktop
- Recipe photos load from Unsplash with a colourful gradient + initials fallback if an image ever fails

## How to add a recipe

Open `app.js` and add another object to the `RECIPES` array following the existing pattern:

- `categories`: any of `"breakfast"`, `"mains"`, `"desserts"`, `"vegetarian"`, `"quick"` (Quick also requires `time` under 30 — it is derived, so keep `time` accurate)
- `ingredients`: `{qty: 200, unit: "g", item: "flour"}` — use `qty: null` for “to taste” items; numeric quantities are what the servings scaler multiplies
- `steps`: an array of strings, shown as a numbered method

## Files

- `index.html` — page structure
- `styles.css` — all styling
- `app.js` — recipe data and all interactivity
- `preview.png` — screenshot of the homepage (if generated)
