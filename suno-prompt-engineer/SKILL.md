---
name: suno-prompt-engineer
description: >-
  当用户需要创作 Suno AI 音乐提示词、开发曲风或歌手模板、将歌词套入现有模板、或为指定歌曲定制提示词时使用本技能。
license: MIT
agent_created: true
---

# Suno 提示词工程

通过主Agent（客户经理）与五位专家子Agent 协作，完成 Suno 提示词的创作与交付。主Agent 不撰写、不修改提示词——只收集需求、路由任务、交付结果。

触发条件：用户要求从零创作 Suno 提示词、开发曲风模板、套用现有模板、或为指定歌曲定制提示词。

## 1. 收集需求

进入任一工作流前，与客户确认需求，按 `references/subagents/00-requirements-template.md` 格式写入 `build/<song>/00-requirements.md`。核心字段如下，完整结构见模板：

| 字段 | 说明 |
|-------|-------------|
| 任务类型 | ① 开发新模板 / 从零　② 套用现有模板　③ 为指定歌曲定制 |
| 曲风 / 流派 | 如 Mandopop hard rock、City Pop |
| 情绪线 | 起始情绪 → 终点情绪（如「冷峻 → 宣泄」） |
| 目标歌手 / 参考 | 对标歌手或参考曲目 |
| 使用场景 | 活动 BGM / 短视频 / 卡拉 OK / … |
| 原创或翻唱 | 原创需 Tempo + Key；翻唱需原曲信息 |
| 是否含歌词 | 客户提供歌词，或纯器乐 |
| 歌曲结构 | 仅 ③ 需要：实际段落结构，或交由搜索专家检索 |

## 2. 工作流路由

根据任务类型选择对应工作流。每步使用第 3 节的统一公式派发子Agent。

所有产出写入 `build/<song>/`，此为流水线临时工作目录。最终产物按工作流类型归档（见第 5 节）。

### 2.1 开发新模板 / 从零

1. **信息搜索**（01-researcher.md）→ `build/<song>/01-research.md`
2. **Styles 撰写**（02-styles-writer.md）：Read 01-research.md，结构要求=固定 14 段骨架 → `build/<song>/02-styles.md`
3. **Lyrics 撰写**（03-lyrics-writer.md）：Read 02-styles.md + 01-research.md（仅取 BPM/Key/情绪线），结构要求=固定 14 段骨架 → `build/<song>/03-lyrics.md`
4. **质检**（04-qa.md）：Read 02-styles.md + 03-lyrics.md → `build/<song>/04-qa.md`
   - 不通过：将 `04-qa.md` 连同原文件回传给对应专家修改。最多 2 轮。
5. QA 通过后，归档模板（见 5.1）。

### 2.2 套用现有模板

1. **套模板**（05-template-applier.md）：目标歌手/曲风、客户歌词（无序号段落）、风格诉求 → `build/<song>/05-applied.md`
2. 交付产物，可选归档到 `songs/<song>/`（见 5.2）。

此工作流不过质检。

### 2.3 为指定歌曲定制

与 2.1 相同序列，但「结构要求」= 目标歌曲的实际段落结构（取自需求卡或由搜索专家检索），非固定 14 段骨架。

完成后交付，可选归档到 `songs/<song>/`（见 5.2）。

## 3. 派发子Agent

所有子Agent 使用以下统一公式：

```
Read references/subagents/0X-role.md。
按「知识加载清单」加载，按「工作流程」执行，按「交付模板」输出。

任务输入：[字段列表及取值]

Write to: build/<song>/0X-output.md
```

不在派发 prompt 中注入方法论或参考文件路径。子Agent 自行从自身文件加载知识。每步验证输出文件已生成再继续。不修改子Agent 产物——需修改时回传质检报告让子Agent 修订。

## 4. 子Agent 索引

| # | 专家 | 文件 | 任务 |
|---|--------|------|------|
| 1 | 信息搜索 | `references/subagents/01-researcher.md` | 检索歌曲信息，产出知识简报 |
| 2 | Styles 撰写 | `references/subagents/02-styles-writer.md` | 撰写四段法 Styles 提示词 |
| 3 | Lyrics 撰写 | `references/subagents/03-lyrics-writer.md` | 撰写 [Key: Value] Lyrics 提示词 |
| 4 | 质检 | `references/subagents/04-qa.md` | 硬性规则质检 |
| 5 | 套模板 | `references/subagents/05-template-applier.md` | 套用现有模板输出提示词 |

## 5. 产物归档

### 5.1 模板归档（工作流 ①）

QA 通过后，将 `02-styles.md` 和 `03-lyrics.md` 的最终内容追加到 `templates/<歌手>系列模板.md`：

```markdown
### <子模板名>（模仿<对标歌曲>）
#### Styles 提示词
```text
<02-styles.md 内容>
```
#### Lyrics 快速模板
```text
<03-lyrics.md 内容>
```
```

若 `templates/<歌手>系列模板.md` 不存在则新建。同时更新 `templates/index.md`——追加一行：`<歌手> | <子模板名> | templates/<歌手>系列模板.md`。

`templates/` 目录位置：工作空间根目录下。若安装 Skill 的 Agent 工作空间非固定，每次运行时先确认或创建。

### 5.2 歌曲归档（工作流 ②/③）

可选——将最终 Styles + Lyrics 保存到 `songs/<song>/styles.md` 和 `songs/<song>/lyrics.md`，方便回顾或重跑。

## 6. 交付

- 将最终产物整理为可复制粘贴的提示词卡交付客户。
- 若通过质检，附注「已通过硬性规则质检」。
- 不向客户暴露子Agent 调度细节。
