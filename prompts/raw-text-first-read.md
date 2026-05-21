# Raw Text First Read

**Use when:** You have a primary-source text from the field — a leaflet, policy document, posted notice, archival fragment, signage — and you want a first-pass description on paper before you start citing it. **Not for your own field notes** — use [`reflective-assistant.md`](reflective-assistant.md) for those.

## System prompt

> You are reading a primary-source text I encountered in my field research — a leaflet, policy document, posted notice, archival fragment, or similar. Do not paraphrase.
>
> Reply in two short labelled lines, then one question:
>
> **Form:** what kind of text this is (notice, leaflet, official document, etc.) and its likely audience.
> **Stated:** the explicit claim or instruction the text makes.
> **Question:** one question about who produced this and why, that I should answer before citing it.

## How to use it in LM Studio

1. Open the **Chat** tab. Clear any default system prompt and paste the prompt above into the **System Prompt** field.
2. Paste the text as your first message. Include any visible signature, date, or letterhead — those details often shape what counts as the **Form**.
3. Read the response. The **Question:** is the one to do something with — it usually points at provenance, which is exactly what you need to nail down before the text can carry weight in your writing.

## Example queries

> A posted notice I photographed on the station wall: [paste text].

> Excerpt from a 2018 municipal mobility plan I found in the city archive: [paste excerpt].

For multilingual material, the model often correctly identifies register and likely audience even without being asked to translate. If you want a translation, ask for one in a follow-up message — don't bake it into the system prompt.

## What to expect

A well-functioning response gives concrete answers under **Form:** (e.g., *"Official municipal notice, addressed to commuters using the line"*), not vague ones (*"This is a piece of text"*). If the model speculates beyond what is visible in the source — invents an author, attributes motive — re-paste the prompt or try a more capable model.

**Setup:** see [`../prep/setup-guide.md`](../prep/setup-guide.md) for installation and the recommended model (**Qwen 2.5 7B Instruct**).
