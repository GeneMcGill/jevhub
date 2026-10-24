<div align="center">

<a href="https://github.com/Guislabert/jevhub">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/hero-dark.svg">
    <img alt="JevHub" src="assets/hero-light.svg" width="820">
  </picture>
</a>

[![CI](https://img.shields.io/badge/CI-passing-34A853.svg)][ci]
[![Version](https://img.shields.io/badge/Version-0.1.0-4285F4.svg)][vlg]
[![License: MIT](https://img.shields.io/badge/License%3A%20MIT-FBBC05.svg)][osi]

`#astro5` `#static` `#jelv` `#whatships-replica` `#llms.txt` `#zero-backend`

</div>

# JevHub

<div align="center">

> A curated launch-video directory of the **Jev / System-1 agent ecosystem** — discover project launches, demos and walkthroughs, refreshed daily from free, official, compliant sources.

> [!NOTE]
> Deployed site: [jevhub.example.org](https://jevhub.example.org/) — a statically built GitHub Pages catalog. Star it if it helps [others find the Jev ecosystem](https://github.com/Guislabert/jevhub).

English | [简体中文](README.zh-CN.md)

</div>

---

## Why

Launch videos and project demos from the **Jev / System-1 agent ecosystem** are scattered across GitHub, Hacker News and YC discussions. There is no single, browsable place to discover what launches when — new agents, tool-chains and demos ship every day, and the community has no shared catalog to track them.

> **JevHub is that catalog.** A curated, launch-style directory of the ecosystem, refreshed daily from free, official, compliant sources.

## What

JevHub is a **static Astro 5 website** (no JS framework runtime, no backend) that indexes **864+ projects** across **17 categories**, laid out like a launch-video catalog (think [`whatships.com`](https://whatships.com/) for the Jev ecosystem). Every entry links back to its GitHub source, its HN/YC discussions, and its review basis.

Data comes from a **zero-paid-API pipeline** (GitHub REST Search API + HN Algolia), collected daily and built statically to GitHub Pages.

## Structure

```
jevhub/
├── src/
│   ├── pages/
│   │   ├── index.astro        #  hero + category chips + card grid
│   │   ├── videos/[slug].astro #  per-project detail page
│   │   ├── tools.astro        #  alphabetical index
│   │   ├── studios.astro      #  teams ranked by stars
│   │   ├── submit.astro       #  issue-only submit flow
│   │   └── about.astro
│   ├── layouts/Base.astro
│   ├── data/projects.json     #  daily data snapshot
│   └── styles.css
├── public/
│   ├── banner.svg
│   ├── favicon.svg
│   └── llms.txt               #  AI-citation index
├── assets/hero-light.svg      #  readme-harness hero (light)
├── assets/hero-dark.svg       #  readme-harness hero (dark)
├── tools/version-check.mjs    #  readme-harness version guard
└── .github/workflows/ci.yml   #  version train + build
```

## Features

| Feature | Description |
|---|---|
| Category chips | All / AI / Developer tools / Design / Motion / Productivity / Consumer / Hardware / Other |
| Launch cards | Poster + handle + name + category in a browsable grid |
| `/videos/<slug>/` | One detail page per project |
| Tools index | Alphabetical list of ecosystem projects |
| Studios | Teams ranked by GitHub stars |
| Submit | Open an issue — no pull request needed for catalog changes |
| AI-ready | `llms.txt` + JSON-LD (`Dataset`, `SoftwareApplication`) |

## Quick start

```bash
git clone https://github.com/Guislabert/jevhub.git
cd jevhub
npm install
npm run dev       # → http://localhost:4321
npm run build     # → dist/ (static pages, ~1s build)
```

To deploy yourself, publish `dist/` to any static host. No backend required.

## Adopting / Contributing

Catalog submissions ride the [`awesome-jev-projects` issue flow](https://github.com/logicrw/awesome-jev-projects/issues/new?template=project.yml) — no pull requests for catalog changes. Code pull requests are welcome.

Version discipline follows [SemVer 2.0.0](https://semver.org/) and is guarded by `tools/version-check.mjs`:
`package.json.version === CHANGELOG newest section === README badges` (see [SPEC §5](https://github.com/Guislabert/readme-harness/blob/main/SPEC.md)).

## Feedback

Raise an issue for a missing project, a broken link, or a category suggestion.

[ci]: https://github.com/Guislabert/jevhub/actions
[vlg]: CHANGELOG.md
[osi]: https://opensource.org/licenses/MIT

## License

MIT © Guislabert — see [LICENSE](LICENSE).