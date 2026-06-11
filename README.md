# WI-03 Voting Procedures Dashboard

Built from `voting-dashboards-source` repo, district config `client/src/configs/wi-03.ts`.

## District profile
- **State**: Wisconsin
- **Counties**: La Crosse, Eau Claire, Crawford, Vernon, Monroe, Buffalo, Pepin, Pierce, Trempealeau, Jackson, Juneau, Adams, Richland
- **2026 race**: Derrick Van Orden (R, incumbent, unopposed primary) vs Rebecca Cooke (D, DCCC Red-to-Blue, likely Aug 11 primary winner)
- **Next key date**: Aug 11, 2026 (primary)
- **Cook PVI / rating**: Toss Up / Lean R
- **Election admin**: Wisconsin Elections Commission

## Data inventory
- 13 sources verified (state SOS + county election offices + nonpartisan journalism)
- 12 rules — all `needsReview: true, confidence: "unconfirmed"` (verify before publish)
- 16 election events on timeline
- 9 voter resources
- 6 news cards (last 90 days)
- 3 updates panel entries (initial-build inventory)
- 1 conflict logged: Drop box legality — banned 2022 (Teigen v. WEC), reinstated 2024 (Priorities USA v. WEC); municipal availability still varies across the 13 counties

## Deploy to GitHub Pages

```bash
# In Apprentice101/wi03-dashboard repo:
git add .
git commit -m "Deploy WI-03 dashboard"
git push -u origin main
```

Enable GitHub Pages from main branch root in repo settings.

## Files
- `index.html` — entry point
- `snapshot.json` — district data (data layer)
- `assets/` — bundled JS/CSS

## QA status (2026-06-11)
- All rules and events marked `confidence: "unconfirmed"` — strict review required before public ship per user policy
- Zero console errors on smoke test
- Review Queue tile, district map, tab highlighting, Updates/Conflicts panels all rendering correctly (post-v2 fixes)

## Built from
- Source repo: https://github.com/Apprentice101/voting-dashboards-source
- Config file: `client/src/configs/wi-03.ts`
- Build command: `VITE_DISTRICT_ID=WI-03 npm run build:static`

## Title fix (2026-06-11 patch)
- Browser tab `<title>` now reads "WI-03 Voting Procedures Dashboard" (was generic/empty)
- `client/index.html` and `script/build-static.ts` updated so all future builds get the district title automatically
