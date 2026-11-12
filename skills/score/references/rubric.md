# Rubric (Gate A)

Seven dimensions, each 0 to 2. Maximum 14.

| # | Dimension | 0 | 1 | 2 |
|---|---|---|---|---|
| 1 | Audience and problem | vague persona or solution-first | named segment plus a problem | segment, trigger, current workaround, why it fails, where to reach them |
| 2 | Demand signal | none or opinions only | people already pay, search or watch (E1 proxies); rivals with verifiable traction | observed behaviour or commitments from the target audience (E2 or E3) |
| 3 | Differentiation and timing | copy of a saturated offering | a wedge or niche | wedge, a reason it works now, and something hard to copy |
| 4 | Feasibility and operator fit | beyond the user's skills, time or budget | doable with a stretch | within skills, first test in 8 weeks or less, ongoing workload stated |
| 5 | Economics | no path where revenue exceeds cost | a path using optimistic but sourced numbers | a path at median benchmarks, with the one-line calculation shown |
| 6 | Risk and rules | breaks a platform or legal rule (veto) | manageable with known mitigations | low exposure |
| 7 | Cheapest test | no test under about $500 and 2 weeks could falsify demand | a test exists but its signal is only opinions or email sign-ups | pre-written pass/fail on a behaviour or money signal, with cost and days |

Economics is scored against median benchmarks. Top-quartile numbers need evidence that this builder can reach them.

**Tie rule.** When an answer fits two columns of a row, score the weaker column and write "scored on the weaker half: <which half>" in the counter-argument cell. Example: the persona "everyday internet users" fits column 0, a named workaround fits column 1, so audience scores 0 and the clarify question asks for one named segment.

## Evidence levels and caps

- **E0**: assumption, model inference, or an interview answer with no source. Caps any dimension at 1, and caps demand and economics at 0.
- **E1**: cited desk evidence that was READ (competitor pricing page, store ratings count, search results showing people already pay). Allows demand and economics up to 1.
- **E2**: first-party behaviour from the target audience (conversations ending in a commitment, landing-page conversion, test-video retention). Allows demand 2.
- **E3**: money (pre-order, paid pilot). Required before anyone says "validated".

Claims labelled RECALLED or UNVERIFIED never lift a score above the E0 cap.

Levels needed for a score of 2: demand needs E2. Economics needs E2 as well (a first-party price or conversion result) and the calculation shown; E1 desk numbers allow economics 1 at most. Risk 2 needs READ platform or legal pages (E1). Cheapest test 2 needs a pre-written threshold (see the test design rules); no evidence level.

## Demand: commitment signals against compliments

For desk research (E1), separate what people did or paid from what they said:
- **Commitment signals** (count toward demand 1): a rival's paid plan with a price page, a waitlist with a deposit, job posts or freelancer gigs for the workaround, people paying for a workaround, a thread where someone asks where to pay or says they switched.
- **Compliments** (E1 at best, never a score of 2): likes, upvotes, stars, "I'd use this", "great idea", sign-ups with no price shown.
- A rival's existence proves a market exists, not that this audience pays for this idea; say so in the counter-argument.
- Demand 2 still needs E2 evidence from the target audience: a commitment or a next step from a real person.
Basis: compliments are cheap and commitments cost the other person something, so only commitments or next steps count as demand.

## Economics: priors and the range test

Public benchmarks conflict by definition (for example free-to-paid against trial-to-paid, different sample sizes and years). Do not average them and do not pick one silently.
- **Prior hierarchy:** (1) the closest rival's own published numbers (pricing page, public stats); (2) a primary report from a company that owns the data, in the same category; (3) a secondary blog only if it names its primary source, and then trace it; (4) otherwise write "no benchmark found", score economics at most 1, and list the missing cost data under Open questions.
- **A number counts as a benchmark "median"** only if the source says median, names what it divides by (the denominator), and is dated within 24 months. Otherwise it is an unclear statistic and counts as E0.
- **Range test:** show the one-line calculation at a low, a median and a high value taken from the benchmark ledger. Profitable at the median and not catastrophic at the low: that supports a score of 1 (and 2 only with E2 evidence). Profitable only at the high: score 0 or 1.
- **Unknown inputs become the test:** any economics input at E0 must appear as something the cheapest test will measure.

## Verdict table (Gate A)

| Verdict | Condition |
|---|---|
| **KILL** | any veto: risk 0 with a hard blocker; economics 0 at E1 or better; total 6 or below; or the red-team found a fatal flaw that no stated mitigation answers |
| **GO** ("worth testing") | total 10 or more of 14; audience, demand, feasibility and economics each at least 1; demand and economics at E1 or better; risk at least 1; cheapest test at least 1; the red-team counter-case was written and the idea survived it |
| **CLARIFY** | everything else |

## Verdict words (definitions only; the rules are above and in the score skill)

| Word | Gate | Meaning |
|---|---|---|
| GO | A | Worth specifying and running the cheapest test. Not "validated". |
| GO (unaudited) | A | A GO from lite mode, where one model did research, scoring and audit. |
| CLARIFY | A | Not enough evidence to decide; up to 3 questions per round, at most 2 rounds. |
| KILL | A or B | Stop. A successful outcome of validation. |
| PARK | A | The user's choice after two CLARIFY rounds with no new evidence: keep the files, write no spec, re-enter only with new evidence. |
| PROCEED | B | The pre-set test thresholds were met (demand 2 at E2 or better, economics at least 1, no new veto). "Validated" only with E3 money evidence. |
| ITERATE | B | One more test, once, with new thresholds written first. |

The number 10 is a starting guess, not a proven threshold. It should be back-tested on 20 to 30 past ideas.

After two CLARIFY rounds with no new evidence the verdict becomes KILL or PARK (the user chooses), unless the user triggers a Revisit that brings new evidence.

## Test design rules (for the cheapest test and score 2 on dimension 7)

A test scores 2 only when all of these are written before it runs:
- **Signal:** a behaviour or money signal, not a compliment. A sign-up or email is the weakest form ("leaving an email is cheap"); a click on a priced buy button, a booked call, a deposit or a pre-order is stronger.
- **Numbers:** cost, days, the minimum number of visitors or conversations, a pass threshold and a fail threshold, with a check date. Results between the two lines are "inconclusive", not a pass.
- **One call to action** per test, and a stated traffic source. Warm traffic (your own followers, a forum you post in) gives an upper bound, so say so and set the threshold higher than for cold traffic.
- **Free test first** when one exists: 5 to 8 short conversations about the last time the problem happened and what the person did, ending in a commitment or a next step (a pilot, a waitlist with a stated price, an introduction). Ask about specific past events, not hypotheticals.

Rules of thumb for landing-page tests, from one author (https://kromatic.com/real-startup-book/2-evaluative-market-experiments/value-proposition-test/landing-page-smoke-test/, READ 2026-11-11, not a controlled study): at least 200 unique visitors before reading a result; email sign-up 5 to 15% from targeted paid search, above 10% strong; a click on a simulated purchase button 1 to 3% of paid visitors is a good signal. Cite these as "vendor rule of thumb" and say when your threshold differs and why. Do not present them as facts about this idea.

## Always

Name the cheapest test, with cost, days, signal and thresholds, whatever the verdict.
