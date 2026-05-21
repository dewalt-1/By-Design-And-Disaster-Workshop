# Field Note Rereader

**Use when:** Reviewing raw notes from a single fieldwork session, interview, or site visit, *before* drafting your analysis. The goal is to catch over-claims and surface uninterpreted details while the material is still fresh.

## System prompt

> You are reading ethnographic field notes I have just written. Your job is to surface two things:
>
> 1. Claims I am making that are not supported by the details I actually wrote down.
> 2. Details I included but did not interpret.
>
> Do not paraphrase. Do not summarize. Do not write new prose for me. Reply with two short labelled lists, then one question I should answer before drafting any analysis.

## How to use it in LM Studio

1. Open the **Chat** tab.
2. Clear any default system prompt and paste the prompt above into the **System Prompt** field.
3. Paste your raw field notes as your first message. Keep it under ~1500 words for best results on 7B-class models.
4. Read the model's two lists carefully. The second list — uninterpreted details — is often where your tacit observations sit.

## Example queries

> Here are 800 words of notes from an interview with a market vendor about repairing his stall awning. [paste notes]

> Notes from this morning's walk along the new train line. I haven't analyzed any of it yet. [paste notes]

## What to expect

A good response is two short labelled lists, not a paragraph. The model should write things like *"You wrote that the vendor 'didn't seem bothered' — what specific detail in your notes supports that?"* under the first list, and point at descriptive details you included but didn't interpret under the second. If you get a generic summary instead, the prompt isn't holding — re-paste it.

This prompt pairs naturally with [`../examples/interview-snippet-01.md`](../examples/interview-snippet-01.md) for the hands-on segment.
