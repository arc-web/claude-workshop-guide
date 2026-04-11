# Pod Kickoff Guide

Pjotr just handed it over to you. Here's exactly what to do.

---

## Step 1 - Pick Your Problem (15 minutes max)

This is the most important decision your pod makes today. Don't overthink it.

**Go around the table. Each person answers two questions:**
1. What's something at work or in life that wastes your time or frustrates you?
2. Who else has this same problem?

Write every idea down in your `notes.md` as people share. Don't judge yet, just collect.

**Then pick one.** Use these filters:

| Question | What you want |
|----------|--------------|
| Can AI actually help with this? | Yes - it involves information, writing, decision-making, or repetition |
| Can we make something real in 4 hours? | Yes - it's specific, not "fix everything" |
| Does more than one person in the pod care? | Yes - shared pain means shared motivation |
| Is there a clear person this helps? | Yes - "salespeople", "HR managers", "my team" |

**If your pod can't agree:** the leader calls a vote. Majority wins. Move on. A decided problem is better than a perfect one you haven't picked yet.

---

## Step 2 - Define It Clearly

Before you build anything, write this down in your `notes.md`:

**The problem in one sentence:**
> "[Type of person] wastes time / struggles with [specific thing] because [reason]."

Example:
> "Our sales team wastes 2 hours a day writing follow-up emails from scratch because every client situation is slightly different."

**What the solution does:**
> "A Claude prompt that takes a few bullet points about the meeting and generates a personalised follow-up email in under 30 seconds."

**How you'll show it works:**
> "We'll demo it live - someone on our pod describes a real meeting, we run the prompt, and read out the result."

If you can write all three of these, you're ready to build.

---

## Step 3 - Divide the Work

Once you have your problem defined, split into roles so nobody is waiting on anyone else.

**Suggested split for a 5-6 person pod:**

| Role | What they do |
|------|-------------|
| Builder | Works in Claude Code or Claude web to build the actual solution |
| Prompter | Writes and tests the prompts - focused on making the AI output great |
| Researcher | Finds examples, context, data that makes the solution better |
| Documenter | Fills in notes.md as the team builds - owns the presentation story |
| Presenter | Prepares how to demo it at the end - practices the narrative |

One person can do two roles. That's fine. What matters is everyone has something to do.

---

## What Your Repo Should Have

By the end of today, your pod repo should tell the whole story. Here's what a great repo looks like:

### The README (your front page)

This is the first thing Pjotr and everyone else sees when they open your repo. Update it with:

- **What you built** - one sentence, plain English
- **The problem it solves** - who it helps and why it matters
- **How to use it** - what someone does to get the output
- **A quick demo or example** - paste a sample input and the output you got

### The notes.md (your work log)

Fill this in as you go, not just at the end. It should have:

- The problem statement you agreed on
- The approaches you tried (including the ones that didn't work)
- What you actually built
- The prompts that worked best
- What you'd do next with more time

### Your actual work files

Whatever you built goes in the repo:
- A prompt? Paste it in as a `.md` or `.txt` file
- A script or tool? The code file
- A doc or template? Upload it
- A screenshot of the output? Drag it in

The repo should be a complete picture - someone who wasn't in the room should be able to open it and understand what you built.

---

## Step 4 - You Have Your Idea. Do This Right Now.

The moment your pod agrees on a problem, stop talking and do these five things in order. This is the bridge from "we have an idea" to "we're building."

### 1. Fill in notes.md right now

Don't wait. Open your `notes.md` and write the three lines from Step 2:
- The problem in one sentence
- What the solution does
- How you'll show it works

If you don't write it now, you'll spend time later trying to remember what you agreed on.

### 2. Update your pod README

Find the line in your `README.md` that says "What We're Building" and fill it in. One sentence. Plain English. This is what Pjotr sees when he opens your repo at the end.

### 3. Tell Claude Code your idea

Open Claude Code and paste this:

```
Our pod is building [describe what you're making] for [who it helps].
We have about [X] hours left. What's the single first thing we should build
to have something working to demo?
```

Claude Code will read your CLAUDE.md file and know your team's context. Give it the idea and let it help you start.

### 4. Lock in who does what

Go around the table right now and confirm who has each role. Say it out loud:

| Role | Name |
|------|------|
| Builder - runs Claude Code, builds the thing | |
| Prompter - writes and tests the prompts | |
| Documenter - keeps notes.md updated as you go | |
| Presenter - owns the demo at the end | |

One person can hold two roles if your pod is small.

### 5. Set a 30-minute checkpoint

Look at the clock right now. Add 30 minutes. That's your first checkpoint.

By then you need something - anything - that actually runs. It doesn't have to be good. It just has to work. If you don't have something working in 30 minutes, your idea is too big and you need to cut it down.

---

## The Presentation

At the end, each pod gets a few minutes. Structure it like this:

1. **The problem** - what it is, who has it, why it matters
2. **The solution** - what you built and how it works
3. **The demo** - show it working live (or show a screenshot/output if live is risky)
4. **What's next** - if you had a week, what would you add?
5. **What surprised you** - one honest thing you learned

Keep it tight. The demo is the most important part. Let the work speak.

---

Back to [main README](../README.md)
