# AGENTS.md — AI working contract

> Generated following [Readme Harness](https://github.com/Guislabert/readme-harness) conventions.
> An AI coding agent reads this file when it starts work in this repository.

## Project

- **Name**: `jevhub`
- **Kind**: Node (Astro 5 static site)
- **Version**: `0.1.0`
- **CI**: GitHub Actions (`.github/workflows/ci.yml`)

## README discipline (enforced, not optional)

- Keep `README.md` in **English (en-GB)**; other languages live in separate
  `README.<lang>.md` files (e.g. `README.zh-CN.md`), never inline.
- Keep every README **Version badge** in sync:
  `package.json.version` === `CHANGELOG newest section` === `README badges`
  (run `node tools/version-check.mjs`).
- Version bumps are release points (SemVer): fix → PATCH, backward-compatible
  feature → MINOR, breaking change → MAJOR. Pre-`1.0` (`0.y.z`) is unstable.

## Badge row

The header badge row follows the `badges-google` semantic palette:
CI `#34A853` · Version `#4285F4` · License `#FBBC05`. Order:
built → versioned → published → licensed → meta. Centered inside a
`<div align="center">` below the hero image.

## Data & build

- `src/data/projects.json` is the daily data snapshot, produced by collectors
  (GitHub REST Search API + HN Algolia) outside this repo.
- Build with `npm run build` (Astro 5 static); deploy by publishing `dist/`
  to any static host.

## Testing

- Run `node tools/version-check.mjs` and `npm run build` locally before
  depending on a change.
- CI reports but is never your only verification.