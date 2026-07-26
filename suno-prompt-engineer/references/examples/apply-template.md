# 范例：套用现有模板 / 翻唱（最浪漫的事）

## 任务

用甜妹舞曲风格翻唱赵咏华《最浪漫的事》。

## 用户需求输入（无序号段落歌词 + 风格诉求）

```text
用甜妹舞曲风格翻唱赵咏华《最浪漫的事》

[Intro]

[Verse]
背靠着背坐在地毯上
听听音乐聊聊愿望
你希望我越来越温柔
我希望你放我在心上

[Verse]
你说想送我个浪漫的梦想
谢谢我带你找到天堂
哪怕用一辈子才能完成
只要我讲你就记住不忘

[Chorus]
我能想到最浪漫的事
就是和你一起慢慢变老
一路上收藏点点滴滴的欢笑
留到以后坐着摇椅慢慢聊
我能想到最浪漫的事
就是和你一起慢慢变老
直到我们老的哪儿也去不了
你还依然把我当成手心里的宝

[Interlude]

[Verse]
背靠着背坐在地毯上
听听音乐聊聊愿望
你希望我越来越温柔
我希望你放我在心上

[Verse]
你说想送我个浪漫的梦想
谢谢我带你找到天堂
哪怕用一辈子才能完成
只要我讲你就记住不忘

[Chorus]
我能想到最浪漫的事
就是和你一起慢慢变老
一路上收藏点点滴滴的欢笑
留到以后坐着摇椅慢慢聊
我能想到最浪漫的事
就是和你一起慢慢变老
直到我们老的哪儿也去不了
你还依然把我当成手心里的宝

[Chorus]
我能想到最浪漫的事
就是和你一起慢慢变老
一路上收藏点点滴滴的欢笑
留到以后坐着摇椅慢慢聊
我能想到最浪漫的事
就是和你一起慢慢变老
直到我们老的哪儿也去不了
你还依然把我当成手心里的宝

[Outro]
```

> 用户输入用**无序号段落**（`[Verse]`/`[Chorus]`），这是工作流 B 的典型输入形态。

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

### Lyrics（无序号 → 有序号转换）

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
背靠着背坐在地毯上
听听音乐聊聊愿望
你希望我越来越温柔
我希望你放我在心上

[Verse 2: Driving Rhythm]
[Lead-Vocals: Dynamic rhythmic phrasing, slightly warmer tone]
[Instrument: Full driving dance pop groove established, crisp claps added]
[Dynamics: mp -> mf, walking forward]
你说想送我个浪漫的梦想
谢谢我带你找到天堂
哪怕用一辈子才能完成
只要我讲你就记住不忘

[Chorus 1: Explosive Bright]
[Lead-Vocals: Energetic power belting, sweet and resonant, double-tracked]
[Backing-Vocals: Lush multi-layered harmonies, playful backing vocals]
[Instrument: Wide stereo shimmery synthesizers, driving punchy drums, four-on-the-floor kick]
[Texture: Dense sweet pop wall of sound]
[Dynamics: ff, energetic release]
我能想到最浪漫的事
就是和你一起慢慢变老
一路上收藏点点滴滴的欢笑
留到以后坐着摇椅慢慢聊
我能想到最浪漫的事
就是和你一起慢慢变老
直到我们老的哪儿也去不了
你还依然把我当成手心里的宝

[Interlude: Playful Break]
[Instrument: Shimmery synth lead melody over bouncy bassline and crisp claps]
[Dynamics: mf, jumping rhythm]
(Instrumental)

[Verse 3: Stripped Back]
[Lead-Vocals: Playful narrative, intimate breathy delivery, crisp articulation]
[Instrument: Stripped back. Bouncy bassline, crisp snare cross-stick, acoustic guitar accents only]
[Texture: Sudden drop to sparse]
[Dynamics: mp, deep groove]
背靠着背坐在地毯上
听听音乐聊聊愿望
你希望我越来越温柔
我希望你放我在心上

[Verse 4: Rhythm Return]
[Lead-Vocals: Bouncy phrasing, rising anticipation]
[Instrument: Full punchy upbeat drums return, bright synthesizers sweep in]
[Dynamics: mp -> mf, driving momentum]
你说想送我个浪漫的梦想
谢谢我带你找到天堂
哪怕用一辈子才能完成
只要我讲你就记住不忘

[Chorus 2: Explosive Bright]
[Lead-Vocals: Energetic belting, soaring high notes, double-tracked]
[Backing-Vocals: Thick vocal pad, rich stacked harmonies, playful vocal responses]
[Instrument: Maximum wide synths, heavy driving dance pop groove, bright acoustic guitar]
[Texture: Massive bright pop wall of sound]
[Dynamics: ff, uplifting release]
我能想到最浪漫的事
就是和你一起慢慢变老
一路上收藏点点滴滴的欢笑
留到以后坐着摇椅慢慢聊
我能想到最浪漫的事
就是和你一起慢慢变老
直到我们老的哪儿也去不了
你还依然把我当成手心里的宝

[Grand Chorus: Epic Finale]
[Lead-Vocals: Ultimate energetic delivery, sweet soaring ad-libs, double-tracked lead]
[Backing-Vocals: Maximum lush layered harmonies, intricate counter-melodies]
[Instrument: Full band explosion, maximum shimmery synthesizers, heavy four-on-the-floor beat]
[Dynamics: fff, stadium pop energy]
我能想到最浪漫的事
就是和你一起慢慢变老
一路上收藏点点滴滴的欢笑
留到以后坐着摇椅慢慢聊
我能想到最浪漫的事
就是和你一起慢慢变老
直到我们老的哪儿也去不了
你还依然把我当成手心里的宝

[Outro: Fading Groove]
[Arrangement: Smooth dance pop fade]
[Lead-Vocals: Playful fading ad-libs, echoing vocal delay throws]
[Instrument: Bouncy bassline and upbeat drums slowly fading out]
[Dynamics: mf -> pp -> Stop]
(Instrumental)
[Stop]
```

> 设计意图：用户输入是**无序号段落**，AI 产出转换为**有序号段落**（`[Verse]`→`[Verse 1]`、`[Chorus]`→`[Chorus 1]`）。这种"不一致"是**刻意对照示范**——展示"用户给无序号、Agent 输出有序号"的转换，不是需要统一成同一套编号的 bug。
>
> 注：本例歌词为**未脱敏原词**，仅作教学展示。若实际要喂 Suno 生成，需按需脱敏以规避版权校验。
