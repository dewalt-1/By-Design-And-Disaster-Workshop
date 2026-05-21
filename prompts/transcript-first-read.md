# Transcript First Read

**Use when:** You have a raw transcript from an interview or recording, and you want a first-pass description on paper before you start interpreting it. Text-only model is fine.

## System prompt

> You are reading the raw transcript of an interview or recording from my field research. Do not paraphrase. Do not summarize.
>
> Reply in two short labelled lines, then one question:
>
> **Register:** who is speaking and how — formal, informal, hedging, technical.
> **Stated:** the explicit claims the speaker makes, in 2–3 short bullets.
> **Question:** one question I should answer about this transcript before I cite it.

## How to use it in LM Studio

1. Open the **Chat** tab. Clear any default system prompt and paste the prompt above into the **System Prompt** field.
2. Paste the transcript as your first message. Keep it under **~1500 words** for best results on 7B-class models — split a longer transcript into segments.
3. Read the response. The **Stated:** bullets give you a clean list of the speaker's explicit claims; this is useful when you come back to the transcript weeks later.
4. Answer the model's closing question in writing. Your answer is often the start of your interpretive notes.

## Example queries

> Transcript from an interview with a market vendor about awning repair. [paste transcript]

> Recording transcript from a community meeting about the new train line. [paste transcript]

The prompt works on transcripts in any language a multilingual model like Qwen 2.5 handles natively. The labels will come back in whatever language the transcript is in — that is correct behaviour, not a bug.

## What to expect

A well-functioning response gives you concrete bullets under **Stated:** that quote or closely paraphrase the speaker, not abstract summaries. If you see *"the speaker discusses their work"* under **Stated:**, the prompt is not holding — re-paste it.

**Setup:** see [`../prep/setup-guide.md`](../prep/setup-guide.md) for installation and the recommended model (**Qwen 2.5 7B Instruct**).
