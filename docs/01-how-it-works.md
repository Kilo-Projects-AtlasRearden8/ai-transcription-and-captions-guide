# Chapter 1: How AI Transcription Works

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## The Big Idea

You speak. AI writes it down. That's it.

But under the hood, something clever happens. Understanding the basics helps you pick the right tool and get better results.

---

## The Three-Step Pipeline

Every AI transcription system — whether cloud or local — does three things:

```
Audio File → [1] Feature Extraction → [2] Acoustic Model → [3] Language Model → Text
```

### Step 1: Feature Extraction
The AI chops your audio into tiny slices (usually 20–30 milliseconds each). For each slice, it measures frequencies — basically, a fingerprint of the sound at that moment.

**Think of it like:** Taking a photo of a sound wave every 0.02 seconds.

### Step 2: Acoustic Model
This model has "listened" to thousands of hours of speech. It matches each sound-slice to *phonemes* — the building blocks of words (like "k", "ae", "t" for "cat").

**Think of it like:** A listener who knows every accent and mumble pattern.

### Step 3: Language Model
Phonemes alone give you "k ae t". The language model knows English (or other languages) — grammar, common phrases, context. It turns "k ae t" into "cat" not "kat" or "cut."

**Think of it like:** Autocomplete on steroids. It predicts the most likely word sequence.

---

## Why This Matters for You

| If your audio has... | The pipeline struggles with... | Fix it by... |
|---|---|---|
| Background noise | Step 1 (feature extraction) | Record in a quiet room, use a directional mic |
| Accents / fast speech | Step 2 (acoustic model) | Choose a model trained on diverse speech (Whisper, Vosk) |
| Technical jargon / names | Step 3 (language model) | Add custom vocabulary, or edit afterward |
| Multiple speakers | All steps | Use speaker diarization tools (Chapter 10) |

---

## The Secret: It's All Probabilities

AI doesn't "know" what you said. It calculates: *"Given these sound frequencies, what word sequence is most probable?"*

That's why:
- Clear audio = high confidence = accurate transcript
- Noisy audio = low confidence = hallucinations (wrong words)
- Silence or music = garbage output (the model tries to "hear" words)

**Pro tip:** Most tools show confidence scores. Low confidence = check that part manually.

---

## Meet the Main Models You'll Encounter

| Model | Type | Strengths | Best For |
|---|---|---|---|
| **Whisper** (OpenAI) | Cloud & Local | Multilingual, robust to noise, free weights | Almost everything |
| **Vosk** | Local only | Fast, tiny models, offline | Low-end computers, mobile |
| **Faster-Whisper** | Local only | 4–8x faster than original Whisper | Local transcription on CPU |
| **AssemblyAI** | Cloud only | Speaker labels, summarization, free tier | Meetings, podcasts |
| **Deepgram** | Cloud only | Real-time streaming, cheap | Live captions, apps |
| **Google Speech-to-Text** | Cloud only | Huge language support | Non-English, enterprise |

We cover all of these in Chapters 3 and 4.

---

## Try It: See the Pipeline in Action

**Online demo (no install):**
1. Go to [huggingface.co/spaces/openai/whisper](https://huggingface.co/spaces/openai/whisper)
2. Click the microphone or upload a short audio file
3. Watch the text appear — that's the pipeline running in real time

**What to notice:**
- Pauses become punctuation
- "Um" and "uh" are usually filtered out
- Proper nouns (names, places) may be misspelled

---

## Key Takeaways

1. **Transcription = 3 steps:** Features → Phonemes → Words
2. **Quality in = quality out:** Clean audio is the #1 factor
3. **Models differ:** Some favor speed, some accuracy, some languages
4. **Confidence scores exist:** Use them to know what to double-check
5. **You don't need to understand the math** — just know what affects results

---

## Next: [Chapter 2 — Key Terms You'll See](02-key-terms.md)

*Learn the vocabulary so tool documentation makes sense.*