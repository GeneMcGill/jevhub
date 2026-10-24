<div align="center">

<a href="https://github.com/Guislabert/jevhub">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/hero-dark.svg">
    <img alt="JevHub" src="assets/hero-light.svg" width="820">
  </picture>
</a>

</div>

<div align="center">

[![CI](https://img.shields.io/badge/CI-passing-34A853.svg)][ci]
[![版本](https://img.shields.io/badge/版本-0.1.0-4285F4.svg)][vlg]
[![License: MIT](https://img.shields.io/badge/License%3A%20MIT-FBBC05.svg)][osi]

</div>

<h1 align="center">JevHub</h1>

<div align="center">

> **Jev / System-1 agent 生态**的策展式发布视频目录 —— 发现项目发布、演示与走查，由免费、官方、合规渠道每日刷新。

</div>

> [!NOTE]
> 已上线： [jevhub.example.org](https://jevhub.example.org/) —— 基于 GitHub Pages 的静态目录。如果它对你有帮助，请点亮 star，帮助更多人发现 Jev 生态。

<div align="center">

[English](README.md) | 简体中文

</div>

---

## 为什么（Why）

**Jev / System-1 agent 生态**的发布视频与项目演示散落在 GitHub、Hacker News 和 YC 讨论各处。这里没有单一、可浏览的地方来发现「何时发布了什么」——新的 agent、工具链和演示每天都在上线，而社区缺少一个共享目录来追踪它们。

> **JevHub 就是那个目录。** 由免费、官方、合规渠道每日刷新的策展发布目录。

## 是什么（What）

JevHub 是一个**静态 Astro 5 网站**（无 JS 框架运行时、无后端），收录 **864+ 个项目**、覆盖 **17 个分类**，以发布视频目录的形态呈现（可以理解为 Jev 生态版的 [`whatships.com`](https://whatships.com/)）。每个条目都链接回它的 GitHub 源、HN/YC 讨论与评审依据。

数据来自**零付费 API 管线**（GitHub REST Search API + HN Algolia），每日采集后静态构建并部署到 GitHub Pages。

## 目录结构

```
jevhub/
├── src/
│   ├── pages/
│   │   ├── index.astro        #  hero + 分类芯片 + 卡片网格
│   │   ├── videos/[slug].astro #  每个项目独立详情页
│   │   ├── tools.astro        #  字母序索引
│   │   ├── studios.astro      #  按 star 排序的团队
│   │   ├── submit.astro       #  issue-only 提交流程
│   │   └── about.astro
│   ├── layouts/Base.astro
│   ├── data/projects.json     #  每日数据快照
│   └── styles.css
├── public/
│   ├── banner.svg
│   ├── favicon.svg
│   └── llms.txt               #  AI 引用索引
├── assets/hero-light.svg      #  readme-harness hero（亮）
├── assets/hero-dark.svg       #  readme-harness hero（暗）
├── tools/version-check.mjs    #  readme-harness 版本守卫
└── .github/workflows/ci.yml   #  版本链 + 构建
```

## 功能（Features）

| 功能 | 说明 |
|---|---|
| 分类芯片 | 全部 / AI / 开发工具 / 设计 / 动效 / 生产力 / 消费 / 硬件 / 其他 |
| 发布卡片 | 海报 + 账号 + 名称 + 分类的可浏览网格 |
| `/videos/<slug>/` | 每个项目的独立详情页 |
| 工具索引 | 生态项目字母序列表 |
| 工作室 | 按 GitHub star 排序的团队 |
| 提交 | 打开 issue 即可——目录变更无需 pull request |
| AI 就绪 | `llms.txt` + JSON-LD（`Dataset`、`SoftwareApplication`） |

## 快速开始

```bash
git clone https://github.com/Guislabert/jevhub.git
cd jevhub
npm install
npm run dev       # → http://localhost:4321
npm run build     # → dist/（静态页面，约 1s 构建）
```

如需自行部署，把 `dist/` 发布到任意静态托管即可，无需后端。

## 采纳与贡献（Adopting / Contributing）

目录类提交走 [`awesome-jev-projects` issue 流程](https://github.com/logicrw/awesome-jev-projects/issues/new?template=project.yml) —— 目录变更无需 pull request。代码类 PR 欢迎。

版本纪律遵循 [SemVer 2.0.0](https://semver.org/)，由 `tools/version-check.mjs` 守卫：`package.json.version === CHANGELOG 最新小节 === README 徽章`（见 [SPEC](https://github.com/Guislabert/readme-harness/blob/main/SPEC.md) §5）。

## 反馈

缺项目、链接失效或分类建议，请在 issue 提出。

[ci]: https://github.com/Guislabert/jevhub/actions
[vlg]: CHANGELOG.md
[osi]: https://opensource.org/licenses/MIT

## 许可证

MIT © Guislabert —— 见 [LICENSE](LICENSE)。