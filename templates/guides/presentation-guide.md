# Presentation Guide - Turning Your Build Into a Pitch

You built something today. Now you need to show it.

This guide walks you through using NotebookLM to take everything in your pod repo and turn it into a pitch deck and a video - without starting from scratch.

---

## The Story You're Telling

Every presentation today follows the same arc. This is the "Stupid Problem. Smart Solution." format:

| Part | What you say | Time |
|------|-------------|------|
| **The Problem** | What it is, who has it, why it's painful | 30 seconds |
| **The Solution** | What you built and how it works | 30 seconds |
| **The Demo** | Show it working live - this is the most important part | 60-90 seconds |
| **What's Next** | If you had a week, what would you add? | 20 seconds |
| **What Surprised You** | One honest thing you learned today | 20 seconds |

Total: about 3 minutes. Tight, clear, and demo-first.

---

## Step 1 - Make Sure Your Repo Is Ready

Before you open NotebookLM, your pod repo should have:

- `notes.md` filled in - problem, approach, what you built, how to use it
- Your `README.md` updated with what you built and who it helps
- Any code, prompts, or output files committed

If notes.md is sparse, take 5 minutes now and fill it in. NotebookLM can only work with what you give it.

**Tell Claude Code:**
```
Help me fill in our notes.md based on everything we've built today.
Ask me questions about what we made and write the answers into the file.
```

---

## Step 2 - Get Your Repo Content Into NotebookLM

NotebookLM works by reading sources you give it. Here's how to feed it your pod repo:

### Option A - Add the GitHub URL directly (easiest)

1. Go to **https://notebooklm.google.com** and sign in with a Google account
2. Click **New Notebook**
3. Click **Add Source**
4. Choose **Website** and paste your pod repo URL:
   `https://github.com/arc-web/claudeconference-pod-X`
5. Also add your notes.md URL directly:
   `https://github.com/arc-web/claudeconference-pod-X/blob/main/notes.md`
6. Click **Insert**

### Option B - Copy and paste your notes (most reliable)

1. Open your `notes.md` in GitHub
2. Click the **Raw** button to see plain text
3. Select all (`Ctrl+A` or `Cmd+A`), copy
4. In NotebookLM, click **Add Source** > **Copied text**
5. Paste and confirm

Do the same for your `README.md`.

### Option C - Upload a document

1. In Claude Code, say: *"Export our notes.md as a text file I can download"*
2. In NotebookLM, click **Add Source** > **Upload** and upload the file

---

## Step 3 - Generate the Audio Overview (Your Video Pitch)

This is the fastest way to get a polished pitch. NotebookLM will generate a natural-sounding audio discussion of your solution - two AI hosts talking through what you built, why it matters, and what's interesting about it.

1. Once your sources are loaded, click **Audio Overview** in the right panel
2. Click **Generate**
3. Wait 1-2 minutes
4. Press play - listen to it

This becomes your **video pitch audio track**. You can record your screen while it plays and show your demo or repo at the same time - instant video.

**To customize what it covers**, click the pencil icon before generating and add instructions:

```
Focus on: the problem we identified, the solution we built using Claude AI,
and why this matters for [who it helps]. Keep it under 3 minutes.
Make it sound like an exciting startup pitch, not an academic summary.
```

---

## Step 4 - Generate the Pitch Deck Outline

1. In the NotebookLM chat box, paste this prompt:

```
Based on my notes, create a pitch deck outline for our solution.
Use this structure:

Slide 1 - Title: [Solution name] by Pod [X]
Slide 2 - The Problem: What it is, who has it, why it hurts
Slide 3 - The Solution: What we built in plain English
Slide 4 - How It Works: The 3 key steps a user takes
Slide 5 - Live Demo: [placeholder - we'll demo live]
Slide 6 - What's Next: Top 3 things we'd add with more time
Slide 7 - What We Learned: The most surprising thing from today

Write the talking points for each slide in 2-3 bullet points.
Keep everything plain, punchy, and specific to our solution.
```

2. Copy the output
3. Paste it into a Google Slides or Canva deck
4. Add screenshots of your working solution to Slide 3 and 4

---

## Step 5 - Record Your Video Pitch (Optional but impressive)

If you want to submit a video pitch, here's the fastest way:

### On Mac:
1. Press `Shift + Cmd + 5` to open screen recording
2. Click **Record Entire Screen**
3. Open your NotebookLM audio overview and press play
4. While it plays, switch to your GitHub repo or demo and walk through it
5. Stop recording - you have a video

### On Windows:
1. Press `Windows + G` to open Xbox Game Bar
2. Click the record button
3. Same flow as above

### Even faster - just use Loom:
1. Go to **https://www.loom.com** and sign up free
2. Click **New Video**
3. Record your screen while you walk through your demo
4. Share the link - done in 5 minutes

---

## The Presentation Checklist

Before you go up, make sure:

- [ ] `notes.md` is filled in and committed to the repo
- [ ] Your repo README says what you built in one sentence
- [ ] You've done a test run of your demo - know exactly what to click
- [ ] You know who is saying what - divide the 3 minutes across pod members
- [ ] NotebookLM audio overview is generated and ready to play if needed
- [ ] You have a backup plan if the live demo breaks (screenshot or recorded screen)

---

## If Your Demo Breaks

It happens. Here's what to do:

1. Don't panic. Say: *"Let me show you what it looks like when it works."*
2. Show a screenshot you took when it was working
3. Show the output - paste the best result you got into a doc and read it
4. Or describe it: *"Here's exactly what it does - [explain step by step]"*

The judges aren't testing your live demo skills. They're evaluating whether you solved a real problem. The explanation is enough if the demo fails.

---

## Prompt to Help You Prep Right Now

Paste this into Claude Code or Claude web:

```
Help me prepare our pod's 3-minute presentation for the StellarPH Claude AI Workshop.

Here's what we built: [describe it]
Here's the problem it solves: [describe it]
Here's who it helps: [describe it]

Write me a tight 3-minute script following this format:
1. The problem (30 seconds)
2. Our solution (30 seconds)
3. Demo walkthrough narration (60 seconds - I'll do the actual demo while reading this)
4. What's next (20 seconds)
5. What surprised us (20 seconds)

Make it sound confident and real - not corporate. This is a room of builders.
```

---

Back to [main README](../README.md)
