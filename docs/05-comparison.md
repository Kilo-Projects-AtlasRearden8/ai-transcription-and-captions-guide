# Chapter 5: Comparison: Which Should You Use?

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## Decision Flowchart

```
Is the audio sensitive (patients, confidential, personal)?
├─ YES → Use LOCAL (Chapter 4)
└─ NO → Continue

Do you need speaker labels ("Speaker 1", "Speaker 2")?
├─ YES → Cloud: AssemblyAI or Otter (Chapter 3)
└─ NO → Continue

Is it a video you want captions for?
├─ YES → YouTube auto-captions (Chapter 3)
└─ NO → Continue

Do you want zero setup, no install?
├─ YES → Cloud: Google Docs Voice Typing (Chapter 3)
└─ NO → LOCAL: faster-whisper (Chapter 4)
```

---

## Scenario-Based Recommendations

| Scenario | Recommended | Why |
|---|---|---|
| Team meeting, confidential | **Local (faster-whisper)** | Privacy, no limits |
| Lecture recording | **Local (faster-whisper)** | Long files, free, offline |
| YouTube video captions | **YouTube Studio** | Free, built-in, downloads SRT/VTT |
| Quick dictation, notes | **Google Docs Voice Typing** | No install, real-time |
| Podcast with multiple speakers | **AssemblyAI** | Speaker diarization, summaries |
| Live event captions | **Deepgram** (streaming) | Real-time, low latency |
| Sensitive client call | **Local** | Audio never leaves your machine |
| Old/slow computer | **Vosk** or **tiny Whisper** | Low resource usage |
| Non-English audio | **Whisper (local)** or **Google Cloud** | Best multilingual support |
| One-time 10-minute file | **YouTube** or **Otter free tier** | No setup needed |

---

## Feature Comparison

| Feature | faster-whisper (Local) | YouTube | Google Docs | AssemblyAI | Otter |
|---|---|---|---|---|---|
| Cost | Free | Free | Free | ~5 hrs/mo free | 600 min/mo free |
| Privacy | Excellent | Low | Low | Low | Low |
| Install required | Yes | No | No | No | No |
| Internet after setup | No | Yes | Yes | Yes | Yes |
| Speaker labels | No (manual) | No | No | Yes | Yes |
| Timestamps | Yes | Yes | No | Yes | Yes |
| Export formats | TXT, SRT, VTT, JSON | SRT, VTT, TXT | DOCX, PDF, TXT | SRT, VTT, JSON, TXT | TXT, PDF, SRT, DOCX |
| Languages | 99+ | Many | Many | Many | English-focused |
| File size limit | Your disk | 128 GB | None | 1 GB | 100 MB |
| Length limit | Your disk | 12 hours | None | ~5 hrs/mo | 600 min/mo |

---

## Privacy Decision Matrix

| Audio Type | Recommendation | Reason |
|---|---|---|
| Doctor-patient recording | **LOCAL only** | HIPAA, patient privacy |
| Business strategy meeting | **LOCAL only** | Confidential company info |
| Personal journal/dictation | **LOCAL only** | Personal data |
| Public lecture (already posted) | Cloud OK | Already public |
| YouTube video you own | Cloud OK | You control the upload |
| Practice recording (no sensitive content) | Either | Low risk |

**Rule of thumb:** If you wouldn't email the audio file, don't upload it to a cloud transcription service.

---

## Cost Reality Check (Free Tiers)

| Service | Free Limit | Resets | Good For |
|---|---|---|---|
| AssemblyAI | ~5 hours/month | Monthly | Occasional meetings |
| Otter.ai | 600 minutes/month | Monthly | Regular meeting notes |
| Deepgram | $200 credit (one-time) | Never | One-time projects |
| Google Cloud | 60 minutes/month | Monthly | Light usage |
| Azure Speech | 5 hours/month | Monthly | Light usage |
| YouTube | Unlimited | N/A | Videos |
| Google Docs | Unlimited | N/A | Dictation |
| Local tools | Unlimited | N/A | Everything |

---

## Hybrid Workflow (Best of Both)

Use cloud for convenience, local for sensitivity:

```
Non-sensitive draft → Cloud transcription (fast, speaker labels)
Sensitive sections → Re-transcribe locally (private)
Combine → Edit in one document (Chapter 9)
```

Or: transcribe everything locally (Chapter 4), then use cloud only for speaker diarization on non-sensitive files.

---

## Try It: Pick Your Tool

Answer these three questions:

1. Is the audio sensitive? → **Yes = Local**
2. Do you need speaker labels? → **Yes = AssemblyAI/Otter (cloud)**
3. Is it a video? → **Yes = YouTube auto-captions**

Write down your choice, then go to the matching chapter.

---

## Key Takeaways

1. **Sensitive audio = local, always**
2. **Cloud free tiers reset monthly** — track usage
3. **YouTube is best for video captions** — free SRT/VTT downloads
4. **Local tools have no monthly limits** — transcribe as much as you want
5. **Mix and match** — cloud for convenience, local for privacy

---

## Next: [Chapter 6 — Transcribing a Meeting (Cloud)](06-meeting-cloud.md)

*Step-by-step cloud meeting transcription.*