# Research Prompt

Paste this into Claude with your attendee list. Works best with Claude Sonnet or Opus.

---

## The Prompt

```
I'm running a [type of event] called [event name] on [date] in [location].

I have [N] attendees and I want to build a profile on each one for introductions and facilitation purposes.

For each person, search LinkedIn, Google, and any other public sources. Return a profile card with:
- Full name
- Likely job title and company
- LinkedIn URL if found
- Any other relevant public links (GitHub, Twitter, portfolio, website)
- Confidence level: HIGH (multiple verified sources), MEDIUM (one confirmed source or strong inference), LOW (no public profile found)
- A one-sentence intro angle - how I should open a conversation with this person at the event

Here is my attendee list with registration data:

[paste your list here - names, emails, and any other fields from your form]
```

---

## Tips for Better Results

**Run in batches of 7-10 people.** Claude searches more thoroughly on smaller batches. For 30+ attendees, split into groups and run separately.

**Include all registration fields.** The more context Claude has (company email, experience level, what tools they use), the better the profiles.

**Work email domains are the best signal.** If someone registered with `name@company.com`, Claude can confirm employer before searching anything else.

**Run a second pass on LOW confidence results.** After the first batch, take all the LOW results and try again with slightly different search terms - sometimes a job title or city helps.

**Ask for flags explicitly.** Add to the prompt: "Also flag anything unusual - possible email typos, first-name-only registrations, or anything I should check before the event."

---

## Organizing the Output

Once you have all profiles, organize them using the template in `templates/profiles-full.md`.

Add two sections at the end:
1. **Flags to Action** - anything that needs follow-up before the event
2. **Room Expertise Map** - group attendees by skill/background tier so you can see the shape of your audience

---

## Example Output Format

```
### [Name]
**Confidence: HIGH**
- **Role:** Product Designer at [Company]
- **LinkedIn:** https://linkedin.com/in/[handle]
- **Notable:** Won [award], founded [project], speaks at [conference]
- **Setup:** Mac, active AI user, has paid subscription
- **Intro:** Ask about their work on [project] - they recently [notable thing]
```
