<div align="center">

<a href="https://arc-web.github.io/claude-workshop-guide/">
  <img src="https://img.shields.io/badge/🎬_Interactive_Presentation-View_Live-7B2FBE?style=for-the-badge&labelColor=0F0F1A&color=7B2FBE" alt="View Interactive Presentation" />
</a>

</div>

---

# Claude Code Workshop - A-to-Z Facilitator Guide

A complete, repeatable playbook for running a hands-on Claude Code workshop for any audience size (10-50 people). Everything from pre-event attendee research to post-event cleanup.

Built from battle-tested patterns running the StellarPH x KMC Claude AI Workshop (April 10, 2026 - Cebu, Philippines - 15 attendees, 4 pods, 5 hours, 4 working apps shipped).

---

## What's in this repo

```
README.md                          <- you are here
FACILITATOR.md                     <- the full A-to-Z playbook
checklists/
  pre-event.md                     <- 2-4 weeks before
  day-of.md                        <- morning of the event
  post-event.md                    <- after the session
templates/
  hub/
    CLAUDE.md                      <- hub repo AI context (templatized)
    SETUP.md                       <- attendee setup guide (templatized)
    README.md                      <- hub repo front page (templatized)
  pod/
    CLAUDE.md                      <- per-team AI context (templatized)
    README.md                      <- per-team front page (templatized)
    notes.md                       <- structured work log
  guides/
    claude-code-quickstart.md      <- install + first commands
    github-basics.md               <- repos, commits, sharing
    pod-kickoff.md                 <- pick problem, define it, build
    prompt-cheatsheet.md           <- copy-paste starter prompts
    using-your-repo.md             <- push, pull, token setup
    presentation-guide.md          <- NotebookLM + demo prep
    tools.md                       <- all tools with decision guide
prompts/
  facilitator/
    stalled-pod.md                 <- when a team hasn't started
    midpoint-checkin.md            <- halfway pulse check format
    final-push.md                  <- fill notes.md, prep demo
    blind-spot-audit.md            <- find demo-breaking bugs
    rate-limit-workaround.md       <- Claude web + Claude Code relay
  attendee-research/
    research-prompt.md             <- profile attendees from reg data
    profile-card.md                <- per-person profile template
    profiles-full.md               <- full dossier with expertise map
presentations/
  workshop-intro.html              <- GSAP animated intro deck
  collab-guide.html                <- roles, handoffs, rate limits, NotebookLM
mistakes.md                        <- every mistake we made and how to avoid it
```

---

## Quick start

1. Read `FACILITATOR.md` - the full playbook from start to finish
2. Copy `templates/` to your event repo, find-and-replace the `{{PLACEHOLDERS}}`
3. Use `checklists/` to track progress at each phase
4. Use `prompts/facilitator/` during the live session

---

## The format

| Phase | Time | What happens |
|-------|------|-------------|
| Opening | 15 min | Setup verification, intro, pod assignments |
| Ideation | 30 min | Pick a problem, define it, assign roles |
| Build | 2.5-3 hours | Build with Claude Code, facilitator monitors |
| Midpoint | 15 min | One person per pod, 2 min each |
| Final push | 30 min | Fill notes.md, fix demo-breaking bugs |
| Presentations | 30-45 min | 3 min per pod, live demo |

---

## Key principles

- **3-4 people per pod** - 5-6 causes idle members
- **Each pod needs a leader** who can keep things moving
- **Fine-grained PATs per repo** - never org-level OAuth tokens
- **CLAUDE.md primes Claude Code** - team context, what to build, where to get help
- **notes.md IS the presentation** - fill it in as you go, not at the end
- **Done beats perfect** - a working demo with rough edges beats a polished idea with no code
- **Rate limits are normal** - switch to Claude web, keep building, paste back into Claude Code

---

## Proven results

From the first run (April 10, 2026):

| Pod | Project | What they built |
|-----|---------|----------------|
| A | TindaCheck | Grocery price comparison with barcode scanner |
| B | Sakay Na! | Cebu jeepney route finder |
| C | FitAlarm | GPS fitness alarm you can't snooze |
| D | GiftMaster | Relationship intelligence PWA with AI agent |

All 4 pods shipped working apps in under 5 hours. Two were deployed live via GitHub Pages during the session.
