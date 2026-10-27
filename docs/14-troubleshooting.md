# Chapter 14: Troubleshooting

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## Installation Problems

### "pip: command not found"

**Cause:** Python isn't installed, or pip isn't in your system PATH.

**Fix:**
1. Install Python from [python.org](https://python.org)
2. During installation on Windows, check **"Add Python to PATH"**
3. Restart your terminal
4. Try: `python3 --version` and `pip --version`

### "ModuleNotFoundError: No module named 'faster_whisper'"

**Cause:** faster-whisper isn't installed.

**Fix:**
```bash
pip install faster-whisper
```

If that fails:
```bash
python3 -m pip install faster-whisper
```

### "ffmpeg: command not found"

**Cause:** ffmpeg isn't installed (needed for audio conversion).

**Fix:**
- Mac: `brew install ffmpeg`
- Windows: Download from [ffmpeg.org/download.html](https://ffmpeg.org/download.html)
- Linux: `sudo apt install ffmpeg`

---

## Transcription Problems

### Out of Memory / Computer Freezes

**Cause:** Model too large for your RAM.

**Fix:**
- Use `--model tiny` (smallest)
- Close other applications
- Restart your computer and try again
- Avoid `medium` or `large-v3` on computers with less than 16 GB RAM

### Transcription Is Very Slow

**Cause:** CPU-only processing, large model.

**Fix:**
- Use `--model tiny` or `--model base`
- Close browser tabs and other apps
- Transcribe overnight
- If you have an NVIDIA GPU, install CUDA support for faster processing

### Model Download Fails

**Cause:** No internet, or download interrupted.

**Fix:**
- Check your internet connection
- Try again — downloads resume automatically
- Models download from Hugging Face (may be slow in some regions)

### "File Not Found" Error

**Cause:** Wrong file path or filename typo.

**Fix:**
- Use the full path: `~/Downloads/lecture.mp3`
- Or move into the file's folder first: `cd ~/Downloads`
- Check the filename spelling (case-sensitive on Mac/Linux)

### Wrong Language Detected

**Cause:** Whisper guessed the wrong language.

**Fix:**
- Specify the language: `--language en` (English), `--language es` (Spanish)
- See supported languages in Whisper documentation

---

## Quality Problems

### Many Wrong Words

**Common causes and fixes:**

| Cause | Fix |
|---|---|
| Background noise | Record in a quieter place, closer to the speaker |
| Low volume | Increase microphone gain, speak louder |
| Accent/dialect | Try `medium` or `large-v3` model |
| Fast speech | Ask speakers to slow down |
| Music/overlap | Hard for all ASR — manual editing needed |

### Missing Punctuation

**Fix:** Add punctuation manually during editing (Chapter 9). Some cloud tools add it automatically.

### No Speaker Labels

**Fix:** Local Whisper doesn't do diarization. Add labels manually, or use Otter/AssemblyAI (cloud).

---

## Output Problems

### SRT File Doesn't Show Captions in VLC

**Fix:**
- Name the `.srt` file exactly like the video (e.g., `lecture.mp4` + `lecture.srt`)
- Put them in the same folder
- In VLC: Subtitle → Sub Track → Track 1

### Captions Out of Sync

**Fix:**
- Edit the SRT file's timestamps
- Or use Subtitle Edit (free) to adjust timing

### Transcript Opens as One Long Line

**Fix:** Add paragraph breaks manually. Or re-transcribe with `--output_format txt` (Whisper adds line breaks by segment).

---

## When to Ask for Help

- You get an error message you don't understand
- Transcription crashes repeatedly
- You need to transcribe sensitive audio and aren't sure about privacy

**Resources:**
- [faster-whisper GitHub Issues](https://github.com/SYSTRAN/faster-whisper/issues)
- [Whisper GitHub Discussions](https://github.com/openai/whisper/discussions)
- Asdale Dynamics, LLC — [dylanasdale.github.io](https://dylanasdale.github.io)

---

## Try It: Troubleshoot a Practice File

1. Find any audio file on your computer
2. Try to transcribe it: `python -m faster_whisper transcribe yourfile.mp3 --model tiny`
3. If it works — great! If not, use the fixes above
4. Document what worked and what didn't

---

## Key Takeaways

1. **Most problems have simple fixes** — check Python, pip, ffmpeg first
2. **Use `tiny` model** if you have memory or speed issues
3. **Specify language** if Whisper guesses wrong
4. **Name SRT files to match videos** for VLC playback
5. **When stuck, check the GitHub issues page** for your tool

---

## Next: [Chapter 15 — Glossary](15-glossary.md)

*Plain-English definitions of all terms used in this guide.*