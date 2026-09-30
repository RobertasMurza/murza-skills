---
name: grill-rca
description: Grill a plan down to its root needs. Ladders every mechanism to its goal, treats the user's own artifacts as workarounds, and closes on a worked example and a back-test. Writes CONTEXT.md and ADRs as it goes.
disable-model-invocation: true
---

Call the Skill tool for "grilling" and "domain-modeling" (from the mattpocock-skills plugin), and run them with the rules below on top. Where these rules and `grilling` differ, these rules win.

## Sources and workarounds

Sort every input before the first round:

- **Primary sources** are documents from the outside world that the plan has to fit: supplier invoices, portals, contracts, API docs, regulations. What you find in them is fact; look it up yourself, as `grilling` says.
- **Workarounds** are things the user built to cope today: spreadsheets, notes, scripts, old code. Their shape records habit and constraints (screen width, tool limits), not the domain.

Everything you observe in a workaround enters the design tree as a question for the user: state the observation and your guess. For example: "The `+2` sits in the night electricity column. Is it a night fee, or just where it fits?" When a workaround shows something a primary source would settle, ask the user for one sample of each kind (one invoice per supplier, one screenshot per portal), then read it.

## Terms

Every term that enters `CONTEXT.md` is defined in the user's words. A term you picked up from a workaround (a column header, an abbreviation) goes to the user as a question before it goes into the glossary.

## Laddering

Requirements arrive as mechanisms: "notify me", "a separate line for", "a checkbox to". Ladder every mechanism, the user's and your own recommendations alike. Ask what it gives them, and repeat until the answer is a goal: an outcome the user wants, independent of any feature. It usually takes two or three rungs. Then derive the mechanism again from the goal, and offer it if it differs. Record the goal in the ADR next to the mechanism, so later changes can be tested against it.

## Indifference and horizon

"Anything goes" and "whatever's easiest" are answers to ladder too. Ask what else the user runs (other projects, databases, deploy tools, libraries they reach for) and what would annoy them if they saw it. Ask once where the thing is heading in a year. Features on that horizon shape today's model: for example, data that will arrive piecemeal calls for drafts.

## Worked example

Before closing, render one concrete case end to end from real data, as its end user will see it: an HTML mockup file for anything with a UI, a filled-in document otherwise. Pick the case that exercises the most decisions, such as a partial period with an unusual charge. Show it and ask for reactions. Every reaction opens a new round.

## Back-test

When history exists (past records in a workaround), run the agreed rules over all of it and compare the result with what actually happened. A throwaway script is fine. Each mismatch goes to the user as a question: is the rule wrong, the history wrong, or is the difference accepted? Record accepted differences in the ADR.

## Done

The session is done when all three hold:

- the `grilling` frontier is empty;
- the user has accepted the worked example with no open reactions;
- every back-test mismatch is explained, or there is no history.

Then confirm the shared understanding with the user, as `grilling` requires.
