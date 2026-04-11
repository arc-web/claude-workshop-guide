# Claude Code Quickstart

Claude Code is Claude in your terminal. You type, it builds. This guide gets you from zero to running in under 10 minutes.

---

## Step 1 - Install

You need Node.js first. Check if you have it:

```bash
node --version
```

If you get a version number (v18 or higher), skip to Step 2. Otherwise install Node from https://nodejs.org (download the LTS version).

Then install Claude Code:

```bash
npm install -g @anthropic-ai/claude-code
```

---

## Step 2 - Get Your API Key

1. Go to https://console.anthropic.com
2. Sign in or create an account
3. Click **API Keys** in the left sidebar
4. Click **Create Key**, name it something like `workshop`
5. Copy the key - it starts with `sk-ant-...`

> Keep this key private. Don't paste it in Discord or share it in screenshots.

---

## Step 3 - Authenticate

In your terminal:

```bash
claude
```

It will prompt you for your API key. Paste it and press Enter.

That's it. You're in.

---

## Step 4 - First Commands to Try

Once Claude Code is running, try these:

```
> help me understand what's in this folder
```

```
> create a simple HTML page that introduces me
```

```
> explain what this code does: [paste any code]
```

```
> I want to build [describe your idea]. Help me plan it first.
```

---

## How Claude Code Works

- You talk to it in plain English
- It reads your files, writes code, runs commands - with your permission
- Type `/help` inside Claude Code to see all commands
- Press `Ctrl+C` to exit

---

## Plan Mode

Before jumping into building, use Plan mode to think through what you're making:

```
> /plan [describe what you want to build]
```

Claude will map out the approach before writing a single line of code. This saves a lot of backtracking.

---

## Tips for Today

- **Be specific** - "build me a todo app" is worse than "build me a simple to-do list as a webpage that remembers your tasks even if you close the browser"
- **Iterate** - don't expect perfection on the first prompt, push back and refine
- **Ask why** - if Claude suggests something you don't understand, ask it to explain before moving on
- **Use your pod** - share what's working with your group, someone always has the better prompt

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `command not found: claude` | Run `npm install -g @anthropic-ai/claude-code` again |
| API key not working | Double-check you copied the full key including `sk-ant-` |
| Slow responses | Normal during high traffic - just wait |
| Confused output | Start fresh: describe your goal clearly from scratch |

---

Back to [main README](../README.md)
