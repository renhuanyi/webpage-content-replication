# 跨 Agent 兼容说明

本发行版采用 Agent Skills 的可移植格式：一个技能目录，根目录有 `SKILL.md`，可选的 `references/`、`scripts/` 和 `assets/` 通过相对路径关联。宿主 Agent 可以忽略不认识的附加元数据文件，只需读取 `SKILL.md` 和任务所需的 reference。

## Claude Code

个人安装目录：

```text
~/.claude/skills/webpage-content-replication/
```

项目安装目录：

```text
.claude/skills/webpage-content-replication/
```

目录名保持为 `webpage-content-replication`，根目录直接放置 `SKILL.md`。Claude Code 可以按描述自动加载，也可以使用 `/webpage-content-replication` 直接调用。不要把仅 Codex 专用的 `agents/openai.yaml` 当作运行时依赖。

## WorkBuddy / WorkPuddy

WorkBuddy 的技能市场或技能导入流程要求技能包根目录包含 `SKILL.md`，并支持可选的 `references/`、`scripts/` 和模板目录。本仓库的公开包已经按此结构组织：导入时选择仓库目录或 Release ZIP 的顶层技能目录，不要把仓库外层目录再套一层。

WorkBuddy 的浏览器、文件系统和 MCP 能力由宿主配置决定。本 Skill 只声明工作流和验收标准，不假设某个 WorkBuddy 专用工具名、登录态、MCP 服务、Node/Python 路径或本地目录。

如果你所说的产品名称是 WorkPuddy 而不是 WorkBuddy，请以该产品实际导入器的字段和目录要求为准；只要它遵循 Agent Skills 的 `SKILL.md` 入口，正文和 references 可以直接复用。

## 其他 Agent

1. 解压或复制整个技能目录。
2. 确认宿主能发现根目录 `SKILL.md`。
3. 确认宿主支持 Markdown 指令和相对文件引用。
4. 根据宿主工具名称，将“浏览器控制”“截图”“文件写入”“HTML 打开”映射到等价能力。
5. 在最终回执中分别说明：实际完成的采集、宿主工具限制、未验证的浏览器或媒体能力。

## 兼容性边界

跨 Agent 兼容只证明“技能文件可以被读取并提供同一套工作流指令”，不证明每个平台都具备相同的浏览器、截图、网络、文件系统、登录态、资源下载或离线浏览器验收能力。平台专项能力必须在对应宿主中单独验证。

