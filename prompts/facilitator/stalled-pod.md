# Stalled Pod Prompt

When a pod hasn't committed anything in 30+ minutes or seems stuck on ideation, paste this in their Discord channel or hand it to the pod leader.

---

## Generic version (works for any pod)

```
Paste this into your terminal:

"I'm at a workshop with [N] other people. We have [describe what you decided to build - or if you haven't decided yet, tell me the most painful thing that wastes your time at work]. I need something working and demo-able by end of today.
1. If we haven't decided yet: ask me 3 quick questions then suggest the fastest thing we can build that solves a real problem.
2. If we have decided: skip planning - start building the simplest version that actually works right now.
3. After every piece is done, save it to our GitHub repo."
```

---

## Custom version (when you know what they're building)

Read their repo first (`gh api repos/ORG/pod-X/contents`), then tailor:

```
[Pod name] - [project name] is [status description]. Here's a prompt to [specific next step].

Paste this into your terminal:

"[Context about what they've built so far]. [Specific instruction about what to do next]. [Constraint to keep scope small]."
```

**Example from the first workshop (Pod D - GiftMaster):**

```
Pod D - your app builds perfectly and the server starts in under 2 seconds. The only thing blocking it is two missing env vars. Do this right now:

1. Open .env.local in your repo root
2. Replace the placeholder lines with your actual Supabase values
3. Save the file and run: npm run dev

That's it. App loads instantly after that.
```
