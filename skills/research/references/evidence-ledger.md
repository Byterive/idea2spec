# 00-evidence.md format

```
# Evidence: <idea slug>
Retrieved: <date>   Mode: full | lite   Privacy: generalized | exact | no web
Counts: READ <n> | RECALLED <n> | UNVERIFIED <n>

## Competitors
| Name | URL (opened?) | What it is | How it earns | Price | Traction signal | Claim IDs |

## Claims
| ID | Claim | Label | Source URL | Fetched? | Original source | Retrieved | Verbatim quote | Tier |
| E-001 | ... | READ | https://... | Y | same page | 2026-10-21 | "..." | official |

## Benchmarks (only when the idea needs priors for economics)
| Metric | Value | Definition and denominator | Segment | Sample size | Year | Original publisher | URL | Fetched? | Tier |

## Conflicts
| Claim | Source A: value, definition, date | Source B: value, definition, date | Likely reason (denominator, year, segment) | Decision |

## Disconfirming searches
| Query (as sent) | Result summary | Claim IDs |

## Evidence levels reached
E0 assumption | E1 cited desk evidence | E2 first-party behaviour | E3 money
Highest per dimension: audience <E?>, demand <E?>, differentiation <E?>, feasibility <E?>, economics <E?>, risk <E?>, test <E?>

## Gaps
<what could not be verified and why>
```

Tiers: official (the product's or platform's own page), secondary (news, reviews), vendor (a company describing itself or rivals), aggregator (directory or listing).

Fetched? is Y only if you fetched that exact URL in this run and copied the quote from the fetched text; N for a URL that came from a search result list or from memory; "pasted" for text the user pasted. A row with Fetched? N or a missing quote cannot be READ.

Extract caution: the built-in fetch tool may return a model-written extract of a page, not its raw text, so a "verbatim quote" can be a paraphrase (found in test run 002, 2026-11-11). Ask the fetch for the exact sentence containing the figure, mark a quote that is clearly a paraphrase "(extract)" in the quote cell, and let the spot-check re-open the claims the verdict rests on. A key number that exists only in an extract and was not re-opened stays READ but is named in Gaps.

Original source: for a secondary claim (a blog, a directory, a news story quoting a number), name who first published it and open that page. If the trace fails, the claim is UNVERIFIED. "Same page" is enough for an official page.

Source count rules (design choices, not an established standard):
- A rival exists, or its price: 1 official page READ.
- A demand or traction number: one official or store page READ plus one independent corroboration; otherwise flag "single-source" and cap demand at 1.
- A market-size or benchmark number: 2 independent sources that do not cite each other, or one primary report READ. Blogs that cite each other count as one.
- A failure or shutdown story: prefer a first-hand source (an official notice or the founder's own post); an aggregator is a lead only.

Conflicts: list both values with their definitions and dates, say the likely reason, and decide. Use the lower value for scoring unless one source is primary. Never average.

Labels: READ means opened this session and the quote is on the page. RECALLED means from memory. UNVERIFIED means weak, conflicting, blocked, seen only in a search snippet or summary, or summarized without a quote. Only READ claims can raise a score above 1.
