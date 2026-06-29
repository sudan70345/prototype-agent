# Prototype Agent 安装与配置

## 前置要求

1. **Pencil 桌面应用**（必须已安装并运行）
   - 下载地址：https://pencil.evolus.vn/
   - 运行后保持打开状态，否则 MCP 调用会失败

2. **Pencil MCP Server**（必须已安装）
   - 安装方式：`npm install -g @pencil/mcp-server`（或参考 Pencil 官方文档）

## 配置步骤

### 在 OpenCode 中使用

1. 将本项目克隆或复制到本地
2. 在 OpenCode 中打开本项目目录
3. **（重要）激活 Pencil MCP 服务**：编辑 `opencode.json`，将 `mcp.pencil.enabled` 从 `false` 改为 `true`
   ```json
   "pencil": {
     "type": "stdio",
     "command": "pencil-mcp",
     "args": [],
     "enabled": true   // ← 改为 true
   }
   ```
   确保命令行中 `pencil-mcp` 命令可用（已安装 Pencil MCP Server）
4. 在对话中输入 `prototype-designer` 切换为该 Agent（或通过 Tab 键选择）
5. 开始对话：「我想设计一个电商 App 原型」

### 在 Claude Code 中使用

1. 将本项目克隆或复制到本地
2. 将 `claude.json` 中的 MCP 配置合并到你的 `~/.claude/settings.json` 中
   ```json
   // ~/.claude/settings.json
   {
     "mcpServers": {
       "pencil": {
         "command": "pencil-mcp",
         "args": []
       }
     }
   }
   ```
3. 在 Claude Code 中打开本项目目录
4. 开始对话，CLAUDE.md 会自动加载

### 在 Cursor 中使用

1. 将 `claude.json` 复制为 `.cursor/mcp.json`
2. 项目级指令由 CLAUDE.md 自动加载

## 使用方法

### 启动一个任务

1. 在 AI 对话中输入你想设计的原型需求，例如：「我想设计一个电商 App」
2. Agent 会引导你完成三轮递进沟通：
   - **第 1 轮**：了解业务架构（端、类型、页面、流程、风格）→ 确认
   - **第 2 轮**：逐页面沟通详细规格 → 逐页确认
   - **第 3 轮**：自动调用 Pencil 绘制 → 截图自校验 → 通知你验收
3. 所有产出文件（业务架构描述、页面规格、.pen 文件、截图、校验报告）都在 `prototype/{task_name}_{YYYYMMDD}/` 目录下

### 使用自定义 UI 设计要素

可以将你的品牌 UI 设计要素文件放入任务目录中，Agent 会自动使用它：

```
# 在任务开始前或阶段 3 之前
将你自定义的 ui-design-elements.md 放入 prototype/{task_name}_{YYYYMMDD}/
# Agent 在阶段 3 会优先使用自定义文件，否则使用模板
```

### 任务归档

任务完成后，手动将任务目录移动到归档区：

```
mv prototype/{task_name}_{YYYYMMDD}/ prototype/history/
```

---

## 项目文件清单

```
prototype-agent/
├── CLAUDE.md                    # 项目级指令（自动加载）
├── AGENTS.md                    # Agent 对话策略
│
├── opencode.json                # OpenCode 配置
├── claude.json                  # Claude Code MCP 配置
│
├── agent/
│   └── prototype-agent.md       # Agent 定义
│
├── skills/
│   ├── business-architecture/  # 阶段1：业务架构沟通
│   │   └── SKILL.md
│   ├── page-specs/             # 阶段2：逐页面规格沟通
│   │   └── SKILL.md
│   ├── pencil-executor/        # 阶段3：Pencil 执行 + 自校验闭环
│   │   └── SKILL.md
│   └── delivery/               # 阶段3d：交付通知
│       └── SKILL.md
│
├── templates/
│   └── ui-design-elements.md           # UI 设计要素模板
│
├── prototype/                   # 任务目录（自动创建）
│   └── history/                 # 归档目录（手动移动）
│
└── SETUP.md                     # 本文件（配置说明）
