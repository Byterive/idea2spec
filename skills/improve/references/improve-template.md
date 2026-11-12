# 02-improve.md format

Write this file in the idea folder after the user says yes. Fill every field. Write UNKNOWN where nothing is known; never invent. Every sentence about the market, a rival, a segment, a price or a complaint ends with a ledger ID (E##, I##) or [Assumption].

```
# Improve: <idea slug>
Date: <date>   Based on: 01-decision.md (<verdict>, <total>/14)   Run mode: full | lite (unaudited)
Search privacy: <as in interview.md>

## Diagnosis
| Dimension | Score | Weakest assumption | Lens |

## New evidence (Improve <n>)
Rows I01... are in 00-evidence.md. Counts: <n> READ, <n> UNVERIFIED. Searches that found nothing: <list>.

## Candidates
(at most 4, ranked by evidence strength first, then test cost)

### C1 <name>   Type: wedge | segment pivot | need pivot | zoom-in | price | positioning | adjacent
- Change in one line: <what differs from the killed idea; what stays the same>
- Failed assumption it answers: <dimension and claim ID from the scorecard>
- Segment, trigger, current workaround: <text with IDs or [Assumption]>
- Wedge or gap: <text>. Support: <READ IDs>. Rival pages opened: <IDs and how many>. Status: supported | not yet a wedge
- Positioning (alternatives, unique attribute, value, target, category): <short, with IDs or [Assumption]>
- Price hypothesis: <number> anchored on <IDs>. Cost line: known | UNKNOWN
- Riskiest assumption: <one sentence>
- Cheapest test: <test>. Cost <n>, days <n>, signal <a commitment signal>, minimum sample <n>, PASS at least <n>, FAIL below <n>, traffic source, check date. Benchmark IDs used and why the threshold differs from them
- Why this may still die: <IDs>
- Risks carried over from the original scorecard: <list>
- Paper score (hypothetical, not a verdict): audience x, demand x, differentiation x, feasibility x, economics x, risk x, test x = total. Cannot exceed <n> until <evidence>
- Evidence strength: strong | moderate | thin (number of READ rows that carry the wedge)

## Stay killed
The strongest case that the original idea and every candidate should stop, and what the saved time and money are best used for. If no candidate has a supported wedge, say so here first.

## Ideas with no evidence yet
One line each, no scoring.

## Not recommended and why
Candidates the ledger rules out, with IDs.

## Audit
Sentences without an ID or [Assumption]: <n, list>. Wedges resting only on UNVERIFIED rows: <list>. Audited by: reviewer agent | same model, unaudited.

## Next step (the user's choice)
Test one card | re-run Gate A as a Revisit on one card (new evidence required) | park | stop
```

Rules for the file:
- No praise language. The stay-killed section gets the same effort as a candidate.
- The paper score is capped by the rubric's evidence caps and never reaches GO. Motive (what the user wants to try) is recorded as motive, never as evidence.
- Do not edit `01-decision.md`. Earlier thresholds are not moved; new thresholds are written here before any test.
