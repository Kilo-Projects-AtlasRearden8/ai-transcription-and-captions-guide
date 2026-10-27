# Chapter 12: Export Formats Explained

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## Choosing the Right Format

Different formats serve different purposes. This chapter helps you pick.

---

## Format Comparison Table

| Format | Extension | Timestamps | Speaker Labels | Best For |
|---|---|---|---|---|
| **TXT** | `.txt` | No | Optional | Reading, printing, notes |
| **MD** | `.md` | Optional | Optional | Documents, websites, GitHub |
| **SRT** | `.srt` | Yes | No | Video captions, YouTube, VLC |
| **VTT** | `.vtt` | Yes | No | Web video (HTML5) |
| **DOCX** | `.docx` | No | Optional | Word documents, sharing |
| **PDF** | `.pdf` | No | Optional | Fixed-layout sharing |
| **JSON** | `.json` | Yes | Yes | Developers, data processing |
| **CSV** | `.csv` | Yes | Yes | Spreadsheets, analysis |

---

## Format Details

### TXT — Plain Text

```
Good morning everyone. Today we'll cover three topics.

First, we'll review the budget.
Second, we'll discuss the timeline.
Third, we'll assign action items.
```

- **Pros:** Opens everywhere, smallest file, easy to edit
- **Cons:** No timestamps, no formatting
- **Best for:** Reading, study notes, quick reference

### MD — Markdown

```markdown
# Meeting Transcript

## Speakers
- Sarah (Manager)
- Mike (Developer)

## Transcript

[00:00] **Sarah:** Good morning, everyone.

[00:15] **Mike:** Good morning. Ready to begin?
```

- **Pros:** Readable plain text, formatting (headers, bold, lists), works on GitHub
- **Cons:** Slight learning curve for syntax
- **Best for:** Documentation, blogs, version-controlled documents

### SRT — SubRip Subtitle

```
1
00:00:01,000 --> 00:00:04,000
Good morning everyone.

2
00:00:04,000 --> 00:00:07,000
Today we'll cover three topics.
```

- **Pros:** Universal caption format, works in YouTube/VLC/players
- **Cons:** Text only, limited formatting
- **Best for:** Video captions, subtitles

### VTT — WebVTT

```
WEBVTT

00:00:01.000 --> 00:00:04.000
Good morning everyone.

00:00:04.000 --> 00:00:07.000
Today we'll cover three topics.
```

- **Pros:** Web standard, supports positioning and styling
- **Cons:** Less support in desktop video players
- **Best for:** HTML5 video on websites

### JSON — Structured Data

```json
{
  "segments": [
    {
      "start": 0.0,
      "end": 4.0,
      "text": "Good morning everyone.",
      "speaker": "Speaker 1",
      "confidence": 0.95
    }
  ]
}
```

- **Pros:** Complete data (timestamps, speakers, confidence), machine-readable
- **Cons:** Hard to read as text, needs programming to use
- **Best for:** Developers, custom tools, data analysis

### DOCX / PDF — Documents

- **Pros:** Professional formatting, easy to share, printable
- **Cons:** Larger files, harder to edit programmatically
- **Best for:** Sharing with clients, printing, formal records

---

## Quick Decision Guide

| Your Goal | Recommended Format |
|---|---|
| Read on your phone | TXT or MD |
| Add captions to video | SRT |
| Put on a website | VTT |
| Share with a team | DOCX or PDF |
| Analyze with code | JSON |
| Import to spreadsheet | CSV |
| Publish on GitHub | MD |
| Study notes | TXT or MD |

---

## Converting Between Formats

### SRT to TXT (Remove Timestamps)

```bash
# Using sed (Mac/Linux)
grep -v '^[0-9]*$' lecture.srt | grep -v '-->' | grep -v '^$' > lecture.txt

# Or just open in a text editor and copy the text portions
```

### TXT to MD (Add Headers)

Open your TXT file, add `# Title` at the top, save as `.md`.

### Multiple Formats from Whisper

faster-whisper can output multiple formats at once:

```bash
python -m faster_whisper transcribe audio.mp3 \
  --model base \
  --output_format srt,txt,json \
  --output_dir ./output
```

This creates `audio.srt`, `audio.txt`, and `audio.json` in one run.

---

## Try It: Export in Three Formats

1. Take any transcript you've created
2. Save it as:
   - `transcript.txt` (plain text)
   - `transcript.md` (add a title header `#`)
   - `transcript.srt` (if you have timestamps, or create SRT from Whisper)
3. Open each file and notice the differences
4. Decide which format you'll use for your project

---

## Key Takeaways

1. **TXT** = simplest, works everywhere
2. **SRT** = video captions, universal player support
3. **MD** = formatted, GitHub-friendly, good for documentation
4. **JSON** = for developers and data tools
5. **Whisper outputs multiple formats at once** — use `--output_format srt,txt,json`

---

## Next: [Chapter 13 — Quick Reference Card](13-quick-reference.md)

*One-page cheat sheet for common tasks.*