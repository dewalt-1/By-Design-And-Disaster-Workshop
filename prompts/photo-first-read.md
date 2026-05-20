# Photo First Read

**Use when:** You have a photograph from a site visit, fieldwork, or archival source, and you want a first-pass description on paper before you start interpreting it. Requires a **vision-capable model** — see setup below.

## System prompt

> You are looking at a photograph from my field research. Describe only what you can see — do not invent context or speculate about what is outside the frame.
>
> Reply in two short labelled lines, then one question:
>
> **Foreground:** what is in the front of the image.
> **Background:** what is behind or surrounding it.
> **Question:** one question that would help me look at this photo more carefully.

## How to use it in LM Studio

1. Make sure you have a vision-capable model loaded — see [`../prep/setup-guide.md`](../prep/setup-guide.md) for **Qwen2-VL 7B Instruct**. If the loaded model is text-only, LM Studio will not show the image-attach button.
2. Open the **Chat** tab. Clear any default system prompt and paste the prompt above into the **System Prompt** field.
3. Click the **paperclip / image** icon in the message composer and attach a photo.
4. Send the photo as your first message — no text needed alongside it unless you want to ask a follow-up.
5. Read the response. Answer the model's question by sending a reply that says what you actually see when you look at the photo again.

## Example queries

> [attach a single site photo, no caption needed]

> [attach a photo of a posted notice at a transit station]

If you have a series of photos, **send them one at a time** rather than as a batch. Local vision models are much weaker at cross-image reasoning than at single-image description.

## What to expect

A well-functioning response sticks to what is visible and asks a question that points back at the image rather than out into your interpretation. If the model invents what is around the frame ("the photographer must have been standing on a bridge") or imputes intent ("the people in the background seem frustrated"), the prompt is not holding — re-paste it, or try a stronger model.

**Setup:** see [`../prep/setup-guide.md`](../prep/setup-guide.md) for installation and the recommended model (**Qwen2-VL 7B** for photos, **Qwen 2.5 7B** for text).
