---
name: export
description: Opt-in export of a finished spec into local files in another layout, either a stories folder or a plain issues list. Use only when the user asks to export, convert or hand the spec to another tool. Never publishes anything.
---

# idea2spec: export

Run only when the user asks. This skill writes local Markdown files and nothing else. It never posts to GitHub, Google Docs or any other service. If the user wants that, give them the files and tell them how to paste or upload them themselves.

## Preconditions
- `spec.md` exists with `status: reviewed`. If not, offer to run the review skill first.
- The user has chosen a format and approved the output path. Write only under `idea2spec/<NNN-slug>/export/`.

## Formats

### Stories folder (`export/stories/`)
- `stories.md`: user stories ordered by priority P1, P2, P3 (Must, Should, Could), each with Start / Action / Result scenarios, REQ and MET IDs kept, and at most 4 `[ASK OWNER]` markers.
- `README.md`: one paragraph saying how the folder is laid out and that the user adapts it to whatever tool they use.

### Issues list (`export/issues.md`)
One section per Must and Should feature: title, description, acceptance, labels (priority, type), dependencies, and the evidence IDs. The user copies these into their tracker by hand.

## After export
List the files created and remind the user that nothing left their machine.
