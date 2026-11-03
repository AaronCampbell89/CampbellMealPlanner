# Campbell Meal Planner

Single-file web app (`index.html`), hosted on GitHub Pages from `main`. No build step.

- Recipes, planner, favourites and shopping list all live in `index.html`.
- Shared sync uses Firebase Firestore (`households/{sha256 of passcode}`); see the "SHARED SYNC" module script. Firestore rules only allow the fields `plan`, `favs_aaron`, `favs_katie`, `updatedAt`, so update the rules if you add fields.
- **Bump `<meta name="app-version">` in every commit that changes `index.html`** (format `YYYY-MM-DD.N`). Home-screen installs on iPhone compare this value to reload themselves; without a bump they keep showing the old version.
