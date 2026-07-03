# Setup Instructions

Your README now references five things that go beyond plain markdown badges. Two work
immediately once you push. Three need a short one-time setup on your end because they
pull from your own private account data. Do these in order.

---

## ✅ Works immediately (no setup needed)

- Capsule-render banner, typing SVG, shields.io badges, skillicons — all public,
  no config required.
- **GitHub Stats / Streak / Top Languages / Trophies / Activity Graph** — these read your
  public GitHub activity automatically. Just make sure `RaviKurane17` matches your exact
  GitHub username everywhere in the file.

---

## 🐍 1. Contribution Snake

**File added:** `.github/workflows/snake.yml`

This repo must be a **special "profile" repo** — a repository named exactly the same as
your username (`RaviKurane17/RaviKurane17`) — for the README to show on your profile page
at all. If it already is, you don't need to do anything else:

1. Push this repo to GitHub with the workflow file in place.
2. Go to the **Actions** tab → find "Generate Snake" → click **Run workflow** once manually
   (it also runs automatically daily).
3. It will create a new branch called `output` containing the SVG. The README already
   points at that branch, so once the workflow finishes, the snake appears.

If Actions are disabled on your account/repo, enable them under
**Settings → Actions → General → Allow all actions**.

---

## 📈 2. Metrics Dashboard

**File added:** `.github/workflows/metrics.yml`

This one needs a **Personal Access Token (PAT)**, because the default token GitHub gives
Actions can't read enough of your account data for the dashboard plugins (achievements,
habits, stars, etc.).

1. Go to **github.com → Settings → Developer settings → Personal access tokens →
   Tokens (classic) → Generate new token**.
2. Scopes needed: `repo`, `read:user`, `read:org` (optional, only if you want org stats).
3. Copy the token.
4. In your profile repo, go to **Settings → Secrets and variables → Actions → New
   repository secret**.
   - Name: `METRICS_TOKEN`
   - Value: (paste the token)
5. Run the "Metrics" workflow once manually from the Actions tab.
6. It commits a file called `github-metrics.svg` to your repo root — the README already
   points at it.

---

## 🎧 3. Spotify "Now Playing" Widget

This one is the most involved because it needs your Spotify account connected through a
small hosted app (not something that can run purely inside a GitHub Action).

1. Go to **https://spotify-github-profile.vercel.app**
2. Click **Login with Spotify** and authorize it.
3. It gives you a **UID** — copy it.
4. In `README.md`, find this line:
   ```
   uid=YOUR_SPOTIFY_UID
   ```
   Replace `YOUR_SPOTIFY_UID` with the UID you copied.
5. Save, commit, push. The widget updates automatically whenever you're playing something
   on Spotify (or shows your last played track when idle).

---

## 🏅 4. Holopin Badges

1. Go to **https://holopin.io**
2. Sign in with your GitHub account and claim your profile.
3. Once you've collected at least one badge, your badge board becomes live automatically
   at `https://holopin.me/RaviKurane17` — which is already embedded in the README, so
   nothing else to change.

---

## ⏱️ 5. WakaTime Weekly Activity

This shows real coding-time stats (languages, editors, hours), not GitHub activity — it
needs a WakaTime account with a code editor plugin installed.

1. Create a free account at **https://wakatime.com**
2. Install the WakaTime plugin for your editor (VS Code, IntelliJ, etc.) and code normally
   for a few days — it tracks time in the background.
3. In WakaTime, go to **Settings → General** and make sure **"Display coding activity
   publicly"** is turned on.
4. In `README.md`, replace `username=RaviKurane17` in the WakaTime badge URL with your
   actual **WakaTime** username (this may differ from your GitHub username).

---

## Final checklist before pushing

- [ ] Repo is named exactly `RaviKurane17` (same as your GitHub username)
- [ ] Actions enabled in repo settings
- [ ] `METRICS_TOKEN` secret added
- [ ] Snake workflow run once manually
- [ ] Metrics workflow run once manually
- [ ] Spotify UID swapped in
- [ ] Holopin profile claimed
- [ ] WakaTime username swapped in (or remove that section if you don't want it)
