---
name: interview
description: Interview the user about a new idea before any research or scoring. Asks a scaled set of questions in small rounds, keeps an append-only ledger of answers, and ends with a summary and three closing checks. Use when the user wants to explain, sharpen or scope an idea, or when the run skill reaches the interview phase.
---

# idea2spec: interview

Goal: collect enough from the user to score seven dimensions (audience, demand, differentiation, feasibility, economics, risk, cheapest test) without wearing them out.

## How to ask

- Use the question tool (AskUserQuestion) with 3 or 4 questions per call, 2 to 4 options each, a header of at most 12 characters, and free text through "Other". If the tool is missing, use the numbered text fallback in `../run/references/fallbacks.md`.
- Put the bank number in every question's text or header ("Q6 Who") and tell the user to reply by number. Never map unnumbered answers to questions by order; if a reply has a number outside the round or fewer answers than questions, ask which question it was for.
- Ask the most consequential questions first. Skip anything the user already answered; do not re-ask.
- Ask about specific past events and what people did, not hypotheticals ("when did you last...", "what do they use today"). Do not praise the idea.
- Questions are in `references/question-bank.md`. Type-specific extras are in `references/type-addons.md`; read only the section for the chosen type.

## Recommended answers

- **Design and scope questions** (MVP shape, platform, depth of research, which test): put your suggested option first, mark it "(Recommended)", and tell the user to override freely.
- **Questions about facts in the user's world or market** (who the customer is, whether people pay, how much): do not pre-select a recommendation. Put the evidence-honest options first: "I have evidence (describe it)", "I'm assuming this", "I don't know yet". If you offer a typical answer at all, put it last and label it "Typical guess, unverified". A suggested answer is how a model invents evidence, so it must never be scored as evidence.

## Depth and question count

First ask the user for the interview depth (default standard). "Depth" is the size of the interview; "mode" means only full or lite and is asked by the run skill:

| Depth | Questions | Use for |
|---|---|---|
| Quick | 7 | a hobby idea or a first look |
| Standard | 12 | a side income idea |
| Deep | up to 16 | a full-time business or client work (not a throwaway or hobby test) |

Recommend standard unless the user says full-time business or client work, and recommend quick for a throwaway test idea. Ask at most 4 questions per round and say how many rounds remain (for example "round 2 of 4"). Question numbers refer to the bank. Quick: 1, 5, 6, 8, 10, 13, 14. Standard: 1 to 8, 10, 12, 13, 14. Deep: all 15 plus one type add-on (logged as A1, A2, ... from `references/type-addons.md`). Questions 13 (rules) and 14 (test) are in every mode because risk and the cheapest test are always scored. Question 1 is answered in the run skill's intake phase and question 5 is the privacy question, so they are not asked twice. The user can say "stop" at any time; then mark missing dimensions as unscored.

## The privacy question (always ask it, before any web search)

Ask it exactly in this spirit, with the bold parts:

> **Before I search the web: how much of your idea may I put in search queries?**
> - **Generalized only (default, recommended):** I search category terms such as "habit tracker app for shift workers". **Your product name, unique mechanic and identity are never sent to a search engine.** Results may miss exact lookalikes.
> - **Exact wording allowed:** I may search your idea's own words and name. **Those words go to the search service and may be logged by it.** You get closer matches.
> - **No web search:** **Nothing leaves this chat.** The gate then runs on what you tell me, every claim is labelled unverified, and the best possible verdict is CLARIFY.

Record the choice at the top of `interview.md`.

## The ledger

Append every answer to `interview.md` using the labels in `references/ledger-format.md`: Settled, Clash (two answers disagree), Unknown, Parked (useful, but not for now). Never rewrite earlier entries; add a new line instead.

## Finish

1. Show a short summary of the idea in our own table form: who, problem, today's workaround, what you assume, money path, stop rule. Mark each item Settled, Assumed or Unknown.
2. Ask three closing checks as one round (numbered, with "Other" for free text):
   - **C1 Weakest point:** "Which line in this summary are you least sure of?" Options: each Assumed or Unknown item, plus "None".
   - **C2 Missing:** "What did I not ask that could change the verdict?" Options: "Nothing", "Something (describe it)".
   - **C3 Go-ahead:** "Start research on this summary?" Options: "Yes, start", "Fix something first (say what)".
   Log the C1 and C2 answers in the ledger (Unknown if the user names a gap).
3. STOP until the user answers C3 "Yes, start". Never take a yes to C1 or C2 as the go-ahead.
4. Report "ready to research" to the run skill.
