# Observation Log

## 2026-11-03 — CDP-driven in-page JavaScript structured capture

- Representative authorized Chrome capture workflows use Chrome DevTools Protocol `Runtime.evaluate` to execute a bounded in-page JavaScript expression and extract a target document object such as a block model / `dataJson`.
- The precise implementation name for this path is **CDP-driven in-page JavaScript structured capture**. It is distinct from API scraping and from reading only the currently rendered DOM text.
- This remains an `Observation`-level, host- and site-dependent capability. When CDP is unavailable or the target boundary is unclear, the Skill must fall back to DOM, virtual scrolling, visible content, or screenshots.
- The public package must not include authentication storage, unrelated application state, private project paths, or source-page content.

## 2026-09-12 — Public release boundary

- The public package is a privacy-safe distribution of an existing self-maintained Skill.
- Personal paths, named private projects, archived source content, screenshots, account information, and authentication data are not included.
- Representative long-page and virtualized-document workflows support the current contract, but the lifecycle remains `Observation`.
- General behavior across arbitrary sites, complex pagination, multiple collapsible regions, protected media, and every browser environment remains unverified.
- A successful local package validation does not prove that a third party has installed or invoked the Skill.
- Agent Skills format compatibility is structural; browser, file, network, and login capabilities remain host-specific and require separate runtime validation.

## Operational observations

- A single full-page screenshot does not prove complete coverage of a virtualized list or nested scrolling container.
- File creation and ZIP integrity do not prove content completeness, resource closure, or offline browser usability.
- Structured page data can improve fidelity when its boundary is clear, but it must not include authentication storage or unrelated application state.
- Complex tables and grids may require embedded HTML in Markdown; plain-text linearization must be disclosed as a structural downgrade.
