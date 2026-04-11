# Mistakes We Made and How to Avoid Them

Every mistake from the first workshop run (April 10, 2026) and the fix.

---

| # | Mistake | What happened | Prevention |
|---|---------|---------------|------------|
| 1 | **Used org-level OAuth token** | `gho_` token gave access to everything under the org, not just one repo | Always use fine-grained PATs scoped to single repos with `contents:write` only |
| 2 | **Wrong repo naming** | Initially named repos `stellarph-pod-x`, had to delete and recreate as `claudeconference-pod-x` | Decide naming convention before creating repos. Use format: `eventname-pod-letter` |
| 3 | **All pods got the same roster** | Python dict iteration bug pushed Pod F's roster to all 6 repos | Use explicit per-team data with verification. After any batch operation, check each repo individually |
| 4 | **Created too many pods** | Made 6 pod repos but only 4 groups showed up. Had to archive 2 | Create repos just-in-time based on confirmed attendance, not RSVPs. Archive extras immediately |
| 5 | **Stale references after pod removal** | Main README still said "A through E" after pods E and F were removed | After any roster change, search all files for pod references: `grep -r "pod-e\|Pod E\|through E"` |
| 6 | **notes.md left empty** | Teams built great apps but didn't document. Made presentation prep harder | Prompt teams to fill notes.md mid-session (not just at the end). Share the final-push prompt 30 min before presentations |
| 7 | **bash associative arrays on zsh** | Batch operations using bash arrays failed on macOS zsh shell | Use Python for all multi-repo batch operations. Never rely on bash associative arrays |
| 8 | **SETUP.md had wrong install command** | Documented `npm install` for Claude Code instead of the correct `curl` installer | Read actual tool documentation before writing setup guides. Test every command yourself first |
| 9 | **Shared org token in conversation** | An org-wide OAuth token appeared in chat history during live troubleshooting | Never generate or display tokens in shared contexts. Create tokens in private, distribute via pinned Discord messages |
| 10 | **Pod D overbuilt for a 5-hour session** | Next.js + Supabase + VPS + Redis + agent API - spent time fighting Vercel build errors instead of demoing | Encourage the simplest viable architecture. A single HTML file can be a complete app. Deployment can wait until after the demo |
