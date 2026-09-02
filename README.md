# Setup

1. **Create a repo on GitHub** named `<yourusername>.github.io` (this exact naming makes GitHub host it at the root of that URL automatically, no extra config needed).
2. **Push these files** to the repo (root of the repo, not a subfolder):
   ```
   git init
   git add .
   git commit -m "initial site"
   git branch -M main
   git remote add origin https://github.com/<yourusername>/<yourusername>.github.io.git
   git push -u origin main
   ```
3. **Turn on Pages**: repo → Settings → Pages → Source → Deploy from branch → `main` / `root`. Give it 1-2 minutes to build.
4. Site will be live at `https://<yourusername>.github.io`.

## Editing day to day

There are two kinds of posts, both live in `_posts/`, distinguished only by their `categories:`:

**Quarterly earnings reports** (one per ticker, only when that company actually reports)
- File name: `YYYY-MM-DD-ticker-quarter.md` (Jekyll requires date-prefixed names — it's how it sorts posts)
- Front matter: `categories: [cmg]` (or `qsr` / `mcd` / `yum`) — this is what makes it show up grouped under that ticker on the **Coverage** tab
- Use the lean format already in the CMG template: same-store sales, unit growth, margin trend, one quote, one paragraph take

**Weekly industry notes** (whole fast food industry, any company, length varies)
- File name: `YYYY-MM-DD-weekly-update.md`
- Front matter: `categories: [weekly]` — this is what makes it show up on the **Weekly Notes** tab instead of Coverage
- No fixed structure — some weeks 2 bullets, some weeks more

Both post types also show up together, chronologically, on the homepage. Edit `.md` files directly on github.com (pencil icon) if you don't want to set up Jekyll locally — GitHub Pages rebuilds automatically on every push.

## Adding your resume

Drop a `resume.pdf` into an `/assets/` folder — it'll match the download link at the bottom of `about.md`.

## Live stock prices on Coverage

`coverage.md` has a TradingView widget embedded at the top showing live price/change for all 4 tickers — free, no API key, no backend needed, updates in the visitor's browser. To swap tickers or add a 5th, edit the `symbols` list in that script block. Note: it's set to `colorTheme: "light"` — TradingView doesn't auto-match dark mode, so if your site theme switches to dark this widget will stay light unless you hardcode a `"dark"` variant or add JS to detect `prefers-color-scheme`.

## Optional: build locally to preview before pushing

```
bundle install
bundle exec jekyll serve
```
Then visit `http://localhost:4000`.

## Custom domain later

Settings → Pages → Custom domain, once you have one — not needed to get started.
