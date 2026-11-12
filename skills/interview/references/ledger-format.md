# interview.md format

Append-only. Top of file:

```
# Interview: <idea slug>
Created: <date>
Depth: quick | standard | deep
Search privacy: generalized | exact wording | no web
```

Then one entry per answer:

```
- [Settled] Q6 Who: <answer in the user's words>
- [Clash] Q8 Evidence vs Q10 Money: user says people pay, but evidence is "opinions only"
- [Unknown] Q9 Timing: user does not know yet
- [Parked] <item>
```

Rules:
- Settled: the user said it and it is not contradicted.
- Clash: two answers disagree, or an answer disagrees with research. Keep both lines.
- Unknown: unknown. These become clarify questions or assumptions in the spec.
- Out of scope: the user excluded it.
- Assumptions you added yourself are marked `[Assumed by assistant]` and never count as evidence.
- Revisits get a header line: `## Revisit <n>: <date>, new evidence: <what>`.
