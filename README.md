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

It came out of a root cause analysis of a project whose plan was grilled from the user's own spreadsheet. The questions that mattered surfaced only during implementation, and they traced back to five gaps in the grilling:

- The spreadsheet's layout was read as the domain, although it only reflected what fitted on screen.
- An unexplained label went into the model undefined.
- A proposed mechanism was accepted without asking what it was for, and a simpler one met the real goal.
- "Anything goes" about the stack hid firm preferences.
- The agreed rules were never checked against the spreadsheet's history, so contradictions surfaced late.
