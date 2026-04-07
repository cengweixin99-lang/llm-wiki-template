# LLM Wiki 模板使用指南

## 快速开始

### 1. 复制模板

将 `llm-wiki-template` 文件夹复制到你想创建知识库的位置，重命名为你的知识库名称（如 `my-wiki`）。

### 2. 创建必要文件夹

```
my-wiki/
├── raw/           ← 创建此文件夹，放入原始资料
├── wiki/          ← 创建此文件夹，存放编译后的页面
├── prompts/       ← 已包含
├── templates/     ← 已包含
├── index.md
├── log.md
└── schema.md
```

### 3. 配置 Agent 规则

根据你使用的 Agent，复制对应的规则文件：

| Agent | 规则文件 | 位置 |
|-------|----------|------|
| Trae IDE | `project_rules.md` → `.trae/rules/project_rules.md` | 项目根目录 |
| Claude Code | `project_rules.md` → `CLAUDE.md` | 项目根目录 |
| Cursor | `project_rules.md` → `.cursorrules` | 项目根目录 |
| Copilot | `project_rules.md` → `.github/copilot-instructions.md` | 项目根目录 |

### 4. 开始使用

```
1. 将资料放入 raw/ 文件夹
2. 对 Agent 说："帮我编译 raw/xxx.md"
3. Agent 会自动：
   - 创建 wiki 页面
   - 更新 index.md
   - 记录 log.md
```

---

## 文件说明

| 文件/文件夹 | 用途 |
|-------------|------|
| `schema.md` | 编译规范，定义页面类型和写入规则 |
| `project_rules.md` | Agent 规则，指导 Agent 如何工作 |
| `index.md` | 知识地图，所有页面的索引 |
| `log.md` | 编译日志，记录所有操作 |
| `prompts/` | 提示词模板 |
| `templates/` | 页面模板 |

---

## 常用命令

| 命令 | 说明 |
|------|------|
| "帮我编译 raw/xxx.md" | 编译单个原始资源 |
| "帮我编译 raw/ 下的新资料" | 批量编译 |
| "帮我完善 [[页面名]]" | 补充 stub 页面内容 |
| "帮我同步一下" | 检查同步状态 |
| "把这个答案存入 wiki" | 手动触发答案回写 |

---

## 核心理念

**"一次整理、持续复用、复利增长"**

- 传统 RAG：每次查询都重新检索碎片信息，无积累
- LLM Wiki：LLM 维护持久化知识，知识越用越丰富

**人机分工**：
- 人类：筛选资源、提问、指导方向
- LLM：整理、归档、交叉引用、矛盾检测、增量更新

---

## 更多信息

- 基于 [Karpathy llm-wiki](https://github.com/karpathy/llm-wiki) 模式
- 适配 Obsidian 双向链接语法
