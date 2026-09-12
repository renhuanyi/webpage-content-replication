# Webpage Content Replication Skill

用于复刻无法直接保存的网页与在线文档，服务于个人学习、离线阅读、知识整理和个人归档。

This Skill preserves webpages and online documents that a user is authorized to access but cannot directly download or save in full. It is intended for personal study, offline reading, knowledge organization, and personal archiving.

## 能做什么

- 复刻普通长网页、折叠内容、分页内容、独立滚动区域和虚拟滚动页面。
- 生成连续截图、完整 Markdown、可离线打开的 HTML，或三者组合。
- 检查正文顺序、稳定 ID、页面末尾、图片资源闭包和离线可用性。
- 在授权页面存在稳定文档对象时采用结构化采集，否则回退到 DOM、可见正文或截图。
- 采用 Agent Skills 通用目录格式，可适配 Codex、Claude Code、WorkBuddy / WorkPuddy 及其他兼容 Agent。

## What it does

- Handles long pages, collapsible sections, pagination, nested scroll containers, and virtualized lists.
- Produces continuous screenshots, complete Markdown, offline HTML, or a combined delivery.
- Verifies content order, stable IDs, end-of-page evidence, local media closure, and offline rendering.
- Uses structured capture when an authorized page exposes a stable document object, with DOM, visible-content, and screenshot fallbacks.
- Uses the portable Agent Skills directory format so the same package can be imported by Codex, Claude Code, WorkBuddy / WorkPuddy, and other compatible agents.

## 三种模式 / Three modes

| 模式 | 交付物 | 适用场景 |
|---|---|---|
| `visual-archive` | 连续截图、manifest、验收记录 | 保留页面视觉状态 |
| `content-replica` | 完整 Markdown、离线 HTML、验收记录 | 阅读、编辑和离线保存 |
| `dual-delivery` | 截图 + Markdown + HTML | 同时需要视觉证据和可读内容 |

## 安装 / Installation

将仓库克隆到 Codex 用户 Skills 目录：

```bash
git clone https://github.com/renhuanyi/webpage-content-replication.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/webpage-content-replication"
```

Clone the repository into your Codex user Skills directory, then start a new Codex conversation so discovery can refresh.

For Claude Code, copy the same directory to `~/.claude/skills/webpage-content-replication/` or a project’s `.claude/skills/webpage-content-replication/`. For WorkBuddy / WorkPuddy, import the Release ZIP or the directory through its Skill import or marketplace flow and keep `SKILL.md` at the package root. See [cross-agent compatibility](references/agent-compatibility.md).

## 使用 / Usage

```text
使用 $webpage-content-replication，把这个我有权访问但无法直接完整保存的网页复刻为 Markdown 和离线 HTML，用于个人学习。
```

```text
Use $webpage-content-replication to preserve this webpage that I am authorized to access as Markdown and offline HTML for personal study.
```

## 权限与版权边界 / Access and copyright boundaries

使用者必须对目标内容拥有合法访问权，并遵守内容来源的版权和服务条款。本 Skill 不得用于绕过登录、付费墙、访问控制、DRM 或其他技术限制。访问内容不代表获得传播、商用或二次公开原内容的许可。

Users must be authorized to access the target content and must follow the source's copyright terms and terms of service. This Skill must not be used to bypass login requirements, paywalls, access controls, DRM, or other technical restrictions. Access does not grant redistribution, commercial-use, or republication rights.

The package format is portable, but host tools are not identical. A host without browser or file capabilities may only provide planning or content guidance; it must not claim screenshot, resource-download, or offline-HTML acceptance without evidence.

The MIT License in this repository applies to the Skill instructions and supporting documentation in this repository. It does not apply to third-party content archived by users.

## 当前状态 / Status

Version `v0.3.0`, lifecycle `Observation`. Core workflows have succeeded on representative long and virtualized documents, but cross-site behavior, complex pagination, multi-section expansion, protected media, and every browser environment are not claimed as universally verified.

