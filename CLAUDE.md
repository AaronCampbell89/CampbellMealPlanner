# Campbell Meal Planner

Single-file web app (`index.html`), hosted on GitHub Pages from `main`. No build step.

- Recipes, planner, favourites and shopping list all live in `index.html`.
- Shared sync uses Firebase Firestore (`households/{sha256 of passcode}`); see the "SHARED SYNC" module script. Firestore rules only allow the fields `plan`, `favs_aaron`, `favs_katie`, `updatedAt`, so update the rules if you add fields. The template week lives inside `plan` as keys `t0`–`t6` (weeks are `w{week}d{day}`), so it needs no rule change.
- **Bump `<meta name="app-version">` in every commit that changes `index.html`** (format `YYYY-MM-DD.N`). Home-screen installs on iPhone compare this value to reload themselves; without a bump they keep showing the old version.

## Adding recipes

Before adding any recipe to `RECIPES` (and before committing/pushing), **ask the user to confirm these for each recipe**, even if you could guess them:

1. **Source**: where it's from. Offer the existing values as options (e.g. GF Cookbook, Online, Home, Meera Sodha, Ottolenghi, Gordon Ramsay, What Mummy Makes, The Ultimate Weaning and Toddler Cookbook, MOB Cookbook) or a new one.
2. **Kid friendly?** (`isKid`)
3. **Good for batch cooking?** (`isBatch`)

Only once all three are answered: add the recipe(s) in the existing format (next free `id`, `cat`, `stamp`, `serves`, `time`, `source`, `note`, `ingredients`, `method`), bump `app-version`, then commit and push to `main`.
