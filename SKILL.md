---
name: webpage-content-replication
description: "复刻用户有权访问、但平台无法直接下载或完整保存的长网页与在线文档，生成连续截图、完整 Markdown、可离线打开的 HTML，或三者组合，并完成对应验收；主要用于个人学习、离线阅读和个人归档，不适用于摘要、单张截图或绕过访问限制。"
---

# 网页与文档内容复刻

本 Skill 用于保存用户有权访问、但网站没有提供直接下载或完整保存功能的网页与在线文档。主要用途是个人学习、离线阅读、知识整理和个人归档。

不得利用本 Skill 绕过登录、付费墙、访问控制、DRM 或其他技术限制。获得页面访问权不等于获得传播、商用或公开原内容的权利。

## 1. 选择交付模式

- `visual-archive`：用户要连续截图、视觉归档或保存页面原始视觉状态。
- `content-replica`：用户要完整正文、可编辑 Markdown、图片完整或可离线打开的 HTML。
- `dual-delivery`：用户明确同时要截图证据和 Markdown/HTML 正式文件。

用户已经明确要求 Markdown、HTML 或“文字和图片完整”时，直接使用 `content-replica`。只有模式会显著改变工作量或完成条件时才确认。

ZIP 只能作为已验收产物的可选封装，不能单独证明复刻完成。最终回复必须分别提供正式 Markdown、HTML、验收记录或截图目录，不能只交付 ZIP 或资源包。

## 2. 共同工作流

1. 确认目标页面、标题、URL、当前登录状态以及用户保存该内容的权限边界。已有登录态可以直接使用；没有登录态不得绕过登录。
2. 判断页面结构：普通长页面、折叠区、分页、独立滚动容器、虚拟列表，或多种结构组合。
3. 按所选模式采集：视觉模式保存固定视口重叠截图；内容模式在页面已加载稳定目标文档对象且授权边界明确时，优先考虑浏览器结构化采集，否则保存可回读的 DOM、正文和实际资源引用；双交付同时执行两条路径。结构化采集时读取 [browser-structured-capture.md](references/browser-structured-capture.md)。
4. 对虚拟滚动或动态页面使用稳定 item ID；没有稳定 ID 时组合使用 DOM 路径、正文哈希、顺序锚点和窗口重叠，并在验收记录中说明覆盖置信度。
5. 比较重复 item 前，归一化空白、动态 fragment 和框架临时属性。正文、根 block 类型或有效资源引用出现真冲突时阻断生成，不能后写覆盖。
6. 从合并正文的实际引用建立资源闭包。检查 `src`、`data-src`、`poster`、`srcset`、`source`、CSS 背景图和 iframe 等入口，不能只信页面资源清单。
7. 生成正式产物后执行静态验收和真实浏览器验收。目录、折叠、灯箱等交互只有实际生成时才验收。
8. 原目录验收通过后才可生成 ZIP；ZIP 解压一致性不能替代正式文件验收。

## 3. 模式完成门禁

### visual-archive

必须有连续截图、来源与标题、视口记录、结构覆盖、末尾证据和截图清单。详情见 [visual-archive.md](references/visual-archive.md)。

### content-replica

必须有完整可读的 Markdown、可直接通过 `file://` 打开的离线 HTML、正文与图片资源闭包、格式边界说明、静态验收和真实浏览器验收。详情见 [content-replica.md](references/content-replica.md)。

### dual-delivery

必须同时满足 `visual-archive` 和 `content-replica` 的门禁。截图是视觉证据，Markdown 是可读内容交付，HTML 是离线呈现，三者不能互相替代。

## 4. 完成与边界

- “文件已生成”“文件已压缩”“文件大小正常”都不等于复刻完成。
- 缺少关键 item、存在真冲突、关键图片失败、容器未渲染或 HTML 只能通过临时服务器打开时，必须说明具体缺口。
- 文字出现在 Markdown 中不等于表格、网格、富文本或视觉结构被保留。
- 截图只证明视觉覆盖，不能据此声称获得了底层 HTML、可编辑文字或源图片。
- 统一门禁、离线检查、动态数量和失败状态见 [verification.md](references/verification.md)。
- 优先使用用户指定且已有登录态的浏览器。需要真实 UI 滚动和截图时，使用可用的浏览器控制或 Computer Use。
- 导出接口被拒绝时，只能回退到授权范围内的可见区域截图、DOM 或结构化采集，不得规避限制。
- 页面焦点丢失、滚动容器不动、内容持续变化、分页无法打开或无法确认底部时，停止“已完成”判断并报告缺口。

## 5. 跨 Agent 使用

本 Skill 遵循 Agent Skills 的通用目录格式。将整个目录保持在一起，并让宿主 Agent 读取根目录下的 `SKILL.md`；`references/` 中的文件按相对路径加载。

- Claude Code：放入 `~/.claude/skills/webpage-content-replication/`，或当前项目的 `.claude/skills/webpage-content-replication/`。
- WorkBuddy / WorkPuddy：通过其技能导入或技能市场安装，确认导入包根目录直接包含 `SKILL.md`；具体浏览器、截图和文件工具以宿主提供的能力为准。
- 其他 Agent：使用该 Agent 的自定义 Skill 目录或导入功能，保持 `SKILL.md`、`references/` 和 `agents/` 的相对结构。

宿主没有浏览器控制或文件写入能力时，只能完成计划、可见内容整理或能力边界说明，不能声称完成截图、资源下载或离线 HTML 验收。

不同宿主的安装位置、导入方式和工具映射见 [agent-compatibility.md](references/agent-compatibility.md)。

