# Chapter 7: Transcribing a Lecture (Local)

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## Scenario

You recorded a 50-minute university lecture on your phone. You want a searchable, editable transcript for studying. The lecture may contain course-specific terms and is for personal educational use.

**Tool:** faster-whisper (local, free, private)  
**Why local:** Lecture content is your personal study material — keep it on your computer.

---

## Step-by-Step

### Step 1: Get the Recording onto Your Computer

**From iPhone:**
- Connect via USB, use Files app to copy the recording
- Or email/AirDrop the file to yourself

**From Android:**
- Connect via USB, copy the file from the Recordings folder
- Or use Google Drive/Dropbox to transfer

**From a digital recorder:**
- Copy the file via SD card or USB

Save the file as `lecture.mp3` or `lecture.m4a` in a folder you'll remember.

---

### Step 2: Install faster-whisper (One-Time Setup)

Open Terminal (Mac/Linux) or Command Prompt/PowerShell (Windows):

```bash
# Check Python is installed
python3 --version

# Install faster-whisper
pip install faster-whisper
```

If `pip` isn't found, try `pip3` or install Python from [python.org](https://python.org).

---

### Step 3: Convert Audio (If Needed)

Whisper handles most formats, but if you get an error, convert to WAV:

```bash
# Install ffmpeg if needed (Mac: brew install ffmpeg)
ffmpeg -i lecture.m4a -ar 16000 -ac 1 lecture.wav
```

---

### Step 4: Transcribe

Navigate to your lecture folder, then run:

```bash
python -m faster_whisper transcribe lecture.mp3 \
  --model base \
  --output_format srt,txt \
  --output_dir ./transcripts
```

**Model choice:**
- `tiny` — fastest, good for old computers
- `base` — recommended start (good balance)
- `small` — better accuracy, slower
- `medium` — best accuracy, slowest

**What happens:**
1. Model downloads automatically (first time only, ~100 MB for base)
2. Audio is transcribed locally
3. Files appear in `./transcripts/`

**Expected time:** ~5–10 minutes per hour of audio on CPU

---

### Step 5: Open Your Transcript

- `transcripts/lecture.txt` — plain text, easy to read and edit
- `transcripts/lecture.srt` — captions with timestamps (good for video sync)

Open in any text editor (Notepad, TextEdit, VS Code, etc.).

---

### Step 6: Clean Up (See Chapter 9)

Lecture transcripts benefit from:
- Fixing misheard technical terms
- Adding section headers
- Removing filler words ("um," "uh")
- Adding timestamps for key topics

---

## Example: What the Output Looks Like

**lecture.txt:**
```
[00:00] Good morning everyone. Today we're going to talk about
[00:05] the fundamentals of cellular respiration.
[00:10] Cellular respiration is the process by which cells
[00:15] convert glucose into energy in the form of ATP.
...
```

**lecture.srt:**
```
1
00:00:00,000 --> 00:00:05,000
Good morning everyone. Today we're going to talk about
the fundamentals of cellular respiration.

2
00:00:05,000 --> 00:00:10,000
Cellular respiration is the process by which cells
convert glucose into energy in the form of ATP.
```

---

## Speed Tips

| Tip | Effect |
|---|---|
| Use `tiny` model | 2–3x faster, slightly less accurate |
| Close other apps | Frees RAM for transcription |
| Use GPU (NVIDIA) | 5–10x faster than CPU |
| Convert to 16 kHz mono WAV | Slightly faster processing |
| Transcribe in batches | Let it run overnight |

---

## Privacy Advantage

Because this runs locally:
- ✅ Lecture never leaves your computer
- ✅ No account, no API key, no terms of service
- ✅ No monthly minute limits
- ✅ Works offline (after model download)
- ✅ You own the transcript completely

---

## Try It: Transcribe a Short Lecture Clip

1. Record 5 minutes of a lecture, presentation, or video audio
2. Save as `practice.mp3` on your computer
3. Run: `pip install faster-whisper`
4. Run: `python -m faster_whisper transcribe practice.mp3 --model tiny --output_format txt`
5. Open `practice.txt` and read your transcript
6. Try the `base` model for comparison — notice the speed vs. accuracy difference

---

## Key Takeaways

1. **Local transcription** keeps lecture content private and on your computer
2. **faster-whisper** is the recommended tool (Python, accurate, actively maintained)
3. **Start with `base` model** — good balance of speed and accuracy
4. **SRT format** includes timestamps — useful for syncing with video
5. **No monthly limits** — transcribe as many lectures as you want

---

## Next: [Chapter 8 — Adding Captions to a Video](08-video-captions.md)

*Create SRT/VTT caption files and add them to your videos.*