# Los Cabos Mexican Grill — Sealy, TX

A static Astro 4 marketing site for **Los Cabos Mexican Grill** in Sealy, Texas.
Tex-Mex done family-style. Hand-shaken margs. Made-this-morning salsa.

## Stack

- **Astro 4** (static output, TypeScript strict mode)
- **Pure CSS** with design tokens (no Tailwind, no UI lib — keeps it light & fast)
- **Google Fonts**: Bebas Neue (display), Pacifico (script), Inter (body)
- **Netlify**-ready with `netlify.toml` + `_redirects`

## Project structure

```
loscabos-sealy/
├── public/
│   ├── _redirects        # Netlify redirects (404 fallback)
│   ├── favicon.png
│   └── logo.png          # Replace with the LCMG sun-sign mark
├── src/
│   ├── components/
│   │   ├── Bienvenidos.astro
│   │   ├── Features.astro
│   │   ├── Footer.astro
│   │   ├── Header.astro
│   │   ├── Hero.astro
│   │   ├── MenuPreview.astro
│   │   ├── SectionTitle.astro
│   │   └── SideRail.astro
│   ├── layouts/
│   │   └── Base.astro
│   ├── pages/
│   │   ├── 404.astro
│   │   ├── about.astro
│   │   ├── blog.astro
│   │   ├── catering.astro
│   │   ├── contact.astro
│   │   ├── features.astro
│   │   ├── index.astro
│   │   ├── menu.astro
│   │   └── order.astro
│   └── styles/
│       └── global.css    # Design tokens + button system
├── astro.config.mjs
├── netlify.toml
├── package.json
└── tsconfig.json
```

## Local development

```bash
# 1. Install deps
npm install

# 2. Run the dev server (http://localhost:4321)
npm run dev

# 3. Build for production into ./dist
npm run build

# 4. Preview the production build locally
npm run preview
```

## Replacing the logo

`public/logo.png` is currently a placeholder. Drop your real LCMG sun-sign-with-palm-tree
mark in at the same path (`public/logo.png`) and the header will pick it up automatically.

## Deploy to Netlify

### Option 1 — Connect a Git repo (recommended)

1. Push this project to GitHub (or GitLab/Bitbucket).
2. In the Netlify dashboard, click **Add new site → Import an existing project**.
3. Pick the repo. Netlify auto-detects the settings from `netlify.toml`:
   - **Build command**: `npm run build`
   - **Publish directory**: `dist`
4. Click **Deploy**. Done.
5. Add your custom domain under **Site settings → Domain management** when ready.

### Option 2 — Drag-and-drop

```bash
npm run build
# Then drag the dist/ folder onto https://app.netlify.com/drop
```

### Forms

The `/catering` page form is wired for **Netlify Forms** (`data-netlify="true"`).
Once deployed, submissions show up in **Forms** in the Netlify dashboard automatically.

## Design tokens

All brand colors and typography are defined as CSS custom properties in
`src/styles/global.css`:

| Token              | Value      | Use                  |
| ------------------ | ---------- | -------------------- |
| `--orange`         | `#ec6a26`  | Primary brand        |
| `--orange-dark`    | `#c8531a`  | Hover / accent       |
| `--teal`           | `#0f6e7a`  | Secondary brand      |
| `--teal-dark`      | `#0a4f57`  |                      |
| `--red`            | `#c8311e`  | Pills / accents      |
| `--cream`          | `#fff7ec`  | Page background      |
| `--ink`            | `#2a1a10`  | Body text            |
| `--muted`          | `#5a4538`  | Secondary text       |

## Notes

- Trailing slashes are set to `'ignore'` in `astro.config.mjs`.
- The header's primary nav hides under 1100px; social/dot icons hide under 540px.
- The right-side rail (ORD/MEN/CAL) is desktop only.
- All copy is real and voicey — no Lorem ipsum, no AI fillers.

---

Hecho con cariño en Sealy, TX.
