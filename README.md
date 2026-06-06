# Param Gogia — Personal Site

A single self-contained `index.html` — no build step, no dependencies, no framework.
Editorial-brutalist design with a live agent-network canvas, custom cursor, and scroll
reveals. Fonts load from Google Fonts CDN. Just host the one file.

## Preview locally
```bash
# from this folder
python3 -m http.server 8000
# open http://localhost:8000
```
Or simply double-click `index.html`.

## Deploy (pick one — all free, ~1 minute)

**GitHub Pages**
```bash
cd website
git init && git add . && git commit -m "personal site"
git branch -M main
git remote add origin https://github.com/paramgogia/paramgogia.github.io.git
git push -u origin main
```
A repo named `paramgogia.github.io` serves at `https://paramgogia.github.io`.
(For any other repo name: Settings → Pages → deploy from `main` / root.)

**Netlify** — drag this `website` folder onto https://app.netlify.com/drop. Done.

**Vercel**
```bash
npm i -g vercel
cd website && vercel        # accept defaults
```

**Cloudflare Pages** — connect the repo or upload the folder; framework preset = "None".

## Custom domain
On any host above, add your domain in the dashboard and point a CNAME/A record at it.
For GitHub Pages, add a `CNAME` file containing your domain to this folder.

## Editing content
Everything is inline in `index.html`:
- Text lives in the `<section>` blocks (hero, index, work, projects, stack, awards, contact).
- Colors/fonts are CSS variables in `:root` at the top of the `<style>` block
  (`--accent` is the molten orange; `--serif` / `--sans` / `--mono` the type).
- The background animation is the `agent-network canvas` script at the bottom.

## Notes
- Honours respects `prefers-reduced-motion` (canvas + animations disable for those users).
- Custom cursor auto-disables on touch devices.
- To add a "Download CV" button, drop your PDF in this folder and link it from the nav/contact.
