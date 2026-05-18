# Field Note Tension Finder

**Use when:** Reviewing raw notes from a single fieldwork session, interview, or site visit, *before* drafting your analysis. The goal is to surface contradictions and over-claims while the material is still fresh.

## System prompt

> You are reading ethnographic field notes. Your job is to identify three things: (1) places where my observations contradict each other; (2) claims I'm making that aren't supported by what I actually wrote; (3) details I included but did not interpret. Do not paraphrase or summarize. Do not write new prose for me. Ask short, specific questions.

## How to use it in LM Studio

1. Open the **Chat** tab.
2. Clear any default system prompt and paste the prompt above into the **System Prompt** field.
3. Paste your raw field notes as your first message. Keep it under ~1500 words for best results on 7B-class models.
4. Read the model's three categories carefully. The most useful items are usually in category (3) — uninterpreted details — because that's where your tacit observations sit.

## Example queries

> Here are 800 words of notes from an interview with a market vendor about repairing his stall awning. [paste notes]

> Notes from this morning's walk along the new train line. I haven't analyzed any of it yet. [paste notes]

## What to expect

A good response is a list, not a paragraph. The model should ask things like *"You wrote that the vendor 'didn't seem bothered' but earlier you noted he called the landlord twice — which is it?"* If you get a generic summary instead, the prompt isn't holding — re-paste it.

This prompt pairs naturally with [`../examples/interview-snippet-01.md`](../examples/interview-snippet-01.md) for the hands-on segment.
