# Fallbacks

## No question tool
Ask the same questions as a numbered list. Number each question with its question-bank number (Q6 stays "6", even if it is the first one in the round) and give lettered options. Say "Reply by number, for example 6b, 7: <text>, 8c, or write your own answer." If a reply has a number not in the round, or fewer answers than questions, ask which question it was for instead of mapping by order. Wait for the reply. Accept short answers such as "6b, 7a, 8: I don't know yet".

## No agent tool (lite mode)
Do the work of each agent in order, in the main conversation:
1. research: one facet at a time, same call limits;
2. red-team: write the case against the idea before scoring;
3. reviewer: after scoring, re-read the evidence and recompute the total from scratch, then compare.
State "lite mode" and cap a GO at "GO (unaudited)".

## No web tools or the user chose "no web search"
Skip the research phase. Record every claim as UNVERIFIED or RECALLED. Demand and economics stay capped at 0, so the best possible verdict is CLARIFY. Tell the user that and suggest the cheapest test so they can gather evidence themselves.

## Search call limits
WebSearch may be capped (about 200 calls per session in Claude Code, shared with agents). Budget about 10 to 15 calls per facet. If a search is refused or limited, record what is missing as UNVERIFIED.

## Interrupted session
If the user returns later, read the existing folder (`interview.md`, `00-evidence.md`, `01-decision.md`), summarize where things stand and resume at the next unfinished phase.
