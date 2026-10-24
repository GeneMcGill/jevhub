<div align="center">

<img src="public/banner.svg" width="100%" alt="JevHub banner" />

# JevHub

**发现 Jev 生态系统的项目发布**

[![Live site](https://img.shields.io/badge/Live-genemcgill.github.io/jevhub-d7fa91?style=flat-square&labelColor=1a201a)](https://genemcgill.github.io/jevhub/)
[![Catalog](https://img.shields.io/badge/Catalog-864%2B%20projects-2563eb?style=flat-square)](#数据)
[![License](https://img.shields.io/badge/License-MIT-d97706?style=flat-square)](LICENSE)
[![Built with Astro](https://img.shields.io/badge/Built%20with-Astro%205-8b5cf6?style=flat-square)](https://astro.build)

[English](README.md) · [简体中文](#这是什么)

</div>

---

## 这是什么？

JevHub 是 **TypeSafe Jev / System-1 agent 生态系统**的策展目录 —— 864+ 个项目，发布驱动形态，布局类似一个发布视频目录（可以理解为「Jev 生态版的 [whatships.com](https://whatships.com/)」）。每个条目都会链接回它的 GitHub 源、HN/YC 讨论以及评审依据。

**864 个项目 · 17 个分类 · 零付费 API 数据管线。** 所有数据均通过免费、官方、合规的渠道采集（GitHub REST API + HN Algolia），并每日刷新。

导航与你熟悉的目录流程一致：

- **发现（Discover）** —— 按分类芯片浏览所有发布（全部 / AI / 开发工具 / 设计 / 动效 / 生产力 / 消费 / 硬件 / 其他）
- **视频（Videos）** —— 每个项目都有独立的 `/videos/<slug>/` 详情页
- **工具（Tools）** —— 字母序索引
- **工作室（Studios）** —— 按 star 数排序的团队
- **提交（Submit）** —— 打开 issue 即可，无需提交 pull request

⭐ **如果这对你有用，请为它点亮 star** —— 这有助于更多人找到它。

## 数据

| 来源 | 采集内容 | 状态 |
|---|---|---|
| [awesome-jev-projects](https://github.com/logicrw/awesome-jev-projects) | 864 个精选 Jev/System-1 项目（种子数据） | ✅ 完成 |
| GitHub REST Search API | `topic:jev` 新仓库 + 每日 star | ✅ 合规限流 |
| HN Algolia API | 详情页用的 "Jev" 讨论 | ✅ 每日 |
| X / YC（watchlist 浏览） | 海报 + 真实浏览数 | 🚧 下一步 |

## 架构

```
collectors（宿主机 + 沙箱） ──> outerloop-digest 仓库 ──> astro build ──> gh-pages
```

- **前端**：Astro 5 静态（869 页，1.0s 构建），无 JS 框架运行时
- **数据**：`outerloop-digest` 私有仓库中按日保存的 JSONL/JSON 快照
- **部署**：GitHub Pages（`gh-pages` 分支），与构建基础设施完全解耦

## 快速开始

```bash
git clone https://github.com/GuislaBert/jevhub.git
cd jevhub
npm install
npm run dev        # → http://localhost:4321
npm run build      # → dist/（866 个静态页面，约 1s）
```

如需自行部署构建产物：将 `dist/` 发布到任意静态托管即可，无需后端。

## 设计说明

这套 UI 是**为 Jev 生态适配的 whatships.com 复刻**：

- 深色优先、证据精简：在采集到真实素材前，卡片海报先用首字母渐变占位符
- 芯片筛选覆盖全部 8 个 whatships 分类；真实数量实时更新
- `llms.txt` + JSON-LD（`Dataset`、`SoftwareApplication`）为 AI 引用就绪

## 路线图

- [ ] 每个项目的真实 stars/stars24h（每日 GitHub 图表）
- [ ] 将 HN/YC 讨论链接合并进每个 `/videos/<slug>/` 页面
- [ ] X 海报 + 真实浏览数（watchlist 浏览器遥测）
- [ ] 自定义域名 + CNAME

## 贡献

目录类提交走 [awesome-jev-projects issue 流程](https://github.com/logicrw/awesome-jev-projects/issues/new?template=project.yml) —— 目录变更无需 pull request。代码类 PR 欢迎。

## 许可证

MIT —— 见 [LICENSE](LICENSE)。