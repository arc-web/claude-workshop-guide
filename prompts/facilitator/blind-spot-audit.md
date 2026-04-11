# Blind Spot Audit Prompt

Share this with all pods mid-build so they can find demo-breaking issues before the presentation.

---

## General version (works for any project)

```
Paste this into your terminal:

"Do not change anything yet. First, audit this codebase for blind spots and edge cases only.

Look for:
- What happens when a user does something unexpected (blank input, weird characters, double-clicking, going backwards)
- What breaks if the data is missing, empty, or malformed
- What a user would try first that currently doesn't work
- Anything that looks finished but would embarrass us in a live demo

For each issue you find: rank it HIGH (breaks the demo), MEDIUM (looks bad but recoverable), or LOW (nice to fix if time allows).

Only fix the HIGH ones. Tell me what they are before you touch anything."
```

---

## Custom version (tailor to specific app)

Read the pod's repo, identify their actual features, then reference specific failure modes:

```
"Audit [app name] for demo-breaking issues only. Specifically check:
- [Feature-specific edge case 1]
- [Feature-specific edge case 2]
- [Feature-specific edge case 3]
- [UI state that could look broken]
- [Input that could crash the flow]

Rank each HIGH / MEDIUM / LOW. Fix HIGH only."
```

**The key phrases doing the work:**
- "do not change anything yet" - stops Claude Code from refactoring
- "fix HIGH only" - keeps it surgical
- "tell me what they are before you touch anything" - gives the person a chance to decide
