# NYCPlanning/labs-zola context
> refreshed 2026-08-26 | upstream default: develop @ a31db6e6

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
- (none yet)

## Mined gaps (discovered, not yet attempted)
- (none yet)
