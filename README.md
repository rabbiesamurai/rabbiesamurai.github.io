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
3. Go to **Settings → Pages**. Under "Build and deployment", choose **Deploy from a branch**, branch `master`, folder `/ (root)`, and save. For `<username>.github.io` repositories this is often already set.
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

`app-ads.txt` authorizes these Google AdMob publishers:
- `pub-2434042691497162`: Rocket Flip’s restored app, native and standard banner placements, plus the original games.
- `pub-7510407707948062`: retained because Rocket Flip’s rewarded unit is still configured on this publisher. Remove this line only after all apps/placements using that account have moved.

Rocket Flip production configuration:

| Placement | Identifier |
|---|---|
| App | `ca-app-pub-2434042691497162~9685495237` |
| Native card (current HUD) | `ca-app-pub-2434042691497162/1049719099` |
| Standard banner (reserved, separate format) | `ca-app-pub-2434042691497162/7800558769` |
| Rewarded revival (unchanged) | `ca-app-pub-7510407707948062/9368715328` |

The native card keeps its existing design; the standard banner ID must not be used in a native-ad request. Ad unit IDs belong in app configuration, not as extra lines in `app-ads.txt`.

The owner requested the update on `master`. Existing remote history was on `main`; pushing `master` alone does not change the GitHub Pages publishing branch. Check Pages settings before treating a push as a live deployment.

## Keep the pages true

The privacy policy describes how the games behave as of 2026-10-17:
- no accounts, no analytics and no developer servers; progress is saved on the device only;
- Google AdMob ads, with non-personalized requests and no ATT/IDFA;
- Google UMP consent in the EEA, UK and Switzerland, reachable from Privacy options;
- Apple in-app purchases in some games.

If a game adds analytics, accounts, Game Center leaderboards, cloud saves, personalized ads/ATT or anything that sends data elsewhere, update `privacy.html` (and the App Privacy answers in App Store Connect) before that version ships. This is not legal advice.
