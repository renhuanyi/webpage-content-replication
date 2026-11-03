# Skill Changelog

## 2026-11-03 — v0.5.0 CDP-driven structured capture contract

- Named the preferred implementation as CDP-driven in-page JavaScript structured capture via Chrome DevTools Protocol `Runtime.evaluate`.
- Documented extraction of a bounded target document object, such as a block model / `dataJson`, rather than API scraping or unrestricted application-state export.
- Documented DOM, virtual-scroll, visible-content, and screenshot fallbacks when CDP or a stable target boundary is unavailable.
- Kept this public deployment variant privacy-safe and at lifecycle `Observation`; no new binary Release ZIP is created by this source synchronization.

## 2026-09-13 — v0.4.0 阿任 branded release

- Branded the Skill as 阿任 (Aren) in the display name, description, README, version file, and license holder.
- Preserved the Skill id, directory name, invocation name, and repository URL for backward compatibility with already-shared links.
- Added `webpage-content-replication-v0.4.0.zip` and its SHA-256 to `releases/`, keeping the v0.3.0 artifacts in place.
- Delivery modes and acceptance gates are unchanged.

## 2026-09-12 — v0.3.0 public release

- Created a privacy-safe GitHub distribution for personal learning and offline archiving.
- Preserved `visual-archive`, `content-replica`, and `dual-delivery` modes.
- Preserved structured-capture, sensitive-data, resource-closure, manifest, negative-test, and browser-acceptance requirements.
- Added explicit restrictions against bypassing login, paywalls, access controls, DRM, or copyright boundaries.
- Added bilingual public documentation, MIT licensing, lifecycle evidence, and installation guidance.
- Added host-neutral compatibility guidance for Claude Code, WorkBuddy / WorkPuddy, and other Agent Skills-compatible runtimes.
- Retained lifecycle state `Observation` and documented unverified capabilities.
