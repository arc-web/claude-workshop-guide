# Rate Limit Workaround

Share this proactively during the build phase - don't wait for someone to hit a limit and get stuck.

---

## For all pods

```
If Claude Code slows down or stops responding, don't wait. Open claude.ai in your browser and keep building there. Here's the flow:

1. Open claude.ai - it's a different usage pool, works even when Claude Code is busy

2. Tell it what you're building:
   "I'm building [describe your tool]. Here's where we're up to: [paste your notes or current code]. Help me plan the next steps and mock up the frontend."

3. Ask it to generate your frontend:
   "Build a clean frontend for [our tool]. It needs: [describe inputs, outputs, layout]. Output a single self-contained HTML file I can paste into my project."

4. When Claude Code is ready again, paste the code in:
   "Here's the HTML file Claude web built for our frontend [paste it]. Now wire up the logic so the button actually calls [our process] and shows results in the output section."

Two tools, one team. Designer uses Claude web for mockups, Builder uses Claude Code for logic. Nobody waits.
```
