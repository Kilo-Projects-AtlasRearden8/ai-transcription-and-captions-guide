# Chapter 4: Local Options (Run on Your Computer)

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## What "Local" Means

The AI runs entirely on your computer. Your audio never leaves your device. No internet needed after setup.

**Pros:**
- Total privacy — audio never leaves your computer
- No accounts, no API keys, no monthly limits
- Works offline
- Free forever (open-source models)

**Cons:**
- Needs a decent computer (see system requirements below)
- Setup takes 10–30 minutes
- Accuracy may be slightly lower than top cloud models
- Large model downloads (1–5 GB)

---

## System Requirements

| Component | Minimum | Recommended |
|---|---|---|
| RAM | 8 GB | 16 GB |
| Storage | 10 GB free | 20 GB free |
| CPU | Any modern (Intel/AMD/Apple Silicon) | Multi-core |
| GPU | Optional | NVIDIA with 4–8 GB VRAM (much faster) |
| OS | Windows 10+, macOS 10.15+, Linux | Any |

**No GPU? No problem.** Whisper runs on CPU — it's just 2–5x slower.

---

## The Two Best Local Tools

### Option A: Whisper (via faster-whisper) — Recommended

OpenAI's Whisper is the gold standard for free local transcription. `faster-whisper` is a optimized version that runs 4–8x faster.

**Best for:** Most people. Accurate, multilingual, actively maintained.

#### Install (Windows, Mac, Linux)

**Prerequisites:** Install [Python](https://python.org) (3.8+)

```bash
# Open Terminal (Mac/Linux) or Command Prompt/PowerShell (Windows)
pip install faster-whisper
```

#### Transcribe a File

```bash
# Basic transcription
python -m faster_whisper transcribe meeting.mp3 --model base --output_dir ./output

# Model sizes: tiny, base, small, medium, large-v3
# Larger = more accurate, slower, bigger download
```

#### Common Commands

```bash
# Fast, good enough for most English
python -m faster_whisper transcribe audio.mp3 --model base --output_format txt

# More accurate, still fast
python -m faster_whisper transcribe audio.mp3 --model small --output_format srt

# Best accuracy (slower, bigger download)
python -m faster_whisper transcribe audio.mp3 --model medium --output_format vtt

# Spanish audio
python -m faster_whisper transcribe audio.mp3 --model base --language es --output_format txt
```

**Output files:** `audio.txt`, `audio.srt`, `audio.vtt`, `audio.json` (in `./output`)

---

### Option B: Whisper.cpp — Fastest on CPU

A C++ implementation of Whisper. Very fast, no Python needed.

**Best for:** Older computers, maximum speed, no Python.

#### Install

**Mac (Homebrew):**
```bash
brew install whisper.cpp
```

**Windows / Linux:** Download from [github.com/ggerganov/whisper.cpp](https://github.com/ggerganov/whisper.cpp) — see releases for prebuilt binaries, or compile from source.

#### Use

```bash
whisper-cli -m models/ggml-base.en.bin -f meeting.wav -of output
```

Models: `tiny.en`, `base.en`, `small.en`, `medium.en` (English-only, smaller) or multilingual variants.

---

### Option C: Vosk — Lightweight, Offline, Mobile-Friendly

Small models (50 MB), runs on anything including Raspberry Pi.

**Best for:** Low-end computers, continuous streaming, embedded devices.

**Trade-off:** Lower accuracy than Whisper, English-focused models are best.

Download from [alphacephei.com/vosk](https://alphacephei.com/vosk/models)

---

## Model Sizes Explained

| Model | Size | Speed | Accuracy | Best For |
|---|---|---|---|---|
| tiny | ~1 GB | Fastest | Good | Quick drafts, old computers |
| base | ~1 GB | Fast | Good | General use (recommended start) |
| small | ~2 GB | Medium | Better | Meetings, lectures |
| medium | ~5 GB | Slower | Better still | Important content |
| large-v3 | ~3 GB | Slowest | Best | Maximum accuracy |

*English-only models (`.en`) are smaller and faster than multilingual.*

---

## Step-by-Step: Transcribe a Lecture Locally

### Scenario: You recorded a 45-minute lecture on your phone

**Step 1: Transfer the file to your computer**
- Connect phone via USB, or email the file to yourself
- Save as `lecture.mp3` or `lecture.m4a`

**Step 2: Install faster-whisper**
```bash
pip install faster-whisper
```

**Step 3: Transcribe**
```bash
python -m faster_whisper transcribe lecture.mp3 --model base --output_format srt --output_dir ./transcripts
```

**Step 4: Wait**
- CPU: ~5–10 minutes per hour of audio
- GPU: ~1–2 minutes per hour of audio

**Step 5: Open the result**
- `transcripts/lecture.srt` — captions with timestamps
- `transcripts/lecture.txt` — plain text transcript

---

## Converting Audio Formats

Whisper accepts: MP3, WAV, M4A, OGG, FLAC, and most video formats.

If you have an unsupported format, convert with [ffmpeg](https://ffmpeg.org):

```bash
# Convert any audio to WAV (16 kHz mono — ideal for ASR)
ffmpeg -i input.m4a -ar 16000 -ac 1 output.wav

# Extract audio from video
ffmpeg -i lecture.mp4 -vn -ar 16000 -ac 1 lecture.wav
```

Install ffmpeg:
- Mac: `brew install ffmpeg`
- Windows: [ffmpeg.org/download.html](https://ffmpeg.org/download.html)
- Linux: `sudo apt install ffmpeg`

---

## Privacy Checklist for Local Tools

- [ ] No account required
- [ ] No API key needed
- [ ] No internet needed after model download
- [ ] Audio never leaves your computer
- [ ] Model files stay on your disk

✅ **Local = safest option for sensitive audio.**

---

## Troubleshooting Local Installation

| Problem | Fix |
|---|---|
| `pip: command not found` | Install Python from python.org, check "Add to PATH" |
| `ModuleNotFoundError` | Run `pip install faster-whisper` again |
| Out of memory | Use `tiny` or `base` model; close other apps |
| Very slow | Use `base` model; CPU is normal — try `small` only if patient |
| Model download fails | Check internet; models download from Hugging Face automatically |
| File not found | Use full path: `~/Downloads/lecture.mp3` |

---

## Try It: Transcribe a 1-Minute Clip

1. Record 1 minute of yourself speaking on your phone
2. Transfer to computer as `test.mp3`
3. Run: `pip install faster-whisper`
4. Run: `python -m faster_whisper transcribe test.mp3 --model tiny --output_format txt`
5. Open `test.txt` — your first local transcript

---

## Key Takeaways

1. **Local = private** — audio never leaves your computer
2. **faster-whisper** is the best starting point (Python, accurate, fast)
3. **Start with `base` model** — good balance of speed and accuracy
4. **No GPU needed** — CPU works, just slower
5. **ffmpeg** converts any audio/video to Whisper-friendly format

---

## Next: [Chapter 5 — Comparison: Which Should You Use?](05-comparison.md)

*Decision framework: cloud vs local, by scenario.*