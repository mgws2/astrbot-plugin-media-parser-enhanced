# Changelog

## Documentation update — 2026-10-27

- Rework GitHub README into a Chinese-first project overview with a brief English summary.
- Add quick installation steps, feature table, validation limits and upstream attribution.
- Add CONTRIBUTING.md and a privacy-conscious GitHub bug report template.
- Documentation-only changes; no parser, dependency, license or production behavior changes.

## Public RC2 — 2026-10-27

- Publish the attributed upstream-derived public source snapshot, based on commit c16a938128014403057f1deeeaedecbd1fc15707.
- Restore required Bilibili parser and Apache-2.0 Douyin signing module from the verified public baseline.
- Replace only av2bv with an attributed MIT-reference positional adaptation; preserve zero conversion and explicitly reject invalid types/ranges.
- Preserve original root AGPL-3.0 LICENSE and dependency pins; include Colerar MIT and F2 license evidence in NOTICE and credits.
- Exclude production overlays, preview assets and browser sidecar.
- Offline verification: 53 tests passed with AstrBot host doubles. Live platform, QQ delivery and real host startup were not verified for this public candidate.

**Note:** GitHub source publication and real runtime deployment are separate. The public repository exists; no production deployment or standalone GitHub Release is claimed.
