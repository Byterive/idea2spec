---
name: score
description: Run the go / clarify / kill gate on an idea. Writes the strongest case against the idea first, scores seven dimensions 0 to 2 with evidence caps and vetoes, has the total recomputed by a reviewer, and names the cheapest test. With --after-test it re-scores using real test results (Gate B). Use after research, or when the user asks whether an idea is worth building.
---

# idea2spec: score

Gate A answers: "is this worth specifying and running the cheapest test?" It does not mean "validated". Gate B (`--after-test`) answers: "did the test pass the thresholds we set beforehand?"

Inputs: `interview.md` and `00-evidence.md` in the idea folder. If either is missing, go back to the interview or research skill.

## Order of work (do not reorder)

1. **Red-team first.** Write the strongest case for KILL in 5 to 8 lines before looking at any score: why this fails, who already does it better, what breaks. Full mode: use the `red-team` agent with the ledger. Lite mode: do it yourself and say so. Then write a pre-mortem: "six months later this failed; the three likeliest reasons are...".
2. **Score** each dimension using `references/rubric.md`. Every line has: score, evidence level (E0 to E3), claim IDs, one counter-argument, confidence.
3. **Apply caps and vetoes** from the rubric. Caps first, then totals, then vetoes.
4. **Audit.** First write the scorecard and totals to `01-decision.md` as a draft, with the header line "Status: draft, pre-audit". Full mode: start the `reviewer` agent with the idea folder path, naming `00-evidence.md`, `interview.md` and the draft `01-decision.md`; it recomputes every cap and the total from the evidence alone. Lite mode: recompute from scratch yourself in a second pass. Where totals differ, the lower score wins on every dimension. Report any difference, and show the user any difference of more than 1 point in the total.
5. **Verdict** using the table in the rubric. Turn the draft `01-decision.md` into the final file from `templates/decision.md`, remove the draft header line and add the reviewer's numbers to the Total line.
6. **Name the cheapest test** with cost, days, the signal measured and pass/fail thresholds written down now, before the test runs. Follow the test design rules in `references/rubric.md`: a behaviour or money signal, a minimum sample, a fail line, one call to action, and a free conversation test first when one exists.

## Honesty rules

- A score of 2 needs a READ source and the right evidence level. Without a source the cap applies; do not argue around it.
- Do not let how keen the user sounds raise a score. Interview answers count as E0 unless they describe observed behaviour or commitments.
- Competition by itself is not a penalty. Penalize only a missing wedge or a saturated, copyable offering.
- Per-type rules (platform terms, disclosure, kids, IP) come from `references/risk-checklists.md`. A hard blocker is a veto.

## CLARIFY handling

At most 3 questions per round, each naming the dimension, why it blocks the verdict, and the cheapest evidence that would answer it. At most 2 rounds. Re-scoring needs new evidence, not rephrased answers. After round 2 offer: KILL, PARK, or **Revisit** (the user decides: another search or a deep search, then a new batch of up to 3 questions, logged in `interview.md`).

## Gate B: `--after-test`

1. Read the test result from the user (numbers, quotes, dates) and the pre-registered thresholds in `01-decision.md` or `spec.md`.
2. Compare to thresholds only; do not move them. A test that missed its threshold sets demand to 0 and the verdict to KILL, unless the user records a new idea with a new test.
3. Re-score demand (2 needs E2 or better) and recompute economics with the real numbers.
4. Verdict: **PROCEED** (demand 2 at E2 or better, economics at least 1, no new veto; say "validated" only with E3 money evidence), **ITERATE** (one more test, once, new thresholds written first), or **KILL**.
5. Append a `## Gate B` section to `01-decision.md`. Never edit the Gate A section.

## Lite mode

Cap any GO at "GO (unaudited)" and say why in the decision file.
