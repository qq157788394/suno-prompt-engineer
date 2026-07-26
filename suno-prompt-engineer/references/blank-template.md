# 空白模板（建立你自己的模板库）

> 复制本文件，按你的曲风填充。每个模板 = 一个 `###` 标题 + Styles 提示词 + Lyrics 快速模板。
> 文件名建议：`XX系列模板.md`（如 `张惠妹系列模板.md`）。Agent 会自动扫描文件内的 `###` 标题来建立模板索引。
>
> **模板定位：一个模板要能套很多首歌。** 因此 Lyrics 采用完整的 **14 段标准骨架**（见下），作为可复用的结构基底。实际套用到某首歌时，只填该歌用到的段落（用户没给的段落不强行填）。

---

### 模板名（模仿 《参考曲》）

#### Styles 提示词

```text
<genre 描述行：曲风 + 情绪弧线，可含 Tempo/BPM/Key>
VOCAL: <人声：声部、音色、唱法、动态变化>
ARRANGEMENT: <编曲：乐器、织体、段落动态设计、特殊亮点>
PRODUCTION: <制作：混音风格、空间感、动态范围、音色质感>

// 可选
禁止：<Suno 易乱加的元素，如 crowd, live concert, heavy distortion>
// 原创曲需注明
Tempo is X BPM in the key of Y
```

#### Lyrics 快速模板（14 段标准骨架）

```text
[Intro]
[Instrument: ]
[Texture: ]
[Dynamics: ]
(Instrumental)

[Verse 1]
[Vocal: ]
[Instrument: ]
[Dynamics: ]
[歌词]

[Verse 2]
[Vocal: ]
[Instrument: ]
[Dynamics: ]
[歌词]

[Pre-Chorus 1]
[Vocal: ]
[Instrument: ]
[Dynamics: ]
[歌词]

[Chorus 1]
[Vocal: ]
[Backing-Vocals: ]
[Instrument: ]
[Texture: ]
[Dynamics: ]
[歌词]

[Interlude 1]
[Instrument: ]
[Dynamics: ]
(Instrumental)

[Verse 3]
[Vocal: ]
[Instrument: ]
[Dynamics: ]
[歌词]

[Verse 4]
[Vocal: ]
[Instrument: ]
[Dynamics: ]
[歌词]

[Pre-Chorus 2]
[Vocal: ]
[Instrument: ]
[Dynamics: ]
[歌词]

[Chorus 2]
[Vocal: ]
[Backing-Vocals: ]
[Instrument: ]
[Texture: ]
[Dynamics: ]
[歌词]

[Interlude 2]
[Instrument: ]
[Dynamics: ]
(Instrumental)

[Bridge]
[Vocal: ]
[Instrument: ]
[Dynamics: ]
[歌词]

[Grand Chorus]
[Vocal: ]
[Backing-Vocals: ]
[Instrument: ]
[Texture: ]
[Dynamics: ]
[歌词]

[Outro]
[Instrument: ]
[Dynamics: ]
(Instrumental)
[Stop]
```

> **少即是多（Lyrics 属性要少而准）**：每段只写**该段最关键的特征内容**，不要为了"看起来专业"而堆标签。属性标签和文字**不是越多越好**——写太多反而会让 Suno 注意力涣散，甚至丢弃部分指令。判据：这个标签 / 这句描述，是否定义了"这一段最该被听见的样子"？不是就删掉。
> - 有声乐段落基础三件套：`[Vocal:]` + `[Instrument:]` + `[Dynamics:]`；`[Backing-Vocals:]` / `[Texture:]` 仅在合唱、音墙等真正需要时加，非每段必写。
> - 器乐段落（前奏 / 间奏 / 尾奏）**不写 `[Vocal:]`**，改用 `[Instrument:]` / `[Arrangement:]` / `[Texture:]`。
> - 特殊需要独立标签：`[Modulation: Key Change up]`（升调）、`[Mood: ...]`（情绪特殊处理）、`[Texture: ...]`（织体特殊变化，如极稀疏 / 音墙）。
> - 行内歌词注解允许：`(slowly) 歌词`、`[Sudden Drop] 歌词`、`(Powerful) 歌词`。
> - key 名完全自由，没有"错 key"；同一首歌内尽量保持命名统一即可。

---

## 模板索引格式（你的模板如何被收录）

把本文件另存为 `XX系列模板.md` 并填充后，Agent 会自动扫描文件内的 `###` 标题来建立索引
（格式示范见 `references/template-index.example.md`）。

索引表格式示意：

| 歌手 / 曲风 | 可用模板（即你的 `###` 标题） |
|---|---|
| 张惠妹 | 阿密特冷峻硬摇滚、抒情摇滚、摇滚舞曲… |
| 周杰伦 | 经典中国风、说唱抒情… |

> 你只需保证「每个模板 = 一个 `###` 标题 + Styles 提示词 + Lyrics 快速模板」，Agent 会处理好索引与其余的事。
