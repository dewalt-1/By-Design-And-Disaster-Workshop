# Examples

Short anonymized snippets to paste into the chat as context alongside a system prompt from [`../prompts/`](../prompts/). They give the model something concrete to react to during the hands-on segment, so we're not just discussing prompting in the abstract.

## How to use them

1. Load a model in LM Studio.
2. Set a system prompt from [`../prompts/`](../prompts/).
3. Open a new chat. Paste a snippet as your first message, prefaced with what you want the model to do. For example:

   > Read this interview excerpt and identify three tensions in what the participant is saying.
   > [paste snippet]

4. Iterate. Ask follow-up questions that draw out specifics: *Which part of the excerpt makes you think that? What's the participant not saying?*

The point of the hands-on is not the answers the model gives — it's noticing the shape of the conversation, where it helps you think, and where it veers off.

## Suggested pairings

| Snippet | Try with prompt |
|---|---|
| [`interview-snippet-01.md`](interview-snippet-01.md) | [`../prompts/field-note-tension-finder.md`](../prompts/field-note-tension-finder.md) |

## A note on data

All snippets in this folder are anonymized or fictionalized. The source materials that inspired them — colleagues' transcripts, our own field notes — are not part of this public repo.

If you bring your own research material into the workshop:

- Keep it on your machine. Don't send unconsented research data through any cloud AI service.
- Use the folder pattern in [`../templates/`](../templates/) to keep raw sources, LLM interactions, and synthesized writing separate.
- The whole reason local LLMs exist in this workshop is so you don't have to make trade-offs between using AI and protecting your participants.
