# BVL Estimate Tracker

Password-protected estimate pipeline tool for the Compass ops team.

## Access

**URL:** `https://[your-github-username].github.io/bvl-ops/estimates.html`

Replace `[your-github-username]` with your GitHub username once deployed. Share this link with team members who need access.

**Password:** Set in `estimates.html` at the top of the `<script>` block — look for `const PASSWORD = '...'`. Change it there and redeploy to rotate.

---

## Deploying / Updating

### First-time setup

1. Create a new repository on GitHub (github.com → New repository)
   - Name it `bvl-ops`
   - Set it to **Private** (recommended) or Public
   - Do **not** initialize with a README

2. Push this repo:
   ```bash
   git remote add origin https://github.com/[your-username]/bvl-ops.git
   git push -u origin main
   ```

3. Enable GitHub Pages:
   - Go to the repo → **Settings** → **Pages**
   - Source: **Deploy from a branch**
   - Branch: `main` / `/ (root)`
   - Click **Save**

4. After ~60 seconds your URL will be live:
   `https://[your-username].github.io/bvl-ops/estimates.html`

### Pushing updates

```bash
git add estimates.html
git commit -m "Update estimate tracker"
git push
```

GitHub Pages redeploys automatically within ~30 seconds.

---

## What's in this repo

| File | Purpose |
|------|---------|
| `estimates.html` | Standalone estimate tracker (this tool) |
| `index.html` | Main Compass ops dashboard (separate tool, not on Pages) |
| `api/` | Vercel serverless functions (Claude API proxy — not used by estimates.html) |

`estimates.html` is completely self-contained — no server required, no API calls, works from any static host.

---

## Data & privacy

All estimate data is stored in the browser's `localStorage` under the key `bvl-est-v1`. Data stays in the browser — nothing is sent to any server. Each team member's browser holds their own copy; there is no shared database.

To share or back up estimates, use **↓ Export** in the app to download a CSV.
