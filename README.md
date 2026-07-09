 Menu & Shopping Planner

A single-file HTML/CSS/JS Progressive Web App for planning a repeating monthly meal rotation and generating category-grouped, store-filterable shopping lists. Built to run entirely offline on a phone, no backend, no build step.

## Features

- **4-week rotating menu calendar** — Monday–Sunday structure (Breakfast-for-supper / Beef / Fish or Chicken / Mince / Boerie or Hotdogs / Burgers or Pizza / Braai, Roast or Potjie) that repeats indefinitely from a fixed anchor date, so the app always knows which week and day you're on.
- **Seasonal side suggestions** — Auto-switches Summer (Oct–Mar) / Winter (Apr–Sep) or can be set manually. Sunday cards surface a seasonal suggestion (braai vs. potjie/roast + matching sides) without overwriting your planned meal.
- **Editable meals** — Tap any day to change the meal name, emoji, or sides.
- **Shopping list generator** — Build a list from this week, the whole month, or any combination of weeks. Ingredients are pulled automatically from the selected days' meals.
- **Monthly staples basket** — A recurring list of veg, dairy, pantry, and fruit/snack basics, toggle on/off per list. Winter mode adds extra root veg (potatoes, cabbage, soup vegetables).
- **Category + store filtering** — Items are grouped by Fresh Veg / Dairy / Pantry / Meat & Fish / Fruit & Snacks / Other, with a store filter (Spar, Checkers, Pick n Pay, Food Lovers Market, Golden Harvest, BraaiBox, Other) so you can shop one store at a time.
- **Manual price/specials notes** — Optional free-text note per item (e.g. "R89.99 on special at Checkers") and a "usual store" tag. No automated price scraping — stores don't expose that data reliably, so this stays manual by design.
- **Persistent checklist** — Checked items, custom items, and notes are saved per list so a half-finished shop survives closing the app.
- **Add/remove custom items** — Anything not on the auto-generated list can be added manually.

## Tech

- Vanilla HTML/CSS/JS, single file, no dependencies except Google Fonts (Fraunces, Inter, JetBrains Mono) loaded via CDN.
- All data persists in `localStorage` on-device. Nothing is sent anywhere.
- No build step, no package.json, no framework.

## Running it

### Option A — GitHub Pages
1. Push `menu-shopping-planner.html` to a repo (rename to `index.html` if you want it at the repo root URL).
2. Enable GitHub Pages on the repo (Settings → Pages → deploy from branch).
3. Open the published URL on your phone and "Add to Home Screen" for a PWA-style icon.

### Option B — Direct file
1. Download `menu-shopping-planner.html` straight to your phone.
2. Open it in Chrome — works fully offline, same as The Ledger.

## Data & privacy

Everything (menu edits, checked items, custom items, store/price notes) is stored in browser `localStorage`. Nothing leaves the device, there's no login, and there's no server component. Clearing browser data/site data for the page will reset it.

## Customizing the base plan

All source data lives near the top of the `<script>` block:

- `ANCHOR` — the Monday that Week 1 / Day 1 starts on. Change this if the cycle needs to shift.
- `DEFAULT_WEEKS` — the 4-week menu (meal, emoji, sides, ingredients per day).
- `STAPLES_BASE` / `WINTER_EXTRAS` — the recurring monthly basket.
- `CATS` / `STORES` — the category and store lists shown in filters and the item editor.

Edits made in the app itself (day meals, item stores/notes, custom items) are layered on top via `localStorage` and won't be lost on reload, but editing the source data above changes the defaults for a fresh install.

## Backlog / not built yet

- Automated specials/pricing per store (no reliable public API across Spar/Checkers/PnP/Food Lovers/Golden Harvest — kept manual on purpose).
- Multi-user / cloud sync.
- Recipe detail view / cooking instructions per meal.

## Related apps

Same single-file PWA + localStorage pattern as **GSC2** (coaching app) and **The Ledger** (lending tracker).
