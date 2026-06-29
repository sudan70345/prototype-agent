# prototype-agent
这是一个 Agent，可以自动分析用户产品需求，生成需求文档并存放本地。
它还可以调用本地 Pencil MCP 生成原型文档，但只有在用户明确同意时才会进入 Pencil 阶段。

## 运行流程简述

1. 全新需求调用
   - 如果没有指定现有 `prototype/{任务名称}` 目录，agent 视为全新需求。
   - 此时必须询问用户是否需要同时做原型设计。
   - 用户选择「是」：继续完整三轮流程，最终进入 Pencil MCP 绘制。
   - 用户选择「否」：停止在业务架构/页面规格阶段，不调用 Pencil MCP。

2. 已指定任务目录调用
   - 如果传入了 `prototype/{任务名称}` 目录，agent 先读取该目录下现有内容。
   - 读取后，判断用户需求是否为维护/修改已有原型，还是要新做一个原型。
   - 如果用户要维护/更新：再询问是否调用 Pencil MCP 更新现有 `.pen` 或新增页面。
   - 如果用户只要更新文档而不做新原型：不调用 Pencil MCP，直接修改目录中的文档。

3. Pencil MCP 调用条件
   - 仅在用户明确同意进入原型设计或更新原有原型时，才调用 `skills/pencil-executor`。
   - 这个调用点是阶段3之前的必答决策，未获用户确认不得进入。

4. 主要输出目录
   - `prototype/{task_name}_{YYYYMMDD}/`
   - 关键文件：`01-business-architecture.md`、`02-page-specs.md`、`ui-design-elements.md`、`{task_name}.pen`、`pencil-execution-log.md`、`delivery-summary.md`

## 关键约束

- 仅创建一个 `.pen` 文件；主页面和弹窗都应在同一文件内的独立 Pencil 页面中。
- 颜色必须使用 `#RRGGBB`，字体声明必须使用字符串字面量。
- 在进入 Pencil MCP 前，必须先做调用决策，用户没有明确同意则不执行原型生成。
