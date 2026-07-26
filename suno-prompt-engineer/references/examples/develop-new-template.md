# 范例：开发新模板（甜蜜配方）

## 任务

开发一首"甜妹舞曲"风格的 Suno 提示词，对标姚晓棠《甜蜜配方》（Mandopop Upbeat Sweet Pop）。

## 用户侧参考分析（输入，仅作拆解参考）

用户/分析侧给的聚合标签（注意：这是**需求侧输入**，不是产出格式）：

```
音乐类型：Mandopop
风格：Upbeat Sweet Pop
情感：Sweet, Energetic, Cheerful
主要乐器：Bright Acoustic Guitar Strumming, Punchy Upbeat Drums, Bouncy Bassline, Shimmery Synthesizers
混音风格：Clean Pop Mix, Forward Vocals, Wide Stereo Synthesizers
人声身份：Sweet Young Female
演唱力度：Energetic and Bouncy
演唱技巧：Crisp Articulation
多声部逻辑：Double Tracked Chorus, Playful Backing Vocals
结构控制：Upbeat Intro, Energetic Pre-Chorus Build, Explosive Bright Chorus
节奏同步：Driving Dance Pop Groove
空间感指令：Bright Reverb on Vocals, Wide Synths
```

> 这是把参考曲"翻译"成结构化意图的过程。AI 的产出（下方）会把这些重新组织成四段法 + 属性列表 Lyrics。

## AI Agent 输出（Suno Prompt）

### Styles

```text
// Suno Prompt
Mandopop upbeat sweet pop track with dance pop influences, cheerful, energetic, and optimistic emotional arc. Double-time punchy upbeat drums.
VOCAL: Sweet young female vocals. Verses feature dynamic rhythmic phrasing and crisp articulation. Choruses shift to energetic bouncy belting, supported by double-tracked leads, playful backing vocals, and lush multi-layered harmonies to create a rich vocal texture.
ARRANGEMENT: Driven by a bouncy bassline, punchy upbeat drums, and crisp claps locking into a driving dance-pop groove. Verses feature bright acoustic guitar strumming. Choruses explode with shimmery synthesizers and wide synth layers. It includes a soulful, bluesy guitar solo with blues-based bends and blues-scale licks.
PRODUCTION: Clean modern studio pop mix. Upfront forward vocals with bright plate reverb and vocal delay throws, wide stereo spread for synthesizers, punchy low-end, Pristine Hi-fi, clear instrument separation.

// 中文参考说明
华语流行欢快甜系流行曲目，融合舞曲流行风格，整体情绪明快热烈、元气满满、基调积极向上。采用倍速强劲轻快鼓点。
人声：清甜少女声线。主歌段落咬字利落，旋律节奏灵动多变；副歌转为饱满有力、轻快跳跃的强声演唱，搭配双轨主唱、灵动俏皮的伴唱以及层次丰富厚重的和声，塑造饱满立体的人声质感。
编曲：以灵动弹跳的贝斯线、强劲轻快鼓组与清脆拍手声为核心基底，构建富有驱动力的舞曲律动。主歌配以明亮扫弦木吉他；副歌部分叠加闪亮通透的合成器与宽幅多层合成器音色，氛围感拉满。曲目包含一段富有灵魂感的蓝调吉他独奏，运用蓝调推弦技巧与蓝调音阶旋律片段。
制作：干净现代的录音室流行混音。人声置于声场靠前位置，搭配明亮板式混响与人声延迟效果；合成器采用宽立体声分布，低频厚实有力，高保真音质纯净通透，各乐器声部层次清晰分明。
```

### Lyrics

```text
[Intro: Upbeat Pop]
[Instrument: Bright acoustic guitar strumming, bouncy bassline, shimmery synthesizers]
[Texture: Bouncy and cheerful]
[Dynamics: mf, energetic studio opening]
(Instrumental)

[Verse 1: Sweet Narrative]
[Lead-Vocals: Sweet young female, crisp articulation, playful and bouncy, close-mic]
[Instrument: Punchy upbeat drums, bouncy bassline, bright acoustic guitar]
[Dynamics: mp, steady dance groove]

[Verse 2: Driving Rhythm]
[Lead-Vocals: Dynamic rhythmic phrasing, slightly warmer tone]
[Instrument: Full driving dance pop groove established, crisp claps added]
[Dynamics: mp -> mf, walking forward]

[Pre-Chorus 1: Energetic Build]
[Lead-Vocals: Rising emotion, energetic delivery, subtle backing vocals]
[Instrument: Snare rolls accelerating, synth risers, bass drops out]
[Dynamics: mf -> f, intense build-up]

[Chorus 1: Explosive Bright]
[Lead-Vocals: Energetic power belting, sweet and resonant, double-tracked]
[Backing-Vocals: Lush multi-layered harmonies, playful backing vocals]
[Instrument: Wide stereo shimmery synthesizers, driving punchy drums, four-on-the-floor kick]
[Texture: Dense sweet pop wall of sound]
[Dynamics: ff, energetic release]

[Interlude 1: Playful Break]
[Instrument: Shimmery synth lead melody over bouncy bassline and crisp claps]
[Dynamics: mf, jumping rhythm]
(Instrumental)

[Verse 3: Stripped Back]
[Lead-Vocals: Playful narrative, intimate breathy delivery, crisp articulation]
[Instrument: Stripped back. Bouncy bassline, crisp snare cross-stick, acoustic guitar accents only]
[Texture: Sudden drop to sparse]
[Dynamics: mp, deep groove]

[Verse 4: Rhythm Return]
[Lead-Vocals: Bouncy phrasing, rising anticipation]
[Instrument: Full punchy upbeat drums return, bright synthesizers sweep in]
[Dynamics: mp -> mf, driving momentum]

[Pre-Chorus 2: Intense Build]
[Lead-Vocals: Energetic delivery, double tracking, sweet ad-libs]
[Instrument: Heavy snare rolls, bright synth sweeps, continuous handclaps]
[Dynamics: f -> ff, dramatic push]

[Chorus 2: Explosive Bright]
[Lead-Vocals: Energetic belting, soaring high notes, double-tracked]
[Backing-Vocals: Thick vocal pad, rich stacked harmonies, playful vocal responses]
[Instrument: Maximum wide synths, heavy driving dance pop groove, bright acoustic guitar]
[Texture: Massive bright pop wall of sound]
[Dynamics: ff, uplifting release]

[Interlude 2: Synth Dance]
[Instrument: Energetic shimmery synth solo, fast dance pop rhythm, crash cymbals]
[Dynamics: ff, high energy]
(Instrumental)

[Interlude 2: Bluesy Guitar Solo]
[Instrument: Soulful bluesy electric guitar solo, blues-based bends bends, blues-scale licks, wide vibrato]
[Dynamics: ff, intense jam]
(Instrumental)

[Bridge: Dynamic Contrast]
[Lead-Vocals: Sweet intimate whisper shifting rapidly to energetic rhythmic singing]
[Instrument: Sudden drop to sparse acoustic guitar and claps -> massive synth swell]
[Texture: Drop to sparse -> massive build]
[Dynamics: p -> ff, extreme dynamic friction]

[Grand Chorus: Epic Finale]
[Lead-Vocals: Ultimate energetic delivery, sweet soaring ad-libs, double-tracked lead]
[Backing-Vocals: Maximum lush layered harmonies, intricate counter-melodies]
[Instrument: Full band explosion, maximum shimmery synthesizers, heavy four-on-the-floor beat]
[Dynamics: fff, stadium pop energy]

[Outro: Fading Groove]
[Arrangement: Smooth dance pop fade]
[Lead-Vocals: Playful fading ad-libs, echoing vocal delay throws]
[Instrument: Bouncy bassline and upbeat drums slowly fading out]
[Dynamics: mf -> pp -> Stop]
(Instrumental)
[Stop]
```

> 注意：此例 Lyrics 共 15 段，因为 `Interlude 2` 给了两个方案（Synth Dance / Bluesy Guitar Solo）——同一段落的两种选项，段数因此多一个，属正常设计，非结构错误。
