# Chapter 2: Key Terms You'll See

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## Why This Chapter Exists

Tool documentation throws around jargon. This chapter translates it. Bookmark it and come back when you hit an unfamiliar word.

---

## A–Z Glossary

### Acoustic Model
The part of the AI that matches raw sound to phonemes (sound units). Trained on thousands of hours of speech.

### Alignment / Forced Alignment
Matching each word in a transcript to its exact time in the audio. Used for captions and search.

### ASR (Automatic Speech Recognition)
The technical term for "speech-to-text." You'll see this in docs and research papers.

### Beam Search
A decoding strategy: the AI keeps multiple transcription guesses at once, then picks the best. Wider beam = more accurate, slower.

### Confidence Score
A number (0–1 or 0–100) saying how sure the model is about each word/segment. Low score = likely error.

### CTC (Connectionist Temporal Classification)
A method that lets the model output characters without pre-aligned training data. Used in many modern ASR systems.

### Decoder
The algorithm that turns model probabilities into final text. Greedy (fast) vs. beam search (accurate).

### Diarization / Speaker Diarization
"Who spoke when." Splits audio by speaker: "Speaker 1: Hello. Speaker 2: Hi there."

### Endpointing / Voice Activity Detection (VAD)
Detecting when speech starts and stops. Silences are cut out before transcription.

### Feature Extraction
Converting raw audio waveform into numbers the model understands (mel spectrograms, MFCCs).

### Hallucination
The model invents words that weren't spoken — common in silence, music, or heavy noise.

### Language Model (LM)
Predicts likely word sequences. Turns "wreck a nice beach" into "recognize speech."

### Latency
Time between speech and text appearing. Real-time = <300ms. Batch = minutes/hours.

### MFCC (Mel-Frequency Cepstral Coefficients)
A classic audio feature representation. Less common now (neural nets learn their own features).

### Model Weights / Checkpoint
The downloaded file containing the trained neural network. "Download the model" = get the weights.

### Phoneme
The smallest unit of sound that distinguishes words. English has ~44 phonemes.

### Real-time / Streaming
Transcription happens while you speak. vs. **Batch / Offline**: transcribe a finished file.

### Sample Rate
How many audio snapshots per second. 16 kHz = standard for speech. 44.1 kHz = CD quality (overkill for ASR).

### Speaker Identification
Not just "Speaker 1" — actual names. Requires enrollment (training on known voices).

### Token / Subword Token
Models don't see whole words. They see chunks: "trans" + "crip" + "tion". Vocabulary size = number of tokens.

### VAD (Voice Activity Detection)
See Endpointing.

### WER (Word Error Rate)
Standard accuracy metric: (Substitutions + Insertions + Deletions) / Total Words. Lower = better. Human-level ≈ 5%.

---

## Categories at a Glance

### Audio & Recording
| Term | Meaning |
|---|---|
| Sample rate | Snapshots per second (16 kHz standard) |
| Bit depth | Precision per sample (16-bit standard) |
| Mono vs stereo | One channel vs two — ASR wants mono |
| Gain / clipping | Volume too low / too high (distorted) |

### Model & Inference
| Term | Meaning |
|---|---|
| Inference | Running the model (vs. training) |
| Quantization | Compressing model weights (int8, int4) — faster, smaller, slightly less accurate |
| GPU / CPU | Graphics card vs. main processor — GPU is much faster for AI |
| VRAM | GPU memory — limits model size you can run |

### Output & Formats
| Term | Meaning |
|---|---|
| SRT / VTT | Caption formats with timestamps |
| JSON | Structured data — confidence, timestamps, alternatives |
| TXT / MD | Plain text or Markdown — no timing info |
| Diarization JSON | Speaker segments with start/end times |

---

## Cheat Sheet: What to Look For in Tool Docs

| If you see... | It means... |
|---|---|
| "Supports 16 kHz mono WAV" | Convert your audio first (Chapter 6) |
| "Beam size 5" | Accuracy setting — higher = slower |
| "int8 quantization" | Model is compressed — faster, smaller download |
| "Streaming API" | Real-time, for live captions |
| "Diarization included" | Speaker labels come free |
| "WER 12% on LibriSpeech" | Benchmark accuracy — compare apples to apples |

---

## Try It: Decode a Real Doc Page

Go to [github.com/openai/whisper](https://github.com/openai/whisper) and scan the README. You'll now recognize:
- "multilingual" → language model handles many languages
- "robust to accents" → acoustic model trained on diverse speech
- "tiny/base/small/medium/large" → model sizes (parameters)
- "CPU inference" → runs without GPU

---

## Key Takeaways

1. **ASR = Automatic Speech Recognition** — the formal name
2. **Diarization = speaker labels** — essential for meetings
3. **WER = accuracy metric** — lower is better, human ≈ 5%
4. **Quantization = smaller/faster model** — trade-off: slight accuracy loss
5. **Confidence scores = your quality radar** — always check low-confidence segments

---

## Next: [Chapter 3 — Cloud Options (Free Tiers)](03-cloud-options.md)

*Free online services — no install, but your audio leaves your computer.*