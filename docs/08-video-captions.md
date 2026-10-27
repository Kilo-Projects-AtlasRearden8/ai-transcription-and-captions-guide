# Chapter 8: Adding Captions to a Video

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## Why Captions Matter

- **Accessibility:** Deaf and hard-of-hearing viewers
- **Comprehension:** Non-native speakers, noisy environments
- **SEO:** Search engines can index caption text
- **Engagement:** Many people watch videos on mute

Captions = text file + timing information, displayed alongside the video.

---

## Caption Formats Explained

| Format | Extension | Best For | Notes |
|---|---|---|---|
| **SRT** | `.srt` | Most video players, YouTube | Most widely supported |
| **VTT** | `.vtt` | Web video (HTML5 `<track>`) | Web standard, supports styling |
| **TXT** | `.txt` | Reading, editing | No timestamps — not for captions |

**Recommendation:** Create SRT. It works everywhere.

---

## SRT Format Explained

An SRT file is plain text with numbered entries:

```
1
00:00:01,000 --> 00:00:04,000
Welcome to the presentation.

2
00:00:04,000 --> 00:00:07,000
Today we'll cover three main topics.
```

Each entry:
1. Sequence number
2. Start time → End time (`hours:minutes:seconds,milliseconds`)
3. Caption text (1–2 lines)
4. Blank line separator

---

## Step-by-Step: Create Captions from a Transcript

### Method A: From Local Transcription (Whisper SRT Output)

If you used faster-whisper with `--output_format srt`, you already have an `.srt` file:

```
transcripts/lecture.srt
```

Skip to "Add Captions to Your Video" below.

### Method B: From Plain Text (Manual Timing)

If you only have a plain text transcript, you'll need to add timestamps:

1. Open your text transcript
2. Play the video and note when each sentence starts/ends
3. Create SRT entries manually (time-consuming for long videos)

**Better:** Use Whisper locally (Chapter 4 or 7) to generate SRT automatically.

---

## Step-by-Step: Add Captions to Your Video

### Option 1: YouTube (Easiest)

1. Upload your video to YouTube Studio
2. In **Subtitles**, click **Add Language** → select your language
3. Choose **Upload file** → upload your `.srt` or `.vtt`
4. Review and publish

Viewers can now toggle captions with the CC button.

### Option 2: VLC Media Player (Local Playback)

1. Place your video and `.srt` file in the same folder
2. Name them identically: `lecture.mp4` + `lecture.srt`
3. Open the video in VLC
4. Captions appear automatically (or click **Subtitle → Sub Track**)

### Option 3: HTML5 Video (Websites)

```html
<video width="640" height="360" controls>
  <source src="lecture.mp4" type="video/mp4">
  <track src="lecture.vtt" kind="captions" srclang="en" label="English">
</video>
```

The `track` element links the VTT caption file to the video.

### Option 4: Burn Captions Into the Video (Permanent)

Use ffmpeg to hardcode captions:

```bash
ffmpeg -i lecture.mp4 -vf "subtitles=lecture.srt" lecture-with-captions.mp4
```

Captions are always visible — no toggle needed.

---

## Editing Captions

Captions should be readable:
- **1–2 lines per caption**
- **Maximum 32–42 characters per line**
- **Display time: 1.5–7 seconds per caption**
- **Break at natural pauses** (commas, periods, sentence ends)

Tools for editing SRT:
- **Subtitle Edit** (free, Windows) — [github.com/SubtitleEdit/subtitleedit](https://github.com/SubtitleEdit/subtitleedit)
- **Aegisub** (free, cross-platform) — [aegisub.org](https://www.aegisub.org)
- **Any text editor** — SRT is plain text

---

## Try It: Add Captions to a Short Video

1. Take a short video (30–60 seconds) you own
2. Transcribe it locally with faster-whisper (Chapter 4):
   ```
   python -m faster_whisper transcribe video.mp4 --model tiny --output_format srt
   ```
3. Rename the `.srt` file to match your video exactly
4. Open both in VLC — captions appear
5. Upload to YouTube Studio and add the SRT as subtitles (optional)

---

## Key Takeaways

1. **SRT is the universal caption format** — works in YouTube, VLC, HTML5
2. **Whisper generates SRT automatically** — no manual timing needed
3. **VLC plays SRT automatically** if filename matches the video
4. **HTML5 `<track>`** adds captions to web videos
5. **ffmpeg burns captions in** for permanent, always-visible captions

---

## Next: [Chapter 9 — Editing and Cleaning Transcripts](09-editing.md)

*Fix errors, format for readability, prepare for export.*