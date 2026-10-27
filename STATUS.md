# STATUS

## What Was Built

A beginner-friendly manual on free AI transcription and captions, delivered as both Markdown documentation (`docs/`) and a static HTML site (`site/`).

**Project:** Free AI Transcription and Captions Guide  
**Credit:** Asdale Dynamics, LLC (Indiana, formed October 2026)  
**Website:** https://dylanasdale.github.io  
**License:** MIT — Copyright (c) 2026 Asdale Dynamics, LLC

### Documentation (`docs/`)
- `index.md` — Guide overview and table of contents
- `01-how-it-works.md` — The three-step transcription pipeline (features → phonemes → words)
- `02-key-terms.md` — ASR, diarization, WER, quantization, confidence scores, plain English
- `03-cloud-options.md` — YouTube auto-captions, Google Docs Voice Typing, Otter.ai, AssemblyAI, Deepgram
- `04-local-options.md` — faster-whisper, whisper.cpp, Vosk — privacy-first, offline transcription
- `05-comparison.md` — Decision flowchart, scenario recommendations, feature comparison table
- `06-meeting-cloud.md` — Step-by-step meeting transcription with Otter.ai and AssemblyAI
- `07-lecture-local.md` — Step-by-step lecture transcription with faster-whisper (local)
- `08-video-captions.md` — SRT/VTT formats, YouTube, VLC, HTML5 `<track>`, ffmpeg burning
- `09-editing.md` — Editing workflow, common fixes, speaker labels, filler words
- `10-speakers-timestamps.md` — Diarization, manual speaker labeling, timecodes
- `11-privacy.md` — Privacy rules, HIPAA, what never to upload to cloud, local vs cloud comparison
- `12-export-formats.md` — TXT, MD, SRT, VTT, DOCX, PDF, JSON, CSV — which to use when
- `13-quick-reference.md` — One-page cheat sheet for commands, formats, fixes
- `14-troubleshooting.md` — Install, speed, quality, and output problems and fixes
- `15-glossary.md` — Plain-English definitions of all terms

### Static HTML Site (`site/`)
- `index.html` — Landing page with hero, chapter index, cloud vs local table, 5-minute workflow
- `chapter1.html` through `chapter15.html` — HTML versions of every documentation chapter
- `style.css` — Clean, warm, responsive CSS (no frameworks, no external dependencies)

### Root Files
- `README.md` — Project overview, credits Asdale Dynamics, LLC, quick start instructions
- `LICENSE` — MIT License with exact copyright line: "Copyright (c) 2026 Asdale Dynamics, LLC"

## How to Run It

### View the Documentation
Open any `.md` file in the `docs/` folder with a text editor or Markdown viewer.

### View the Static Site
Option 1: Open `site/index.html` directly in a web browser.

Option 2: Serve locally (Python 3):
```bash
python3 -m http.server 8000 -d site
```
Then visit `http://localhost:8000`

Option 3: Serve locally (Node.js / npx):
```bash
npx serve site
```

Option 4: Serve locally (PHP):
```bash
php -S localhost:8000 -t site
```

No build step, no dependencies, no API keys required. The HTML site is pure HTML/CSS with no JavaScript framework.

## Verification Results

| Check | Result |
|---|---|
| LICENSE copyright line exact match | PASS — `Copyright (c) 2026 Asdale Dynamics, LLC` (line 3) |
| Asdale Dynamics, LLC credited in README | PASS |
| All 15 documentation chapters present | PASS (docs/01-15.md + index.md) |
| All 15 HTML chapter pages present | PASS (site/chapter1-15.html + index.html) |
| CSS stylesheet present | PASS (site/style.css) |
| HTML files readable/valid | PASS (all 16 HTML files parse successfully) |
| Static site serves correctly | PASS — index (200), chapter1 (200), chapter15 (200), style.css (200) |
| No .github/workflows files | PASS |
| No secrets, API keys, or personal data | PASS (none present) |
| No remote repos or pushes | PASS (local git only) |
| Plain commit message (no Co-authored-by) | PASS |
| Git initialized and committed | PASS (commit 8d047bf on master) |

## Known Gaps

1. **No automated test suite** — This is a documentation/site project with no code to test. Verification was manual (file presence, HTML parsing, local HTTP serving).
2. **No search functionality** on the static site — Users navigate via the chapter index on the landing page.
3. **No dark mode** — Single light theme; CSS uses system fonts and neutral colors.
4. **Chapter pages are static HTML** — Not generated from Markdown; updates require editing both `docs/` and `site/` versions.
5. **No audio samples included** — Examples reference user-provided recordings.
6. **Whisper model downloads require internet** — First-time local transcription downloads model weights (~100 MB for base model).
7. **No Windows/Mac/Linux-specific installers** — Instructions are command-line based (pip, brew, apt).

## Next Steps (if desired)

- Add a `netlify.toml` or `vercel.json` for one-click static hosting
- Add a `package.json` with a `start` script for `npx serve site`
- Generate HTML from Markdown automatically with a static site generator
- Add print-friendly CSS for the documentation chapters