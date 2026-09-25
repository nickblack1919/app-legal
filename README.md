# App Legal Documents

Static GitHub Pages site hosting Privacy Policies and Terms of Use for my apps.
Plain HTML + one shared CSS file (`assets/style.css`). No JavaScript, cookies, analytics, or external dependencies.

## Structure

```
index.html                  # lists all apps
assets/style.css            # shared styles
<app-slug>/privacy/index.html
<app-slug>/terms/index.html
```

Published URLs:

```
https://nickblack1919.github.io/app-legal/<app-slug>/privacy/
https://nickblack1919.github.io/app-legal/<app-slug>/terms/
```

## Adding a new app

1. Copy an existing app folder, using a lowercase, hyphenated slug:
   ```bash
   cp -R workout-hero my-new-app
   ```
2. In `my-new-app/privacy/index.html` and `my-new-app/terms/index.html`, update:
   - `<title>`
   - the app name (`<p class="app-name">`)
   - the "Last updated" date
   - the document content
   - the contact email (appears in the Contact section and footer)
3. Add the app to `index.html` by copying an `<li>` block in the `app-list`:
   ```html
   <li>
     <h2>My New App</h2>
     <a href="my-new-app/privacy/">Privacy Policy</a>
     <a href="my-new-app/terms/">Terms of Use</a>
   </li>
   ```
4. Commit and push. GitHub Pages redeploys automatically within a minute or two.

Keep links relative (no leading `/`) so the site works under the `/app-legal/` path.

## Preview locally

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.
