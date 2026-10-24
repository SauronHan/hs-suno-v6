# Suno v6 官方标准音乐与影视配乐提示词指南 (Suno v6 Prompt Engineering Guide)

本手册是 `hs-suno-v6` 的垂直技术指南，专为将音乐创意、戏剧功能与影视配乐意图精准编译为 **Suno v6 家族（v6, v6-wild, v6-mini）** 工业级高命中率生成指令。

---

## 一、 Suno v6 平台架构与模型选择决策

Suno 平台于 2026 年全面退役旧版（v4.5 / v5 等），全面转向 **v6 原生架构**。单次最长支持生成达 **8 分钟**，支持多模态参考与精细自然语言微创编辑。

| 模型型号 | 定位与核心优势 | 生产级实战建议 |
| :--- | :--- | :--- |
| **Suno v6** | **旗舰基线**：高稳定性、精准编曲编排、声场饱满、人声极度自然 | 影视长镜头 BGM 交付、商业流行单曲、需要精准掌控起承转合的场景 |
| **Suno v6-wild** | **先锋探索**：更具冒险精神与纹理质感、出人意料的流派融合（Fusion） | 实验性配乐、前卫电子、暗黑异质氛围、跨流派混搭 |
| **Suno v6-mini** | **极速草稿**：极低延迟、轻量快速生成 | 旋律旋法快速摸底、BPM 节奏初测、前置灵感测试 |

---

## 二、 Suno 输入结构与字符权重法则

Suno 提示词主要由两大输入框协同控制：

1. **Style of Music（风格提示词框）**：
   - 决定曲风流派、时代背景、核心配器、制作质感与主观情绪。
   - **黄金长度法则**：控制在 **100–140 字符**以内最为高效；过长会导致关键乐器权重被稀释，过短则模型自由度过高导致失控。
   - **严禁叙事散文**：绝不可写散文句子（如“一个孤独的老人在雨夜流泪”），必须采用逗号分隔的具象标签化语法。
2. **Lyrics / Prompt（歌词与曲式结构框）**：
   - **纯器乐模式 (Instrumental Toggle = ON)**：填入以方括号 `[...]` 标记的**曲式动态演进指令**。
   - **人声歌曲模式 (Instrumental Toggle = OFF)**：填入结构化排版的歌词，并内嵌演唱情绪、声学转折元标签。
3. **Exclude Styles（负向风格排除框）**：
   - 填入与当前目标冲突的流派、乐器与制作特征（如：`happy, EDM, autotune, heavy metal, noisy drums`）。

---

## 三、 风格提示词 (Style of Music) 核心矩阵

编写 Style 标签严格遵循通用六元组公式：
$$\text{主流派} + \text{时代/子流派} + \text{核心主导乐器} + \text{情绪基调} + \text{速度与律动(BPM)} + \text{声学空间与制作质感}$$

### 1. 核心流派词库 (Genre)
- **影视与现代古典**：`Cinematic soundtrack`, `Neo-classical`, `Dark ambient`, `Orchestral thriller`, `Epic hybrid trailer`, `Folk noir`
- **流行与节奏蓝调**：`Contemporary R&B`, `Synth-pop`, `Indie folk`, `Dream pop`, `K-pop`
- **电子与前卫节奏**：`Cyberpunk industrial`, `Phonk`, `Drift phonk`, `Melodic techno`, `Lo-fi hip-hop`, `Jersey club`
- **摇滚与独立**：`Post-rock`, `Shoegaze`, `Alternative rock`, `Grunge`

### 2. 乐器配置词库 (Instrumentation)
- **极简对话避让型**：`sparse solo cello`, `minimal felt piano`, `sub-bass drone`, `soft acoustic guitar`
- **张力危机型**：`pulsating analog synthesizers`, `tremolo strings`, `distorted electric guitar`, `industrial clangs`
- **宏大史诗型**：`heavy brass fanfare`, `aggressive percussion`, `cinematic taiko drums`, `soaring string section`
- **质感特效型**：`tape saturation`, `wide stereo field`, `natural room reverb`, `vinyl crackle`

---

## 四、 两大高阶编曲语法体系 (Advanced Methodologies)

### 方法 1：时序渐进箭头记法 (Progressive Arrow Notation)
利用时间戳与 `→` 箭头，精确指导 Suno 在时间轴上如何渐进演变、乐器何时进入与退出，特别适用于 **2~5 分钟的影视长镜头与情绪推进**：

```text
[0:00 Solo cello, sparse and intimate] → 
[0:20 Soft felt piano enters, subtle melodic motif] → 
[0:45 Low pulsating synth bass and tension strings swell] → 
[1:15 Full hybrid orchestra crescendo, heavy percussion and brass] → 
[2:00 Sudden silence drop, lingering solo piano notes] → 
[2:20 Slow fade out into dark ambient room tone]
```

### 方法 2：分轨分层编排记法 (The Layered Stem Method)
将提示词显式拆分为声学分轨（Stems），严格控制低频、律动、和声、旋律与空间特效：

```text
[Foundation] Sub-bass drone (40-60Hz), deep analog sub, slow pulse
[Rhythm] Sparse cinematic toms, muted rim clicks, gradual accelerating pulse
[Harmony] Minor key string pads, wide stereo warmth, dark harmonic tension
[Melody] Solo melancholic cello melody, high emotional resonance, expressive vibrato
[FX] Subtle room tone, distant metallic resonance, tape delay swells
```

---

## 五、 曲式结构元标签 (Metatags) 速查

在歌词/结构框中，必须使用以下标准化元标签引导乐曲段落：

| 元标签 | 功能与时序定义 | 影视与流行实战示例 |
| :--- | :--- | :--- |
| `[Intro]` | 前奏 / 建立空间氛围 | `[Sparse Piano Intro, distant tape hiss]` |
| `[Verse]` | 叙事展开段 / 主歌 | `[Intimate Verse, acoustic guitar and soft vocal]` |
| `[Pre-Chorus]` | 情绪爬升 / 预副歌 | `[Drums build, rising synths, tension increases]` |
| `[Chorus]` | 主题爆发 / 高潮副歌 | `[Massive Chorus, soaring melody, full instrumentation]` |
| `[Drop]` | 节奏突变点 / 能量爆发 | `[Heavy 808 sub-bass drop, punchy beat kick]` |
| `[Bridge]` | 情感转换 / 变奏对立 | `[Stripped-back Bridge, solo cello breakdown]` |
| `[Guitar Solo]` / `[Instrumental Break]` | 间奏独奏 / 器乐展示 | `[Melodic Electric Guitar Solo, crying bends]` |
| `[Outro]` | 尾奏 / 余韵减弱 | `[Slow Outro, lingering piano chord, fading strings]` |
| `[Silence]` / `[Pause]` | 戏剧性突然静音 | `[Abrupt Silence, heart-beat room tone]` |
| `[Fade Out]` | 渐弱淡出 | `[Gradual Fade Out into silence]` |
| `[End]` | 决绝断音收尾 | `[Sharp Final Hit, abrupt cutoff]` |

---

## 六、 影视配乐对白避让原则 (Dialogue-friendly Masking)

如果配乐需要铺设在包含人物对白的台词场景下方：
1. **中频让位（1kHz–4kHz）**：在风格中明确加入 `dialogue-friendly, sparse instrumentation, minimal arrangement`；
2. **规避密集碎镲与高音合成器**：Exclude 中加入 `busy hi-hats, sharp synths, screaming vocals, loud crash cymbals`；
3. **低频与高频两头铺垫**：采用极低频 Pad 与极高频柔和空气感，把中频完全腾出给演员人声台词。
