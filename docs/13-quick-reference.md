# Chapter 13: Quick Reference Card

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## One-Page Cheat Sheet

Print this or keep it open while you work.

---

## Install Local Tools (One Time)

```bash
# Python
pip install faster-whisper

# ffmpeg (for audio conversion)
# Mac: brew install ffmpeg
# Windows: ffmpeg.org
# Linux: sudo apt install ffmpeg
```

---

## Transcribe a File (Local)

```bash
# Basic
python -m faster_whisper transcribe file.mp3 --model base

# With SRT + TXT output
python -m faster_whisper transcribe file.mp3 --model base --output_format srt,txt --output_dir ./out

# Non-English
python -m faster_whisper transcribe file.mp3 --model base --language es

# Faster (less accurate)
python -m faster_whisper transcribe file.mp3 --model tiny

# More accurate (slower)
python -m faster_whisper transcribe file.mp3 --model medium
```

**Models:** tiny < base < small < medium < large-v3

---

## Cloud Tools (No Install)

| Task | Tool | Link |
|---|---|---|
| Video captions | YouTube Studio | studio.youtube.com |
| Real-time dictation | Google Docs Voice Typing | docs.google.com |
| Speaker labels | Otter.ai | otter.ai |
| Speaker labels + API | AssemblyAI | assemblyai.com |

---

## Privacy Rules

| Content Type | Use Local? | Use Cloud? |
|---|---|---|
| Patient health info | ✅ Required | ❌ Never |
| Confidential business | ✅ Required | ❌ Never |
| Personal/financial | ✅ Required | ❌ Never |
| Public lecture | Optional | Optional |
| Your own dictation | Optional | Optional |
| Practice recording | Optional | Optional |

---

## File Formats at a Glance

| Format | Use For | Extension |
|---|---|---|
| Plain text | Reading, notes | `.txt` |
| Markdown | Docs, GitHub | `.md` |
| Video captions | YouTube, VLC | `.srt` |
| Web captions | HTML5 video | `.vtt` |
| Structured data | Code, analysis | `.json` |
| Word document | Sharing, printing | `.docx` |

---

## Common Problems & Fixes

| Problem | Fix |
|---|---|
| `pip: command not found` | Install Python from python.org |
| Model download fails | Check internet, try again |
| Out of memory | Use `--model tiny`, close apps |
| Transcription too slow | Use `--model tiny` or `base` |
| Wrong words in transcript | Edit manually (Chapter 9) |
| No speaker labels | Add manually or use cloud tool |
| Audio format error | Convert with ffmpeg to WAV |

---

## Keyboard Shortcuts (Text Editing)

- `Ctrl+F` / `Cmd+F` — Find
- `Ctrl+H` / `Cmd+Shift+H` — Find and replace
- `Ctrl+A` / `Cmd+A` — Select all
- `Ctrl+S` / `Cmd+S` — Save

---

## 5-Minute Workflow

1. Record audio
2. Transfer to computer
3. `pip install faster-whisper` (first time only)
4. `python -m faster_whisper transcribe file.mp3 --model base --output_format srt,txt`
5. Open `.txt` file, edit errors
6. Done — you have a transcript

---

## Remember

- **Local = private** (audio never leaves your computer)
- **Cloud = convenient** (no install, but audio goes to their servers)
- **Always edit** — AI isn't perfect
- **Start with `base` model** — best balance of speed and accuracy
- **Sensitive content = local only**

---

*From Asdale Dynamics, LLC — [dylanasdale.github.io](https://dylanasdale.github.io)*