# Using Your Pod Repo

Your pod repo is a shared workspace - like a Google Drive folder but for everything you build today. Here's how to get stuff in and out of it.

---

## Two Directions

**Sending your work up** - you made something on your laptop, you want your pod to see it

**Getting your teammate's work down** - your teammate added something, you want it on your machine

---

## The Easiest Way - GitHub Web Editor

No terminal needed. Good for notes, docs, and text files.

**To add or edit a file:**
1. Open your pod repo on GitHub in the browser
2. Click **Add file** to create something new
3. Or click any existing file, then the pencil icon to edit it
4. Make your changes
5. Click **Commit changes** - that's your save button

That's it. Your whole pod can now see it.

---

## First - Set Up Your Access Token (do this once)

Before you can push anything, your machine needs permission to write to the repo. Your pod has a token for this - it's pinned in your pod's Discord channel and looks like `github_pat_...`.

Once you have it, open a terminal inside your cloned repo folder and run this one command:

```
git remote set-url origin https://YOUR_TOKEN@github.com/arc-web/claudeconference-pod-X.git
```

Replace `YOUR_TOKEN` with the token from Discord, and `pod-X` with your pod letter (pod-a, pod-b, pod-c, or pod-d).

You only do this once per machine. After that, pushing works - no password prompts, no errors.

---

## If You're Using Claude Code

Tell it what you want in plain English - it handles the git commands.

**Get the repo on your laptop (first time only):**
```
git clone https://github.com/arc-web/claudeconference-pod-X.git
cd claudeconference-pod-X
claude
```

**Save your work and share it:**
```
save my work and push it to the repo
```

**Get the latest from your teammates:**
```
pull the latest changes from the repo
```

---

## If You Know Git

```bash
# Get the repo (first time)
git clone https://github.com/arc-web/claudeconference-pod-X.git
cd claudeconference-pod-X

# Get latest from teammates
git pull

# Save and share your work
git add .
git commit -m "describe what you did"
git push
```

---

## The One Rule - No Two People Edit the Same File at Once

If two people edit the same file at the same time without syncing first, GitHub won't know whose version to keep - and you'll have to untangle it manually. Avoid this simply:

- **Divide files by person** - you own your file, they own theirs
- **Or** one person is the designated committer for the pod - everyone passes their work to them and they push it up

Either way works. Pick one and stick to it.

---

## Recommended Pod Flow for Today

1. Pod leader clones the repo at the start
2. Everyone else views the repo on GitHub in their browser
3. One person commits work up every 20-30 minutes as the pod builds
4. Final push before the presentation - that's your deliverable
5. Pjotr opens each pod's repo link at the end

---

Back to [main README](../README.md)
