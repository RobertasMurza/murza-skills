# murza-skills

Agent skills for Claude Code, packaged as a plugin marketplace.

| Skill | What it does |
|---|---|
| `/murza-skills:grill-rca` | Grills a plan down to its root needs: ladders every mechanism to its goal, treats your spreadsheets and notes as workarounds rather than facts, and closes on a worked example and a back-test against history. Writes `CONTEXT.md` and ADRs as it goes. |

## Install

`grill-rca` builds on Matt Pocock's `grilling` and `domain-modeling` skills, so install both plugins:

```
/plugin install mattpocock-skills@claude-plugins-official
/plugin marketplace add RobertasMurza/murza-skills
/plugin install murza-skills@murza-skills
```

## Why grill-rca exists

It came out of a root cause analysis of a project where the plan was grilled from a spreadsheet. The reviews before implementation raised 87 questions, and the few that mattered traced back to the grilling:

- The spreadsheet's layout was read as the domain. A fee sat in one column only because it fitted there.
- An unexplained column header went into the model undefined.
- A proposed mechanism (a separate "Landlord share" line) was accepted without asking what it was for. The real goal was simply "let me lower what the Tenant pays".
- "Anything goes" about the stack hid firm preferences: a shared PostgreSQL server and particular libraries.
- The rules were never checked against the spreadsheet's history, so contradictions surfaced only during implementation.
