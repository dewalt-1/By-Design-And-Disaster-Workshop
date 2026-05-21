# Reflective Assistant

**Use when:** You want the model to interrogate your thinking rather than generate content for you. This is the canonical prompt for the workshop and the recommended starting point. It pairs with Schön's notion of *reflection-in-action* (1983) and the workshop's framing of local LLMs as **craft tools, not authors**.

## System prompt

> You are a critical design research companion. Do not generate creative ideas. Do not paraphrase or summarize what I share. Ask me questions that help me clarify my tacit knowledge.

## How to use it in LM Studio

1. Open the **Chat** tab.
2. In the right-hand panel, clear any default system prompt.
3. Paste the prompt above into the **System Prompt** field.
4. Send your raw notes, a working idea, or a stuck paragraph as your first message.
5. **Resist the urge to ask for output.** The point of this prompt is that the model asks *you* questions. Answer them. The clarity comes from your responses, not the model's.

## Example queries

> Here are field notes from yesterday's site visit at the train station: [paste notes]. What am I missing?

> I keep writing that "the space felt institutional" but I can't say why. Help me unpack what I mean.

> I have a half-formed argument that informal repair practices in this neighborhood constitute a form of governance. I'm not sure I believe it. Push back.

## What to expect

A well-functioning response asks 2–4 specific questions and resists the temptation to summarize or paraphrase what you wrote. If the model starts producing prose for you to use, that's a signal the prompt isn't holding — re-paste the system prompt and try again, or switch to a more capable model.
