# Suno v6 音乐工程操作卡：[MUSIC_ID / 音乐标题]

## 一、 工程元数据

- **音乐编号**：[如：BGM_001_DARK_SUSPENSE / SONG_001_THEME]
- **任务定位**：[影视叙事长镜头 BGM / 商业广告背景乐 / 游戏场景配乐 / 流行人声主题曲]
- **目标时长**：约 [预计秒数/分钟]
- **建议节奏与调性**：[如：75 BPM，D Minor（D 小调）]
- **人声对白避让**：[是：中频让位，极简配器 / 否：纯动作戏或单曲，全频段满载]
- **声画重音锚点 (Sync Points)**：
  - 约第 [xx] 秒：[画面重大转折或情节爆发，音乐在此处出现重音或静音突变]

---

## 二、 Suno v6 平台参数配置

- **推荐模型**：`Suno v6`（旗舰默认推荐）/ `Suno v6-wild`（前卫探索）/ `Suno v6-mini`（快速草稿）
- **纯器乐模式 (Instrumental Toggle)**：`开启 (True)` / `关闭 (False - 带人声)`
- **输出音质规格**：高保真立体声 WAV / MP3

---

## 三、 直接复制到 Suno v6 的完整提示词

### 1. Style of Music（风格提示词框）
```text
[填入精炼的风格标签：流派, 时代子流派, 核心乐器, 情绪氛围, BPM, 制作质感。建议控制在 100–140 字符]
示例：
Cinematic dark ambient, neo-classical, sparse solo cello, felt piano, pulsating sub-bass, eerie suspense, dialogue-friendly, 75 BPM
```

### 2. Exclude Styles（负向排除框）
```text
[填入冲突标签。示例：]
happy, upbeat, heavy metal, EDM, electronic dance beat, autotune, pop vocal, noisy drums, harsh high-end
```

### 3. Lyrics / Structure Prompt（曲式结构与动态演进框）

#### 纯器乐长镜头模式示例（使用时序渐进箭头记法）：
```text
[0:00 Sparse felt piano and low atmospheric drone, intimate and lonely]
[0:20 Melancholic solo cello enters, slow expressive vibrato]
[0:45 Tremolo strings and pulsating sub-bass swell, tension builds]
[1:15 Full hybrid orchestral crescendo, heavy brass and driving percussion climax]
[1:50 Sudden silence drop, only low room tone and heartbeat pulse]
[2:10 Lingering piano notes fading out into darkness]
[End]
```

#### 人声歌曲模式示例（使用结构化歌词与声学元标签）：
```text
[Intro]
[Sparse acoustic guitar and soft ambient pad]

[Verse 1 - Intimate]
雨水打湿斑驳窗台
时间停在离开那一秒钟
城市的霓虹慢慢晕开
影子在长街尽头消融

[Pre-Chorus - Rising Tension]
心跳逐渐加速 (Drums enter)
风声穿透这层迷雾
在记忆破晓的深处
我听见未来的呼唤

[Chorus - Massive Emotional Climax]
穿越这片沉睡的荒原
让所有的呐喊化作烈焰
就算终点遥远而破碎
我也绝不后退，绝不妥协！

[Bridge - Stripped-back Piano]
如果黑夜终将过去
你会不会还在这里？

[Guitar Solo - Emotional and Soaring]

[Chorus - Final Maximal Arrangement]
穿越这片沉睡的荒原
让所有的呐喊化作烈焰
就算终点遥远而破碎
我也绝不后退，绝不妥协！

[Outro - Fading Acoustic]
在光芒落下的地方
[Fade Out]
[End]
```

---

## 四、 媒体成果与验收

- **实际生成音频文件**：`[输出路径]/[文件名]_v001.wav`
- **实际生成音频时长**：[mm:ss]
- **生成所用模型**：Suno v6 / v6-wild
- **试听评估**：
  - [ ] 旋律与节奏是否符合场景预期
  - [ ] 动态爆发与声画转折点是否精确契合
  - [ ] 是否存在突兀的人声杂音或电子破音
