# Prompt Cheat Sheet

Prompting is a skill. These patterns work. Copy, adjust, use.

---

## The Basics

### Give Claude a role
```
You are a [role]. Help me [task].
```
Example:
```
You are a product manager. Help me write a one-page brief for a new feature.
```

### Give Claude context before the task
```
Here's my situation: [context].
Here's what I need: [task].
Here's what I've already tried: [attempts].
```

### Ask it to think before answering
```
Before giving me an answer, think through this step by step.
What are the key considerations? Then give me your recommendation.
```

---

## Planning Mode

Use these before you build anything.

**Break down a goal:**
```
I want to [goal]. I have [time/resources/constraints].
Help me break this into clear steps. Start with the most important thing.
```

**Identify your blind spots:**
```
I'm planning to [plan]. What am I probably not thinking about?
What could go wrong? What questions should I be asking?
```

**Choose between options:**
```
I'm deciding between [option A] and [option B] for [goal].
My priorities are [priority 1] and [priority 2].
Which would you recommend and why?
```

---

## Building and Creating

**Start a project:**
```
I want to build [thing]. I'm not technical / I know [skill level].
Let's start simple. What's the minimum version that would be useful?
```

**Iterate on something:**
```
Here's what I have so far: [paste work].
What's the weakest part? Fix that first.
```

**Unstick yourself:**
```
I'm stuck on [problem]. Here's what I've tried: [attempts].
Don't solve it for me yet - help me think through what I might be missing.
```

---

## Writing and Communication

**Write anything:**
```
Write a [type of content] for [audience].
Tone: [formal/casual/direct/friendly].
Key message: [what you want them to walk away with].
Keep it under [length].
```

**Improve existing writing:**
```
Here's what I wrote: [paste].
Make it clearer and more direct. Don't change the meaning.
Show me the before and after.
```

**Summarize:**
```
Summarize this in 3 bullet points for someone who has 30 seconds: [paste content]
```

---

## Working in a Pod (Group)

**Divide tasks:**
```
We have a team of [N] people and [time] to build [thing].
Help us divide the work so no one is blocked waiting on someone else.
```

**Sync up mid-session:**
```
Person A built [thing]. Person B built [thing]. Person C built [thing].
How do we connect these into one coherent output?
```

**Prepare the presentation:**
```
Here's what our pod built today: [describe or paste].
Help us tell the story in 3 minutes. What's the hook, the demo, the key takeaway?
```

---

## Multi-AI Workflow - When to Use What

| Task | Best Tool |
|------|-----------|
| Deep reasoning, long documents, coding | Claude |
| Image generation | ChatGPT (DALL-E) or Gemini |
| Current news and real-time info | Grok or Gemini |
| Searching the web during a task | Gemini or ChatGPT with browsing |
| Turning your output into a podcast/presentation | NotebookLM |
| Building something in your terminal | Claude Code |

---

## Prompts That Almost Always Work

```
What am I missing?
```

```
Play devil's advocate. What's wrong with this approach?
```

```
Explain this like I'm smart but new to this topic.
```

```
Give me the 20% of knowledge that covers 80% of use cases for [topic].
```

```
What would an expert in this area do differently than what I just described?
```

---

Back to [main README](../README.md)
