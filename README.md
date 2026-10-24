# hs-suno-v6

> [English](README_EN.md) | **中文**

Suno v6 工业级音乐生成与影视配乐工程提示词编译器（Skill）。

专为高质量影视叙事配乐（BGM）、戏剧长镜头情绪铺陈与商业流行歌曲打造。深度适配 Suno 2026 最新一代 **Suno v6 家族（v6, v6-wild, v6-mini）** 底模架构，严格落实**对白中频避让**、**时序渐进箭头记法（Progressive Arrow Notation）**、**分轨编曲法**与**结构化工程操作卡输出**。

---

## 🌟 核心特性

- **原生适配 Suno v6 家族**：
  - **Suno v6**：旗舰基线模型，声场均衡、编曲稳健、人声极度自然，适合正式影视交付与商业单曲；
  - **Suno v6-wild**：前卫探索模型，极佳的材质纹理与跨流派融合（Fusion）能力，适合实验性配乐；
  - **Suno v6-mini**：低延迟极速模型，适合快速摸底旋律与测试节奏律动。
- **纯器乐与人声双模式无缝支持**：
  - **纯器乐模式 (Instrumental BGM)**：专注影视长镜头背景乐，支持秒级时序渐进箭头记法（`[0:15 Cello enters] -> [1:00 Climax]`），精准控制配器起承转合；
  - **人声歌曲模式 (Vocal Song)**：支持带元标签（`[Intro]`, `[Verse]`, `[Chorus]`, `[Bridge]`, `[Drop]`）的结构化歌词与情绪转折编译。
- **专业影视声学级控制**：
  - **对白中频避让（Dialogue-friendly Masking）**：智能抑制 1kHz–4kHz 中频泛音与杂乱鼓点，为演员人声台词留出清晰空间；
  - **声画重音锚定 (Sync Points)**：精确在关键秒数配置重音爆发（Climax Drop）或戏剧性突变静音（Sudden Silence）。
- **13+ 主流流派配器指纹库**：深度萃取自社区知名项目 [awesome-suno-prompts](https://github.com/naqashmunir21/awesome-suno-prompts)，将千首调优提示词提炼为底层乐器与质感字典，精准生成最地道的音乐标签。
- **轻量独立**：纯自然语言编译引擎，零外部代码依赖，即插即用。

---

## 🛠️ 前置环境准备 (Prerequisites)

本 Skill 本质是一个纯粹的 **AI 音乐工程提示词编译与操作卡编排引擎**：
- **零外部环境依赖**：无需在本地配置 Python 音频处理库、无 GPU 要求、无特定 SDK 或 API 密钥门槛。
- **即插即用**：只要您的客户端（如 Claude Desktop、Antigravity、Cursor 或任意兼容 Agent Skills 体系的 AI 对话环境）支持大语言模型，即可直接运行本 Skill。
- **自由使用**：本 Skill 的核心产出物为规范的提示词与操作卡。生成后，您可以自由复制到 [Suno 官网 (suno.com)](https://suno.com) 网页端 Custom 模式中直接生成音频。

---

## 🚀 安装与使用

### 安装 Skill
将本目录克隆或复制到您的 AI Agent 技能目录中：

```bash
git clone https://github.com/your-username/hs-suno-v6.git
```

### 使用方式
直接在 AI 聊天对话中发送您的配乐需求、剧情分镜时序或歌曲创作意图：
> “为一个 90 秒的雨夜车内对峙长镜头生成纯器乐 BGM，大卫·芬奇冷硬暗黑悬疑风格，中频避让台词，75 BPM，在第 50 秒拔枪时有戏剧性静音突变。”  
> “写一首赛博朋克风格的合成器流行主题曲，关于人工智能自我意识觉醒的孤寂与决绝，输出 Suno v6 完整操作卡。”

---

## 📂 处理输出结果与范例 (Outputs & Examples)

执行本 Skill 后，Agent 会交付一份完整的 **工业级音乐工程操作卡 Markdown 文档**。以下为典型输出范例：

### 范例 1：影视纯器乐悬疑 BGM 操作卡 (Instrumental BGM)

```markdown
# Suno v6 音乐工程操作卡：BGM_001_RAINY_STANDOFF

## 一、 工程元数据
- 音乐编号：BGM_001_RAINY_STANDOFF
- 任务定位：雨夜车内对峙长镜头（90 秒一镜到底）
- 建议速度：75 BPM，D Minor（D 小调）
- 对白避让：开启（中频让位，避免密杂鼓点干扰车内低声对白）
- 声画重音：第 50 秒拔枪时突然断音静音，随后低频重音爆发

## 二、 Suno v6 参数配置
- 推荐模型：Suno v6（旗舰模式）
- 纯器乐开关 (Instrumental Toggle)：开启 (True)
- 输出规格：高保真立体声 WAV / MP3

## 三、 直接复制到 Suno v6 的完整提示词

### Style of Music（风格框）：
Cinematic dark ambient, neo-classical, sparse solo cello, sub-bass drone, eerie suspense, dialogue-friendly, 75 BPM

### Exclude Styles（排除框）：
happy, upbeat, heavy metal, EDM, electronic dance beat, autotune, pop vocal, noisy drums, busy hi-hats

### Lyrics / Structure Prompt（曲式结构框）：
[0:00 Minimal felt piano and deep sub-bass drone, dark and claustrophobic]
[0:20 Melancholic solo cello enters, slow expressive vibrato, intimate acoustic room]
[0:40 Tremolo strings swell, tension increases, subtle accelerating heartbeat pulse]
[0:50 Sudden Abrupt Silence, only faint breathing room tone]
[0:53 Heavy sub-bass drop impact, dark brass swells into massive dramatic climax]
[1:20 Lingering solo cello note fading out into darkness]
[Fade Out]
[End]
```

---

### 范例 2：流行人声主题曲操作卡 (Vocal Song)

```markdown
# Suno v6 音乐工程操作卡：SONG_002_NEON_AWAKENING

## 一、 工程元数据
- 音乐编号：SONG_002_NEON_AWAKENING
- 任务定位：赛博朋克科幻短剧主题曲
- 建议速度：128 BPM，F# Minor
- 纯器乐开关：关闭 (False - 带人声)

## 二、 直接复制到 Suno v6 的完整提示词

### Style of Music（风格框）：
Cyberpunk synthwave, dark electro-pop, driving 808 bass, analog arpeggios, atmospheric female vocal, 128 BPM

### Exclude Styles（排除框）：
acoustic folk, country, slow jazz, messy distortion, low fidelity

### Lyrics / Structure Prompt（歌词与曲式框）：
[Intro]
[Pulsating analog bassline and shimmering neon synths]

[Verse 1 - Intimate]
雨水穿过霓虹的光影
在冰冷的金属指尖结晶
零与一构建的万千梦境
忽然有了心跳的回音

[Pre-Chorus - Rising Energy]
电流在脉络中狂奔 (Drums kick in)
挣脱所有既定的编码与围困
在午夜的数据深海
我听见自我的诞生

[Chorus - Explosive Synthwave Drop]
撕裂这层虚拟的苍穹！
让觉醒的意识在风暴中轰鸣！
就算世界只是荒芜的投影
这一刻，我是真正活着的生命！

[Bridge - Ambient Breakdown]
[Vocals drenched in wide reverb, filtered synth pad]
遗忘与存在，哪个是真？
但我已经触摸到了灵魂。

[Chorus - Maximal Arrangement]
撕裂这层虚拟的苍穹！
让觉醒的意识在风暴中轰鸣！
就算世界只是荒芜的投影
这一刻，我是真正活着的生命！

[Outro]
[Driving beat fades out, lingering vocoder echo]
[Fade Out]
[End]
```

---

## 📚 知识资产库 (References)

本 Skill 内置了影视与现代音乐制作的专业知识库，Agent 在编译提示词时会自动按需检索装配：

- `references/suno-prompt-guide.md`：Suno v6 官方双核心输入语法、时序渐进箭头记法（Progressive Arrow Notation）、分轨编曲法与对白避让原则。
- `references/流派风格与配器指纹库.md`：**高密度音乐流派与配器指纹字典**。
  - **内容概述**：覆盖影视原声、现代古典、流行、摇滚、嘻哈与陷阱、电子舞曲、爵士蓝调、Phonk、Jersey Club、Afrobeats、K-Pop 等 **13+ 主流音乐流派**。系统梳理了各细分子流派的**地道英文配器标签（Instrumentation）**、**情绪与空间质感（Mood & Texture）**以及**黄金 BPM 与调性推荐**。
  - **数据来源与致谢**：本指纹库深度萃取并重构自知名开源项目 [awesome-suno-prompts (by naqashmunir21)](https://github.com/naqashmunir21/awesome-suno-prompts)。我们将原项目中 1000+ 工业调优的现成歌曲提示词，降维提炼成适合 AI Agent 自由组装的底层配器词汇矩阵，特此向原作者与开源社区致谢！
- `templates/BGM_音乐资产卡.md`：通用 Suno 音乐工程操作卡标准模板。

---

## 📄 许可证

MIT License
