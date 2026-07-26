# Suno Prompt Engineer

> 一套用于撰写**高质量 Suno 提示词（Styles + Lyrics）**的 WorkBuddy Skill。
> 定义的是「高质量提示词的最低可行结构」——是地基，不是笼子。

## 这是什么

基于《AI 音乐制作人工作手册》的方法论提炼而成。主Agent 充当客户经理，调度五位专家子Agent（信息搜索 → Styles → Lyrics → 质检 → 套模板），稳定产出 Suno 可用的四段法 Styles 提示词与 `[Key: Value]` 属性列表 Lyrics 提示词。

## 目录结构

```
{workspace}/                        ← 用户工作空间（Skill 安装位置无关）
│
├── suno-prompt-engineer/           ← Skill 包（可开源）
│   ├── SKILL.md
│   ├── README.md
│   ├── LICENSE
│   └── references/
│       ├── glossary.md
│       ├── vocabulary.md
│       ├── blank-template.md
│       ├── qa-rules.md
│       ├── template-index.example.md
│       ├── template-index.md        ← 本地私有，Agent 自动维护，已 gitignore
│       ├── subagents/               ← 五位专家的方法论
│       │   ├── 00-requirements-template.md
│       │   ���── 01-researcher.md
│       │   ├── 02-styles-writer.md
│       │   ├── 03-lyrics-writer.md
│       │   ├── 04-qa.md
│       │   └── 05-template-applier.md
│       └── examples/
│           ├── develop-new-template.md
│           ├── apply-template.md
│           └── dynamic-design-meteor-rain.md
│
├── templates/                      ← 用户持久模板库（私有资产，不随 Skill 开源）
│   ├── 陶喆系列模板.md             ← 一个歌手一个文件，含多个子模板
│   ├── 王菲系列模板.md
│   ├── 飞儿乐团系列模板.md
│   └── index.md                    ← 模板索引（Agent 自动维护）
│
├── build/<song>/                   ← 流水线临时工作目录
│   ├── 00-requirements.md
│   ├── 01-research.md
│   ├── 02-styles.md
│   ├── 03-lyrics.md
│   └── 04-qa.md
│
└── songs/<song>/                   ← 最终交付产物（可选归档）
    ├── styles.md
    └── lyrics.md
```

## 三个工作流

| 工作流 | build/ 产出 | 最终落点 |
|--------|------------|----------|
| ① 开发新模板 | 01-research → 02-styles → 03-lyrics → 04-qa | QA 通过 → 追加到 `templates/<歌手>系列模板.md`，更新 index.md |
| ② 套用现有模板 | 05-applied | 交付客户，可选归档到 `songs/<歌名>/` |
| ③ 为指定歌曲定制 | 同 ① | 交付客户，可选归档到 `songs/<歌名>/` |

## 安装

将本目录放入 WorkBuddy 的技能目录（用户级 `~/.workbuddy/skills/` 或项目级 `.workbuddy/skills/`），刷新技能列表即可启用。

`templates/` 和 `build/` 目录由 Agent 首次运行时在工作空间根目录自动创建。

## 使用

直接对 Agent 说「帮我用 Suno 做一首 XX 风格的歌」。Agent 会：

1. 判断工作流（开发模板 / 套模板 / 定制歌曲）；
2. 调度子Agent 逐步产出 Styles 与 Lyrics 提示词；
3. 质检通过后归档模板或交付产物。

## 模板管理

### Skill 产出模板

工作流 ① QA 通过后，Agent 自动将 Styles + Lyrics 追加到对应歌手的系列模板文件中，并更新模板索引。

### 用户导入模板

将 `.md` 模板文件放入 `templates/` 目录，Agent 扫描文件名和 `###` 标题自动重建索引。格式参照现有系列模板文件。

## 资产与开源

- 本 Skill **不内置任何专有模板**。`templates/` 目录下的系列模板是用户私有资产，**不会**随 Skill 开源。
- `references/template-index.md` 由 Agent 在本地生成，含私有模板名，已 gitignore，**请勿提交到公开仓库**。
- 可安全开源的部分：SKILL.md、README.md、glossary.md、vocabulary.md、qa-rules.md、blank-template.md、examples/、subagents/。

## License

[MIT](LICENSE)
