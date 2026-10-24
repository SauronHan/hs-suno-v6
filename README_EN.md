# hs-suno-v6

> **English** | [中文](README.md)

**Suno v6 Industrial Music Generation & Film Scoring Prompt Compiler (Agent Skill)**

Engineered for high-impact cinematic scoring (BGM), long-take emotional pacing, commercial trailer cues, and structured pop production. Natively tuned for Suno's **Suno v6 model family (v6, v6-wild, v6-mini)**, strictly implementing **dialogue mid-frequency ducking**, **Progressive Arrow Notation (PAN)**, **multitrack arrangement rules**, and **structured production task cards**.

---

## 🌟 Key Features

- **Native Suno v6 Family Architecture**:
  - **Suno v6**: Balanced soundstage, pristine arrangement, natural vocals; ideal for formal film cues and commercial singles.
  - **Suno v6-wild**: Avant-garde textures and genre fusion; ideal for experimental and psychological thriller scoring.
  - **Suno v6-mini**: Ultra-low latency draft model for rapid motif and tempo prototyping.
- **Dual Operational Modes**:
  - **Instrumental BGM Mode**: Second-by-second progressive cue notations (`[0:15 Cello enters] -> [1:00 Climax Drop]`) controlling thematic orchestration.
  - **Vocal Song Mode**: Metatagged song structuring (`[Intro]`, `[Verse]`, `[Chorus]`, `[Bridge]`, `[Drop]`) with dynamic vocal style anchors.
- **Cinematic Acoustic Principles**:
  - **Dialogue Mid-Frequency Ducking**: Intelligently suppresses conflicting 1kHz–4kHz overtones and harsh percussion, preserving headroom for spoken actor dialogue.
  - **Audio-Visual Sync Points**: Anchors orchestral hits, riser climaxes, and sudden dramatic silences (`[Sudden Cut to Silence]`) to specific scene timestamps.
- **13+ Genre Orchestration Fingerprints**: Extracted from curated community datasets ([awesome-suno-prompts](https://github.com/naqashmunir21/awesome-suno-prompts)), mapping hundreds of tuned tags to genuine acoustic textures.
- **Self-Contained**: Pure prompt compilation engine with zero runtime dependencies.

---

## 🛠️ Prerequisites

This skill is a pure **Prompt Engineering & Music Sequencing Engine**:
- **Zero Local Environment Setup**: No Python audio libraries, no GPUs, and no API keys required locally.
- **Universal Deliverables**: Outputs standard Style Tags and Lyric/Structure boxes ready to be pasted into [suno.com](https://suno.com) Custom Mode.

---

## 🚀 Installation & Usage

### Installation
Clone or copy this directory into your AI Agent's skills directory:

```bash
git clone https://github.com/your-username/hs-suno-v6.git
```

### Prompting Examples
Instruct your Agent in plain language:
> *"Generate an instrumental BGM cue for a 90-second rainy night car standoff. David Fincher dark minimalist noir, 75 BPM, mid-frequency ducked for dialogue, dramatic drop to dead silence at 0:50 when a weapon is drawn."*  
> *"Write a cyberpunk synthwave theme about an AI's self-awareness awakening, melancholic yet epic, formatted for Suno v6."*

---

## 📂 Output Format & Examples

The Skill compiles a structured **Markdown Operation Card**:

```markdown
### Music Task Card: Rain Standoff (Suno v6)

- **Model**: Suno v6 (Instrumental Mode)
- **Tempo**: 75 BPM | **Time Signature**: 4/4
- **Acoustic Profile**: Dialogue-Friendly (1k-4kHz scooped)

#### 📋 Style Tags (Max 120 chars):
cinematic dark ambient, muted pizzicato cello, sub-bass pulse, brushed snare, minimalist noir, 75 bpm, tense atmosphere

#### 📝 Structure & Progressive Prompt:
[0:00-0:20] Ambient rain texture, warm sub-bass pedal note, distant muffled analog synth pad
[0:20-0:45] Staccato pizzicato cello enters, clockwork ticking percussion, building claustrophobic tension
[0:45-0:50] Sharp ascending violin riser, accelerating heartbeat pulse ->
[0:50-0:55] [Sudden Cut to Dead Silence] (Acoustic void, solo faint reverb tail for dialogue)
[0:55-1:20] Heavy orchestral brass hit, distorted sub-bass drop, slow rhythmic resolving chord
```

---

## 📄 License

Private / MIT (See repository license).
