---
name: delivery
description: 生成交付摘要，通知用户任务完成，提示自行检查确认
allowed-tools:
  - Read
  - Write
  - Glob
  - Grep
  - Bash
---

# 交付通知 Skill — 阶段 3d

## 输入

- `prototype/{task_dir}/pencil-execution-log.md`
- `prototype/{task_dir}/screenshots/`
- `prototype/{task_dir}/screenshots-reviewed/`
- `prototype/{task_dir}/{task_name}.pen`（唯一设计文件）

## 输出

- `prototype/{task_dir}/validation-report.md`
- `prototype/{task_dir}/delivery-summary.md`

---

## 工作流程

### Step 1：汇总执行结果

读取执行日志，统计：
- 主页面总数 / 弹窗页面总数 / 绘制成功数 / 自校验通过数 / 需人工调整数

---

### Step 2：输出自校验报告

写入 `prototype/{task_dir}/validation-report.md`：

```markdown
# {任务名称} — 自校验报告

## 执行总览
- 设计文件: {task_name}.pen（单文件，含全部页面）
- 主页面: N 个
- 弹窗页面: M 个
- 自校验通过: ✅ N+M 个
- 需人工调整: ⚠️ N 个

## 主页面详情
| Pencil 页面 | 绘制状态 | 自校验 | 截图 |
|-----------|---------|--------|------|
| P1_{页面名} | ✅ | ✅ 通过 | screenshots/P1_{页面名}.png |
| P2_{页面名} | ✅ | ⚠️ 需人工 | screenshots/P2_{页面名}.png |

## 弹窗页面详情
| Pencil 页面 | 所属主页面 | 绘制状态 | 自校验 | 截图 |
|-----------|---------|---------|--------|------|
| P1D1_{弹窗名} | P1_{主页面} | ✅ | ✅ 通过 | screenshots/P1D1_{弹窗名}.png |

## 需人工调整项
[如果有，列出页面名称和具体需调整内容]

## UI 设计要素
- 使用的要素文件: ui-design-elements.md
- 来源: 模板生成 / 用户自定义
```

---

### Step 3：输出交付摘要

写入 `prototype/{task_dir}/delivery-summary.md`：

```markdown
# 交付摘要 — {任务名称}

## 设计文件
| 文件 | 说明 | 状态 |
|------|------|------|
| {task_name}.pen | 唯一设计文件，含全部主页面和弹窗页面 | ✅ |

## .pen 文件内页面清单
| Pencil 页面名 | 类型 | 状态 |
|-------------|------|------|
| P1_{页面名} | 主页面 | ✅ |
| P1D1_{弹窗名} | 弹窗页面 | ✅ |
| P1D2_{弹窗名} | 弹窗页面 | ✅ |
| P2_{页面名} | 主页面 | ✅ |
| ... | ... | ... |

## 中间产物
| 文件 | 说明 |
|------|------|
| 01-business-architecture.md | 业务架构描述 |
| 02-page-specs.md | 页面功能原型设计描述 |
| ui-design-elements.md | UI 设计要素 |
| pencil-execution-log.md | Pencil 执行日志 |
| screenshots/ | 初版截图（每个 Pencil 页面各一张） |
| screenshots-reviewed/ | 自校验修正后截图 |
| validation-report.md | 自校验报告 |
```

---

### Step 4：通知用户

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
✅ 原型设计任务「{task_name}」已全部完成！
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📁 输出目录: prototype/{task_name}_{YYYYMMDD}/
📄 设计文件: {task_name}.pen（单文件，含 N 个主页面 + M 个弹窗页面）
🖼️  截图: N+M 张（screenshots/ 和 screenshots-reviewed/）

.pen 文件内 Pencil 页面清单:
  主页面 (N 个): P1_xxx / P2_xxx / ...
  弹窗页面 (M 个): P1D1_xxx / P1D2_xxx / ...

自校验结果:
  ✅ 通过: N+M 个页面
  ⚠️ 需人工调整: N 个页面（详见 validation-report.md）

─────────────────────────────────────────────────────
📋 下一步：请自行检查确认

1️⃣ 打开 Pencil 桌面应用
2️⃣ 打开 {task_name}.pen，在左侧「页面」面板中逐页检查
3️⃣ 重点检查：
   • 弹窗页面是否作为独立 Pencil 页面存在（非嵌在主页面画布中）
   • 行内容宽度、模块间距、列对齐、操作按钮对齐
   • 内容是否有被裁切或遮挡
4️⃣ 重点关注自校验报告中标记「需人工调整」的页面
5️⃣ 如需修改，描述具体需求，我将协助调整
6️⃣ 检查通过后，执行归档：
      mv prototype/{task_name}_{YYYYMMDD}/ prototype/history/
─────────────────────────────────────────────────────
```
