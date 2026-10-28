# trv-page

Public repository for the static web page of The Remote Viewer (TRV), served by GitHub Pages at https://sentinel-architech.github.io/trv-page/.

- Visibility: public.
- Contents: a single `index.html`, `SECURITY.md`, CODEOWNERS (after its PR), and CI workflows (HTML check, gitleaks secret scan, CodeQL, actionlint).
- Licence: none applied yet. AGPL-3.0 is planned but has not been applied.

## How it fits together

```mermaid
flowchart LR
  Src["The-Remote-Viewer-Native-Source (Rust code, private)"] -->|release workflow| Rel["The-Remote-Viewer-Native (APK releases, private)"]
  Lib["The-Remote-Viewer-Library (documents, private)"] --> App["TRV app on the phone (local-first)"]
  Rel --> App
  Page["trv-page (public web page)"] --> Rel
  App -. planned .-> Sol["Solana (identity registry; devnet only today)"]
  Rel -. planned .-> IPFS["IPFS (pinned copies of releases and this page)"]
```
Solid lines exist today. Dotted lines are plans, not live yet. Details: `docs/DECENTRALIZATION.md` in The-Remote-Viewer-Native-Source.
