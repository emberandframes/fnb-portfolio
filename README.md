# Ember & Frames — F&B Photography Portfolio

A static, single-page portfolio for **Ember & Frames**, a food & beverage photography and content studio. No build step, no dependencies — just vanilla HTML, CSS, and JavaScript served as static files.

- **Featured brands:** Conçu, Conçu Hamper, Lunar Café, Rü & Kinru, Tai Tai
- **Stack:** plain HTML, CSS, and JavaScript
- **Hosting:** GitHub Pages (served from the repository root)

## Project structure

```text
.
├── index.html        # The portfolio (entry point served at the site root)
├── 404.html          # Custom not-found page
├── robots.txt        # Allows all crawlers
├── .nojekyll         # Disables Jekyll so files with spaces / leading underscores are served
├── README.md
├── Light/            # Curated images, one folder per brand
│   ├── Concu/
│   ├── Concu Hamper/
│   ├── Lunar Cafe/
│   ├── Ru and Kinru/
│   └── Tai Tai/
├── Logos/            # Brand marks
└── Videos/
    └── Ru and Kinru/
        └── web/      # Web-optimised videos
            └── posters/   # Poster frames for each video
```

> The `.nojekyll` file is required. Several assets use spaces, accented characters, or a leading underscore (for example `_JOY0070.jpg`); without `.nojekyll`, GitHub's Jekyll build would skip them.

## Local preview

Open `index.html` directly in a browser, or serve the folder to mirror how GitHub Pages behaves:

```powershell
python -m http.server 8000
```

Then visit `http://localhost:8000/`.

## Contact behaviour

The contact form does not POST to a server. On submit it builds a pre-filled message and hands off to the visitor's own app:

- **Send via email** opens the mail client with the enquiry pre-filled to `emberandframes@gmail.com`.
- **Send via WhatsApp** opens `wa.me/918447402780` with the same enquiry as text.

Direct contact details are also listed on the page for visitors with JavaScript disabled.

## Editing conventions

- `index.html` is self-contained — its CSS and JavaScript are inlined intentionally so the page deploys as a single artifact.
- Image and video paths are relative and **case-sensitive** on GitHub Pages. Preserve the `Light/`, `Logos/`, and `Videos/` folder names and casing exactly.
- Curated images live in `Light/<Brand>/`; reference new assets from there.
- Videos are referenced from `Videos/Ru and Kinru/web/`, each paired with a poster frame in `Videos/Ru and Kinru/web/posters/`.
- Open Graph preview images are marked in the HTML with the comment `OG_PREVIEW_IMAGE`. Replace those values with absolute `https://` URLs before deploying so WhatsApp, iMessage, and Slack render link previews reliably.

## Deployment

The site deploys to GitHub Pages from the repository root on the `main` branch:

1. In **Settings → Pages**, set **Source** to **Deploy from a branch**.
2. Choose branch `main` and folder `/ (root)`, then **Save**.
3. The published URL appears in the same panel once the build completes.

Pushing to `main` republishes the site automatically. The folder is also host-agnostic — it works on Netlify, Vercel, Azure Static Web Apps, or any server that serves files as-is.

## License

All photographs, logos, and brand assets are © their respective owners and are included for portfolio review only. Do not redistribute without permission.
