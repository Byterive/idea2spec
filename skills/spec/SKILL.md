---
name: spec
description: Write the spec for an idea that passed the gate (GO), or a one-page kill memo for a KILL. The spec has the goal, audience, success metrics, MVP scope and non-goals, must / should / could features, requirements, monetization, risks, milestones, and a validation plan with kill criteria. Use after a GO verdict, or when the user asks to write up the spec.
---

# idea2spec: spec

## Preconditions

- `01-decision.md` exists and the verdict is GO or "GO (unaudited)". If it is CLARIFY or KILL, do not write a spec. Offer the kill memo or the clarify questions instead.
- If the user insists on a spec despite a CLARIFY or KILL, write it only after they say so explicitly, and record the override and the unresolved risks at the top of `spec.md`.
- The user has said yes to writing the spec. Folder and file rules are in `../run/references/safety.md`.

## How to write it

1. Read `interview.md`, `00-evidence.md`, `01-decision.md`.
2. Fill `templates/spec.md` section by section. Keep it proportional: a hobby idea gets a short spec, a business idea a longer one. Do not pad.
3. Rules for content:
   - Every factual statement about the market carries an evidence ID from the ledger, or is marked `[Assumption]`.
   - Features are MoSCoW tiers: Must (the smallest thing that can run the cheapest test), Should, Could. Order inside a tier by dependency first, then by evidence strength against effort (High / Medium / Low). Do not use a numeric priority formula as a gate.
   - Each Must feature gets an ID (REQ-01...), a Start / Action / Result acceptance example, a test hint, and its evidence reference.
   - Success metrics (MET-01...) are measurable, dated and independent of technology.
   - Kill criteria (KC-001...) copy the thresholds from the decision file and add check dates.
   - At most 4 `[ASK OWNER]` markers; each states the question and who must answer it.
   - Non-goals and a do-not-build list are mandatory.
   - List every API key, account or paid service a build would need, and every action a coding agent must not take without asking.
4. Show the draft summary and ask for changes. Then ask once: "May the review step rewrite spec.md up to 3 times to fix checklist failures?" A yes covers the review loop only. Then run the review skill.

## Kill memo

On KILL (or when asked) write `kill-memo.md` from `templates/kill-memo.md`: what was tested, why it died, what would have to change for a retry (one summary line; if `02-improve.md` exists, point to it instead of repeating it), and the best use of the saved time. A kill is a successful outcome; write it that way.

## Never

Never build, scaffold code or start tools. The spec ends with a handoff question handled by the run skill.
