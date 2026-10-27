# Chapter 10: Speaker Labels and Timestamps

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## Speaker Labels: "Who Said What?"

In meetings and interviews, knowing who spoke is as important as what was said.

### How Speaker Labels Work

**Diarization** is the technical term. The AI:
1. Detects voice changes
2. Clusters similar voices together
3. Labels each cluster "Speaker 1," "Speaker 2," etc.

**Limitations:**
- The AI doesn't know names — just "Speaker 1," "Speaker 2"
- Similar voices may be merged
- Overlapping speech is hard to separate
- Local Whisper doesn't do diarization (cloud tools do)

---

## Getting Speaker Labels

### Cloud Tools (Automatic)

| Tool | Speaker Labels | Free Tier |
|---|---|---|
| Otter.ai | Yes (auto) | 600 min/month |
| AssemblyAI | Yes (diarization) | ~5 hours/month |
| YouTube | No | Unlimited |
| Google Docs | No | Unlimited |

### Local Tools (Manual)

faster-whisper does **not** add speaker labels. You add them yourself:

```
[00:00] Speaker 1: Welcome to the meeting.
[00:30] Speaker 2: Thanks for having me.
[00:45] Speaker 1: Let's start with the agenda.
```

Replace "Speaker 1/2" with real names as you edit.

---

## Step-by-Step: Add Speaker Labels Manually

1. Play your audio and follow the transcript
2. Each time the voice changes, add a new line with a label:

```
Speaker 1: Good morning, everyone.
Speaker 2: Good morning. I'm ready to begin.
Speaker 1: Let's start with the quarterly review.
Speaker 3: I have a question about the budget.
```

3. After labeling all speakers, replace generic labels:

```
Speaker 1 → Sarah (Manager)
Speaker 2 → Mike (Developer)
Speaker 3 → Jenny (Designer)
```

Use find-and-replace in your text editor.

---

## Timestamps: "When Was It Said?"

Timestamps let you jump to a specific moment in the audio.

### SRT Timestamps (Automatic from Whisper)

Whisper's SRT output includes timestamps:

```
1
00:00:01,000 --> 00:00:04,000
Welcome to the presentation.
```

### Plain Text Timestamps (Manual)

Add brackets at paragraph starts:

```
[00:00] Welcome to the presentation.
[00:30] Today we'll cover three topics.
[01:15] First topic: project timeline.
```

Useful for:
- Finding a quote in a long recording
- Creating an index of key moments
- Linking to specific audio/video positions

---

## Combined Example: Meeting Transcript with Speakers and Timestamps

```
[00:00] Sarah: Good morning, everyone. Thanks for joining.
[00:15] Mike: Good morning. Ready to go over the launch plan?
[00:30] Sarah: Yes. Let's start with the timeline.
[00:45] Jenny: I have a concern about the design deadline.
[01:00] Sarah: Let's discuss that after the timeline.
[01:15] Mike: The beta is scheduled for March 15.
[01:30] Jenny: That gives us two weeks for design.
```

---

## Timestamps for Captions vs. Transcripts

| Use Case | Format | Example |
|---|---|---|
| Captions (SRT/VTT) | `00:00:01,000 --> 00:00:04,000` | Precise frame-level timing |
| Transcript index | `[00:00]` or `[0:00]` | Approximate, human-readable |
| Video editing | Timecode | Frame-accurate for cuts |

---

## Try It: Label Speakers in a 3-Minute Clip

1. Take any meeting or conversation recording
2. Transcribe it (cloud with labels, or local without)
3. Play and follow along
4. Add speaker labels at each voice change
5. Replace "Speaker 1/2" with real names
6. Add timestamps every 30 seconds
7. Save as `labeled.md`

---

## Key Takeaways

1. **Diarization = automatic speaker labels** — available in cloud tools (Otter, AssemblyAI)
2. **Local Whisper doesn't label speakers** — add manually while editing
3. **Replace generic labels** with real names using find-and-replace
4. **Timestamps** help you find specific moments in audio/video
5. **SRT format** includes precise timestamps for captions

---

## Next: [Chapter 11 — Privacy Rules and Best Practices](11-privacy.md)

*Protecting your data when transcribing audio.*