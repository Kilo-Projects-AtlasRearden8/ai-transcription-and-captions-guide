# Chapter 11: Privacy Rules and Best Practices

*Part of the Free AI Transcription and Captions Guide by Asdale Dynamics, LLC*

---

## Why Privacy Matters

Transcription involves audio that often contains:
- Personal conversations
- Health information
- Business secrets
- Client details
- Financial information

Once you upload audio to a cloud service, you lose direct control over it.

---

## The Golden Rule

**If you wouldn't email the audio file to a stranger, don't upload it to a cloud transcription service.**

---

## Cloud vs Local: Privacy Comparison

| Aspect | Cloud Transcription | Local Transcription |
|---|---|---|
| Audio leaves your device | Yes | No |
| Stored on third-party servers | Yes (temporarily or longer) | No |
| Account required | Usually | No |
| Internet needed | Yes | No (after setup) |
| Terms of service apply | Yes | No |
| You control retention | Limited | Full |
| HIPAA compliant | Rarely (paid tiers only) | Yes (by design) |
| Best for | Non-sensitive content | Sensitive content |

---

## What Never to Upload to Cloud Transcription

❌ **Never upload:**
- Patient health information (PHI) — HIPAA risk
- Therapy or counseling sessions
- Confidential business meetings
- Unreleased product details
- Personal financial data
- Social security numbers, IDs, passwords
- Anything under NDA
- Legal case details

✅ **Generally OK for cloud:**
- Public lectures you own
- Your own dictation/journal (non-sensitive)
- Practice recordings
- Content already public

---

## HIPAA and Healthcare Audio

If you're a healthcare worker:

- **Cloud transcription is generally NOT HIPAA-compliant** on free tiers
- Paid enterprise tiers may offer BAA (Business Associate Agreement)
- **Use local transcription** for any patient-related audio
- Never upload patient recordings to YouTube, Otter, AssemblyAI, etc.
- This guide is for education only — consult your compliance officer

---

## Local = Privacy by Default

Local tools (faster-whisper, Vosk, whisper.cpp):
- ✅ No account, no email, no registration
- ✅ No API key
- ✅ Audio never leaves your computer
- ✅ Works offline
- ✅ Model files stay on your disk
- ✅ You delete files when you want

This is the recommended approach for sensitive content.

---

## Data Retention: What to Ask Cloud Providers

If you must use cloud transcription, check their policies:

- How long is audio stored?
- Is it deleted after transcription?
- Can you delete it manually?
- Is it used to train their AI models?
- Who can access it?
- Is it encrypted in transit and at rest?

**Look for:** "We delete audio after processing" and "Audio is not used for training."

---

## Practical Privacy Checklist

Before transcribing any audio:

- [ ] Is this audio sensitive (health, business, personal)?
- [ ] If yes → Use **local** transcription (Chapter 4)
- [ ] If no → Cloud is acceptable
- [ ] Did I remove or avoid recording sensitive details?
- [ ] Do I know where the transcript will be stored?
- [ ] Have I deleted source audio after transcribing (if sensitive)?
- [ ] Is the transcript stored securely (encrypted device, access-controlled)?

---

## Secure Storage of Transcripts

Once you have a transcript:

- **Computer:** Use account password, full-disk encryption (FileVault, BitLocker)
- **Cloud storage:** Use encrypted folders, 2FA on your account
- **Sharing:** Share only with people who need it, remove access when done
- **Backup:** Encrypted backups, not public folders

---

## Deleting Source Audio

After transcription, consider:

- **Sensitive audio:** Delete the recording after you verify the transcript
- **Non-sensitive audio:** Keep or delete based on your preference
- **Cloud:** Delete from the service's dashboard after downloading

---

## Try It: Privacy Self-Check

Pick a recording you've made or plan to make:

1. What's in it? (Names? Health info? Business details? Just ideas?)
2. Where will you transcribe it? (Cloud or local?)
3. Is that choice private enough?
4. Where will you store the transcript?
5. When will you delete the source audio?

Write down your answers. This is your privacy plan.

---

## Key Takeaways

1. **Local transcription = maximum privacy** — audio never leaves your device
2. **Never upload sensitive audio** to cloud services (health, business, personal)
3. **Healthcare workers:** local only for patient audio — HIPAA considerations
4. **Delete source audio** after transcribing sensitive content
5. **Store transcripts securely** — encrypted devices, controlled sharing

---

## Next: [Chapter 12 — Export Formats Explained](12-export-formats.md)

*Choosing the right file format for your transcript.*