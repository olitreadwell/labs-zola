# NYCPlanning/labs-zola context
> refreshed 2026-10-11 | upstream default: develop @ a31db6e6

## Identity & policies
- upstream: NYCPlanning/labs-zola, default branch `develop`, primary language JavaScript (Ember.js 4.12, Octane edition)
- English-first: yes (issues, docs, UI all English)
- CLA/DCO: none (CONTRIBUTING: public domain CC0 waiver; no CLA bot, no DCO sign-off)
- AI-assisted PR policy: unstated
- signed commits required: no (vetted-repos policy signed_commits_required: false)
- PR template: repo-root `PULL_REQUEST_TEMPLATE.md` (fill verbatim)
- external tracker: github

## Conventions (verified from merged PRs)
- branch naming: `type/issue-number-description` (e.g. `bug/1317-msx-tag-does-not-render-in-details-view`, `issue/1243-add-zoning-for-accessibility-layer`, `task/1301-replace-subway-layer-with-transit-layer`, `1288/add-special-atlantic-av-mixed-use-district`, `1274-Update-links-on-Zola`)
- CI: `ci.yml` runs `yarn lint` (eslint + stylelint + ember-template-lint) and `yarn test` (ember test) on node 18; `main.yml` runs build+test on macos
- test command: `yarn test` (ember test, qunit); lint: `yarn lint`
- maintainers active: dhochbaum-dcp, horatiorosa, TangoYankee, TylerMatteo, pratishta (all core team; no external community merges in last 60d)

## Maintainer picture
- active maintainers: dhochbaum-dcp (most active, merges ~weekly), horatiorosa, TangoYankee, TylerMatteo, pratishta
- recent work: carto cache prod split, transit/ZFA layers, docker/intranet deploy docs

## Issue-area health
- 118 open issues; most recent activity on Ember upgrade (#1304), ZFA layer renames (#1326), carto caching (#1319)
- Bug #1315 (owner info on Citynet) is a network/domain (reCAPTCHA site-key) issue, not code-fixable
- #1297 Fresh Zones outdated link — reported dead link, needs live verification

## Gap ledger (dedupe — READ FIRST, never re-pick)
- #1297 Fresh Zones outdated link — addressed 2026-08-26 in fork PR olitreadwell/labs-zola#2 (base develop). Verified live: old special-areas-rules page is contentNotFound on the DCP content API; replacement rules-for-special-areas#fresh confirmed. Bundled with 2 more verified broken external links in layer-record-views (Commercial Districts C1-C2 anchor x3, E-Designation OER URL) per trivial_fix_rules (min 3). Do not re-pick.
- 2026-10-11 trivial-cleanup pass — attempted, fork PR olitreadwell/labs-zola#4 (`fix/doc-typos-and-stale-test-command`, base develop, 4 files +6/-6): (a) zoning-district.js r5b description said "R4B districts also permit detached and semi-detached buildings" -> "R5B districts" (copy-paste from the r4b entry above); (b) CONTRIBUTING.md `[LICENSE](LICENSE.md)` -> `[LICENSE](LICENSE)` (LICENSE.md does not exist; the root file is LICENSE); (c) README.md Testing section `ember test -server` -> `ember test --server` (ember-cli only defines `--server`/`-s`; `-server` is not a valid flag); (d) README.md "Zola Search API" -> "ZoLa Search API" (x2, the app is branded ZoLa everywhere else); (e) tests/acceptance/navigating-to-qpd-url-breaks-test.js test title "doesnt" -> "doesn't". Do not re-pick any of these. Considered and rejected for this pass as out of the user-facing/fix scope: config/environment.js `['Special Enhanced Commercial District', ['EC', ' brooklyn']]` leading space in a currently-unused crosswalk value; app/router.js comment "hyperlinks to to the new route" duplicated word; data.cityofnewyork.us 404s only in mirage fixtures; s-media.nyc.gov map PDF 404 only in a test string; herokuapp/carto/acris endpoints in code, not docs.

## Mined gaps (discovered, not yet attempted)
- Broken external links in layer-record-views (verified live, fixed in PR #2): Commercial Districts links used a dead #C1-C2-overlays anchor (page has id="C1-C2"); E-Designation link pointed at a "page has moved" stub (new URL https://www1.nyc.gov/site/oer/remediation/e-designation.page). Both confirmed via DCP content API + live requests.
- 2026-09-30 trivial-cleanup pass — attempted, fork PR olitreadwell/labs-zola#3 (`fix/user-facing-typos-and-links`, base develop, 5 files +11/-11): (a) data.hbs OpenStreetMap copyright link was a relative URL (`www.openstreetmap.org/copyright`) -> https, (b) features.hbs "search input provide" -> "provides", (c) zoning-district.js R9A/R9X/R10A "that mimics" -> "that mimic" (x3), (d) tax-lot.js "Loft Buildinghs" -> "Loft Buildings" (x5, L1/L2/L3/L8/L9), (e) CONTRIBUTING.md 18F Code of Conduct link 404s -> repointed at a verified web.archive.org copy. Do not re-pick any of these. Exhaustive re-search for this pass found no further user-facing typos (codespell clean outside mirage fixtures); rejected as non-typos: "ORE" building-class text, "Over Eight Stores", "Ceiling Railroad", English-variant spellings.
