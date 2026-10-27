# Chapter 9: Editing and Cleaning Transcripts

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## Why Edit?

AI transcription is good but not perfect. Common issues:
- Misheard words (especially names, jargon, numbers)
- Missing punctuation
- Filler words ("um," "uh," "like")
- No paragraph breaks
- Speaker labels missing or wrong

A 10-minute edit turns a rough transcript into a useful document.

---

## The Editing Workflow

### Step 1: Read While Listening (First Pass)

Open your transcript and audio side by side. Play the audio and follow along:

- [ ] Fix wrong words
- [ ] Add missing punctuation
- [ ] Fix capitalization (names, start of sentences)
- [ ] Mark sections you can't understand with `[inaudible]`

**Don't aim for perfect on the first pass.** Get it readable, then refine.

### Step 2: Format for Readability (Second Pass)

- Break long blocks into paragraphs
- Add speaker labels ("Speaker 1:" → "Sarah:")
- Add section headers for topic changes
- Remove or reduce filler words (optional — see below)
- Add timestamps for key moments

### Step 3: Final Review

- Read the whole thing aloud
- Check names and technical terms against the audio
- Verify action items and decisions are captured
- Export in your desired format (Chapter 12)

---

## Common Fixes

### Misheard Words
| AI Output | Correction | Context Clue |
|---|---|---|
| "reck a nice beach" | "recognize speech" | Sounds similar, context |
| "AI dynamics" | "Asdale Dynamics" | Company name |
| "mitochondria is" | "mitochondria are" | Grammar |
| "2026" | "twenty twenty-six" | Numbers vs words |

### Filler Words: Keep or Remove?

**Keep them if:**
- This is a verbatim legal/medical record
- You need exact word-for-word accuracy

**Remove them if:**
- This is for reading, studying, or sharing
- You want a clean, readable document

**Compromise:** Remove obvious fillers ("um," "uh") but keep meaningful speech.

---

## Speaker Labels

If your tool didn't add speaker labels (common with local Whisper):

1. Listen to identify who speaks when
2. Add labels at each speaker change:

```
Speaker 1: Good morning, everyone.
Speaker 2: Good morning. Ready to start?
Speaker 1: Yes, let's begin with the agenda.
```

3. Replace "Speaker 1/2" with actual names after the meeting

---

## Tools for Editing

| Tool | Platform | Cost | Best For |
|---|---|---|---|
| Any text editor (Notepad, TextEdit, VS Code) | All | Free | Simple edits, SRT/TXT files |
| Otter.ai web editor | Web | Free tier | Cloud transcripts with speaker labels |
| Subtitle Edit | Windows | Free | SRT caption editing |
| Aegisub | All | Free | SRT/ASS caption editing |
| Microsoft Word / Google Docs | All | Free | Formatted documents, sharing |

---

## Try It: Edit a 2-Minute Transcript

1. Take any transcript you've generated (Chapters 6–8)
2. Open it in a text editor
3. Play the audio and follow along for 2 minutes
4. Fix 5–10 errors you find
5. Add paragraph breaks every 3–4 sentences
6. Save as `edited.txt` or `edited.md`

Compare original vs. edited — notice the difference in readability.

---

## Key Takeaways

1. **AI transcripts need editing** — expect 5–15% error rate
2. **Read while listening** — catches errors fastest
3. **Fix names and jargon first** — most important for accuracy
4. **Add speaker labels and paragraphs** — makes it readable
5. **Keep or remove fillers** based on your purpose (record vs. readable)

---

## Next: [Chapter 10 — Speaker Labels and Timestamps](10-speakers-timestamps.md)

*Advanced: identifying speakers and working with timecodes.*