# Facilitator Playbook - A to Z

This is the complete guide for running a Claude Code workshop. Read it once top to bottom before your event, then use the checklists to track progress.

---

## Phase 1: Pre-Event (2-4 weeks before)

### 1.1 Attendee profiling

Collect registration data (name, email, job title, AI experience, computer type). Then run the research prompt in `prompts/attendee-research/research-prompt.md` through Claude in batches of 7-10 people.

For each person you get back:
- Full name, likely job title and company
- LinkedIn URL (if found)
- Confidence level: HIGH / MEDIUM / LOW
- One-sentence intro angle

Organize results using `prompts/attendee-research/profiles-full.md`. Add two sections at the end:
1. **Flags to Action** - email typos, missing info, anything to follow up before the event
2. **Room Expertise Map** - group attendees by skill tier so you can see the shape of your audience

Run a second pass on LOW confidence results with slightly different search terms.

### 1.2 Pod assignment

**Rules (learned the hard way):**

- 3-4 people per pod. Not 5-6 - too many causes idle members.
- Each pod needs one experienced leader (PM, senior dev, community leader).
- Each pod needs at least one person with a Claude subscription.
- Mix experience levels - put learners with mentors, not with other learners.
- Balance computer types (Mac/Windows) when possible.
- Write a rationale for each pod grouping so you remember why.

**Do not create pod repos until attendance is confirmed.** We made 6 pods, only 4 showed up. Two repos had to be archived. Create repos just-in-time the morning of, or at most the night before, based on confirmed RSVPs.

### 1.3 Infrastructure setup

**Create a GitHub org** (or use an existing one). You need:

1. **Hub repo** (e.g., `my-workshop`) - read-only reference for all attendees. Copy from `templates/hub/`.
2. **One repo per pod** (e.g., `workshop-pod-a`) - writable workspace per team. Copy from `templates/pod/`.
3. (Optional) **Attendee research repo** - profiles and research data, facilitator-only.

**Find-and-replace these placeholders** in all template files:

| Placeholder | Replace with |
|---|---|
| `{{EVENT_NAME}}` | Your workshop name |
| `{{EVENT_DATE}}` | Date of the event |
| `{{EVENT_TIME}}` | Start and end time |
| `{{EVENT_LOCATION}}` | Venue name and address |
| `{{ORG_NAME}}` | GitHub org name |
| `{{HUB_REPO}}` | Hub repo name |
| `{{POD_NAME}}` | Pod A, Pod B, etc. |
| `{{POD_LETTER}}` | a, b, c, etc. |
| `{{POD_REPO}}` | Pod repo name |
| `{{POD_SIZE}}` | Number of team members |
| `{{POD_MEMBERS}}` | Full member list with roles |
| `{{POD_LEADER}}` | Pod leader name |
| `{{POD_RATIONALE}}` | Why this grouping works |
| `{{FACILITATOR_1}}` | First facilitator name and bio |
| `{{FACILITATOR_2}}` | Second facilitator name and bio |
| `{{DISCORD_INVITE}}` | Discord invite link |

**Access tokens:**

Create fine-grained PATs (GitHub Settings > Developer Settings > Personal Access Tokens > Fine-grained tokens):
- One token per pod repo
- Scope: `contents:write` only
- Do NOT use org-level OAuth tokens (`gho_` prefix) - these give access to everything

Distribute tokens via Discord pins or printed cards. Never commit tokens to repos.

Each pod's CLAUDE.md includes the one-command setup:
```
git remote set-url origin https://YOUR_TOKEN@github.com/{{ORG_NAME}}/{{POD_REPO}}.git
```

### 1.4 Discord setup

- Create server with channels: #general, #pod-a through #pod-n, #facilitators
- Pin in each pod channel: Claude API key (`sk-ant-...`), GitHub PAT token, quick-start link
- Pin in #general: hub repo link, setup guide link, Discord invite for sharing

### 1.5 Presentation materials

Copy the GSAP HTML presentations from `presentations/`:
- `workshop-intro.html` - 6 slides: title, the problem, the solution, stats, how it works, closing
- `collab-guide.html` - 10+ slides: roles, handoffs, rate limits, viewing apps locally, midpoint check-in, NotebookLM

Edit the content to match your event. Open in browser, navigate with arrow keys.

---

## Phase 2: Day-of Setup (morning of event)

See `checklists/day-of.md` for the full checklist. Key items:

- Test clone + push with each PAT token
- Verify Claude Code install works on both Mac and Windows
- Open browser tabs for each pod's GitHub repo
- Have terminal ready to clone and run any pod's app locally
- Presentation HTML files open and tested
- WiFi password visible in the room

---

## Phase 3: Session Flow

### 3.1 Opening (15 minutes)

1. Run the workshop intro presentation
2. Point everyone to: hub repo, Discord, SETUP.md
3. Walk through setup checkpoints (each step has a "raise your hand" moment)
4. Confirm everyone has Claude access and Claude Code running
5. Introduce pod leaders by name

### 3.2 Ideation (30 minutes)

Pod kickoff guide (`templates/guides/pod-kickoff.md`) walks them through:

1. Go around the table - what wastes your time at work?
2. Pick one problem using filters (can AI help? buildable in 4 hours? shared pain?)
3. Define it: one sentence for the problem, the solution, and how you'll demo it
4. Lock the idea: fill notes.md, update README, tell Claude Code, assign roles, set 30-min checkpoint

If a pod is stuck after 15 minutes, walk over with the stalled-pod prompt from `prompts/facilitator/stalled-pod.md`.

### 3.3 Build phase (2.5-3 hours)

**Your monitoring cadence:**

Every 20 minutes, check all repos:
```bash
for pod in a b c d; do
  echo "=== Pod $pod ==="
  gh api repos/ORG/pod-$pod/commits --jq '.[0:3] | .[] | "\(.commit.author.date[0:16]) | \(.commit.message | split("\n")[0])"'
done
```

Flag any pod with no commits in 30+ minutes. Walk to their table with a custom prompt based on what they're building.

**Share proactively during the build:**

1. **Rate limit workaround** (see `prompts/facilitator/rate-limit-workaround.md`): switch to claude.ai, mock up frontend, paste code back into Claude Code
2. **Blind spot audit** (see `prompts/facilitator/blind-spot-audit.md`): "audit for demo-breaking bugs, rank HIGH/MEDIUM/LOW, fix HIGH only"
3. **Viewing the app locally**: tell them to say "open this in my browser so I can see it" to Claude Code

**Pull and run apps locally** so you can see what each pod is building:
```bash
# Static HTML (Pod A, C style)
git clone https://github.com/ORG/pod-a.git /tmp/pod-a && open /tmp/pod-a/index.html

# Vite/React (Pod B style)
git clone https://github.com/ORG/pod-b.git /tmp/pod-b && cd /tmp/pod-b && npm install && npm run dev -- --port 3001

# Next.js (Pod D style)
git clone https://github.com/ORG/pod-d.git /tmp/pod-d && cd /tmp/pod-d && npm install --legacy-peer-deps && npm run dev
```

**Enable GitHub Pages** for static HTML apps:
```bash
gh api repos/ORG/pod-a/pages --method POST --input - <<< '{"source":{"branch":"main","path":"/"}}'
```

### 3.4 Midpoint check-in (15 minutes)

One person per pod, two minutes max.

**Cover:**
1. What you built so far (one sentence)
2. What was easy (what Claude nailed)
3. What blocked you (rate limits, wrong output, unclear prompts)
4. What's next (one specific thing)

**After each pod speaks:**
- Anyone with the same blocker raises hand
- Anyone who solved it shares how
- Move on - don't get stuck in one pod's problem

See `prompts/facilitator/midpoint-checkin.md` for the prep prompt pods can use.

### 3.5 Final push (30 minutes before end)

Share the final push prompt from `prompts/facilitator/final-push.md` in all channels.

**Your tasks:**
- Enable GitHub Pages for all static HTML apps
- Pull latest from all repos, verify each app runs
- Update hub README "What Each Pod Built" section
- Prepare to open each repo on the big screen

### 3.6 Presentations (30-45 minutes)

Each pod gets 3 minutes:
1. The problem (30 sec)
2. The solution (30 sec)
3. Live demo (60-90 sec)
4. What's next (20 sec)
5. What surprised you (20 sec)

**NotebookLM option** for pods that want polish:
1. Go to notebooklm.google.com
2. Add source - paste repo URL or copy notes.md content
3. Generate Audio Overview - two AI hosts discuss their project
4. Screen record while audio plays = instant explainer video

**If a demo breaks:** show a screenshot, show the output, describe it. The audience evaluates the problem solved, not the live demo skills.

---

## Phase 4: Post-Event

See `checklists/post-event.md`. Key items:

- Update hub README with final project names, descriptions, live links
- Commit presentation files to hub repo
- Rotate/revoke all PAT tokens immediately
- Share repo links and live app URLs with attendees
- Archive pod repos (or leave open for continued work)
- Collect feedback via Discord or form

---

## Key numbers from first run

| Metric | Value |
|---|---|
| Total attendees | 15 |
| Pods | 4 (3-4 people each) |
| Session length | 5 hours (1 PM - 6 PM) |
| Apps shipped | 4 (all working, 2 deployed live) |
| Repos managed | 5 (1 hub + 4 pods) |
| Commits across all pods | 40+ |
| Time from idea to working app | 2-3 hours |
| Most ambitious build | Next.js + Supabase + Node agent API |
| Simplest build | Single HTML file, zero dependencies |
