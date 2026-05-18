# Research Folder Template

A folder pattern you can copy into any research project — your dissertation, an article, a fieldwork archive. Three numbered folders enforce a separation between the three kinds of artifacts produced when working with AI in research.

## The pattern

```
your-project/
├── 01_Raw_Data/
├── 02_LLM_Interactions/
└── 03_Synthesized_Text/
```

The numbering is deliberate. It imposes a chronological and epistemic order:
- **Raw data** comes first — untouched primary sources.
- **LLM interactions** sit in the middle — your dialogue with the model is a *process artifact*, not a source, and not a draft.
- **Synthesized text** is what you, the human, author at the end.

Keeping these separate makes your use of AI legible — to your supervisor, to peer reviewers, to your future self, and to the institutional citation guidelines (EU, TH Köln, University of Basel) referenced in [`../references/reading-list.md`](../references/reading-list.md).

## `01_Raw_Data/`

Anything goes here: field notes, sketches, site photos, audio clippings, raw transcripts, primary documents. **The LLM does not modify anything here.** Treat the contents as read-only. If you transcribe an interview, the transcript lives here. If you photograph a building, the photo lives here. If you record a 90-second clip in the field, the audio file lives here.

The only filing convention this template asks of you is a **date-prefix** in filenames — `YYYY-MM-DD_*`. Everything after the date is your choice: `2026-04-12_site-entrance.jpg`, `2026-04-12_interview-A.wav`, `2026-04-12_interview-A.md` are all fine. A transcript that shares its audio file's stem (`interview-A`) keeps the link between them visible without needing a subfolder.

**On sensitive material.** Anonymize identifying details — names, addresses, organisational affiliations — in both filenames and inside transcripts *before* you expose any of this to the model. Local LLMs run on your machine and do not phone home, but a copy you paste into a prompt becomes part of your interaction log in `02_LLM_Interactions/`, and that log is what you'll cite. The institutional guidelines in [`../references/reading-list.md`](../references/reading-list.md) (EU, TH Köln, University of Basel) all converge on the same point: handle sensitive material with the same care you would in any non-AI workflow.

You may quote from this folder when prompting the model, but the original stays untouched.

## `02_LLM_Interactions/`

One file per session. Suggested filename pattern:

```
YYYY-MM-DD-short-topic.md
```

For example: `2026-05-22-mobility-tensions.md`

Each session file should record:

- **Model + quantization** used (e.g., `Qwen 2.5 7B Instruct Q4_K_M`)
- **System prompt** (paste the full text — don't just say "Reflective Assistant")
- **Conversation** — your messages and the model's responses, in order
- **What you took from it** — a 1–3 sentence note on what was useful (or not)

This folder is your audit trail. When a guideline asks you to "document your prompting process" (TH Köln 2024; University of Basel 2025), this is what they mean.

Markdown is convenient because it's plain text, diffable, and easy to back up. But any format that preserves the conversation is fine.

## `03_Synthesized_Text/`

Your drafts, revisions, and final outputs. **Human-authored.** You may have been informed by what's in `02_LLM_Interactions/`, but what lives here is your prose, your structure, your argument.

If a paragraph here originated as a model response, the honest move is to rewrite it in your own voice — and to cite the interaction (see institutional guidelines). The model is not a co-author.

## Why this matters

Intended workshop learning #5 is *"transparent self-reflection and documentation of LLM use."* This folder pattern operationalizes that learning. It's not about extra paperwork — it's about treating your relationship with AI tools as something worth knowing and being able to show.

If you adopt this pattern, after a few weeks you'll have a record of:

- which models worked for which kinds of thinking,
- which prompts surfaced something useful and which produced generic output,
- where your own writing diverged from the model's suggestions,
- and where it didn't.

That record is what turns "using AI" into a craft you can refine (Mills 1959; Sennett 2008).

## How to copy this template

From the terminal, in the folder where your project lives:

```bash
cp -r /path/to/this/templates ./my-new-project
```

Or, on macOS/Windows, just drag the three numbered folders into your project folder in Finder/Explorer. Delete this README from the copy if you don't need it.
