---
name: review
description: Check a written spec against a checklist and fix problems in at most three loops. Verifies status, IDs, acceptance examples, open clarifications, evidence counts and kill criteria. Use after the spec is written, or when the user asks to review or tidy a spec.
---

# idea2spec: review

Input: `spec.md` and `01-decision.md` in the idea folder. In full mode you may ask the `reviewer` agent to run the checks (it can read but not write); you apply the fixes. In lite mode do the checks yourself.

## Checklist (copy and tick)

```
- [ ] Verdict in the frontmatter matches 01-decision.md (GO, GO (unaudited) or a recorded override)
- [ ] No more than 4 [ASK OWNER] markers, each with a question and an owner
- [ ] REQ, MET and KC IDs are unique and numbered in order
- [ ] Every Must feature has Start / Action / Result acceptance, a test hint and an evidence reference
- [ ] Success metrics are measurable, dated and not tied to a technology
- [ ] Kill criteria match the thresholds in 01-decision.md and have check dates
- [ ] The first milestone is the cheapest test
- [ ] Non-goals and the do-not-build list exist
- [ ] Every market claim has an evidence ID or is marked [Assumption]
- [ ] Evidence counts in the frontmatter match 00-evidence.md
- [ ] Monetization has a one-line calculation with sources
- [ ] Keys, accounts and paid services a build would need are listed
```

## Loop

1. Run the checklist and list failures.
2. Fix them in `spec.md` (ask before overwriting if the user edited it by hand).
3. Repeat. Stop after 3 loops or when all items pass; list anything still failing.
4. Do not invent evidence to make an item pass. Mark it `[Assumption]` or add an `[ASK OWNER]` instead.

Set `status: reviewed` in the frontmatter only when every item passes.
