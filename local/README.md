# Facilitator working folder

This folder is for **real ethnographic material** that Ben and Simon use to develop and rehearse the workshop — Simon's Dakar Mobilities photos, transcripts, and audio clippings live here.

It mirrors the public [`../templates/`](../templates/) structure on purpose: when Ben demonstrates the three-stage pattern in segment 2, the same workflow runs identically against the populated `local/` view and the empty `templates/` view. No cognitive overhead, no separate instructions.

## What's tracked, what isn't

The folder skeleton ships with the repo:

- `local/README.md` (this file)
- `local/01_Raw_Data/.gitkeep`
- `local/02_LLM_Interactions/.gitkeep`
- `local/03_Synthesized_Text/.gitkeep`

Everything else under `local/` is gitignored. Drop real files into the three subfolders without worrying about leaking sensitive material into the public repo — see [`../.gitignore`](../.gitignore) for the rule.

## How to use this folder

Read [`../templates/README.md`](../templates/README.md) first — the conventions there apply identically here. The difference is only that the files you put here are the actual research material, not a teaching example.

## Adding a new subfolder

If you need a fourth stage (say, `04_Sandbox/`), do two things:

1. Create the folder and anchor it: `mkdir local/04_Sandbox && touch local/04_Sandbox/.gitkeep`
2. Add a negation rule to [`../.gitignore`](../.gitignore) right next to the existing three: `!local/04_Sandbox/`

Without the negation rule in `.gitignore`, the new folder's contents — including the `.gitkeep` — will be ignored, and the folder won't ship with the repo.
