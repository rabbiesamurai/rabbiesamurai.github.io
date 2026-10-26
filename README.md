# rabbiesamurai.github.io

Developer site for Junning Zeng's iPhone games: support page, privacy policy and AdMob `app-ads.txt`.

## Publish with GitHub Pages

1. On GitHub, create a new repository:
   - Owner: `rabbiesamurai`
   - Repository name: **`rabbiesamurai.github.io`** (exactly this, so the site is served from the domain root, where `app-ads.txt` must live)
   - Visibility: **Public**
   - README / .gitignore / license: leave off (this folder already has a README)
2. On the new repository page, choose **uploading an existing file**. Drag in every file from this folder: `index.html`, `privacy.html`, `support.html`, `style.css`, `app-ads.txt`, `.nojekyll`, `README.md`. Then commit to the publishing branch (`master` for the current owner-requested update).
   - Finder hides `.nojekyll`. Press Cmd+Shift+. to show it. It is optional; the site works without it.
3. The existing GitHub Pages deployment reads branch `main`, folder `/ (root)`. Owner-requested changes are maintained on `master`; after checking that `origin/main` is an ancestor, fast-forward the same reviewed commit to `main` to publish it. A push to `master` alone does not deploy this site. Do not force-push or overwrite divergent work.
4. After a minute or two, check:
   - https://rabbiesamurai.github.io/
   - https://rabbiesamurai.github.io/privacy.html
   - https://rabbiesamurai.github.io/support.html
   - https://rabbiesamurai.github.io/app-ads.txt (must list the authorized Google publisher lines from `app-ads.txt`)

## Where these URLs go

| Place | Value |
|---|---|
| App Store Connect → App Information → Privacy Policy URL (each game) | `https://rabbiesamurai.github.io/privacy.html` |
| App Store Connect → version → Support URL | `https://rabbiesamurai.github.io/support.html` |
| App Store Connect → version → Marketing URL (optional), and the developer website AdMob reads | `https://rabbiesamurai.github.io/` |
| AdMob → Apps → (each app) → app-ads.txt | AdMob looks for `https://rabbiesamurai.github.io/app-ads.txt`, based on the developer website in the App Store listing. Verification happens after the app is live and linked to its App Store listing in AdMob. |

`app-ads.txt` authorizes Google AdMob publisher `pub-2434042691497162` for Rocket Flip’s restored native, standard banner and rewarded placements, plus the original games. The temporary publisher entry has been removed.

Rocket Flip production configuration:

| Placement | Identifier |
|---|---|
| App | `ca-app-pub-2434042691497162~9685495237` |
| Native card (current HUD) | `ca-app-pub-2434042691497162/1049719099` |
| Standard banner (reserved, separate format) | `ca-app-pub-2434042691497162/7800558769` |
| Rewarded revival | `ca-app-pub-2434042691497162/4371771023` |

The native card keeps its existing design; the standard banner ID must not be used in a native-ad request. Ad unit IDs belong in app configuration, not as extra lines in `app-ads.txt`.

On 2026-10-26, commit `ad8e810` was pushed to both `master` and the publishing branch `main` by fast-forward. Verify the Pages workflow and the public pages before treating a later push as deployed.

## Keep the pages true

The privacy policy describes the games as of 2026-10-26. Check each game's section: Jet Drift has optional Game Center rankings and Apple cloud saves, while other games may differ. Jet Drift has no separate developer account or backend; local progress remains available when Apple services are unavailable. Google advertising SDK data collection is disclosed, and the existing HOSHI Arcade ATT policy is retained. Do not describe every game as local-only or make a blanket claim that no analytics or personal data is collected.

If a game adds analytics, accounts, Game Center leaderboards, cloud saves, personalized ads/ATT or anything that sends data elsewhere, update `privacy.html` (and the App Privacy answers in App Store Connect) before that version ships. This is not legal advice.
