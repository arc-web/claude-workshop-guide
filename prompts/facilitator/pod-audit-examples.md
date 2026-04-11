# Pod-Specific Audit Prompts - Real Examples

The generic blind-spot audit works for any project. But custom prompts that reference the pod's actual features catch more real bugs. Here are 4 examples from the first workshop run.

---

## Pod A - TindaCheck (grocery price comparison)

```
"Audit TindaCheck for demo-breaking issues only. Specifically check:
- What happens if the barcode scanner can't find a product in Open Food Facts
- What happens if someone adds two products with the same name
- Does the size x packs formula handle decimals and zeros without breaking
- Does the Compare tab work if My List is empty
- Does the dark/light mode toggle break any text contrast

Rank each HIGH / MEDIUM / LOW. Fix HIGH only."
```

## Pod B - Sakay Na! (Cebu jeepney route finder)

```
"Audit Sakay Na! for demo-breaking issues only. Specifically check:
- What happens if the user picks the same origin and destination
- What happens if no route exists between two points
- Does the route display work on mobile viewport
- What does the UI show while routes are loading - is there a loading state or does it look broken
- Can the user clear their selection and start over

Rank each HIGH / MEDIUM / LOW. Fix HIGH only."
```

## Pod C - FitAlarm (GPS fitness alarm)

```
"Audit FitAlarm for demo-breaking issues only. Specifically check:
- What happens if the user denies GPS permission
- What happens if the distance goal is never reached - does the alarm still fire at the set time, or does nothing happen
- Does the alarm actually sound on a phone with silent mode on
- What does the completion screen show if GPS data was patchy
- Can you set an alarm time in the past without the app breaking

Rank each HIGH / MEDIUM / LOW. Fix HIGH only."
```

## Pod D - GiftMaster (relationship intelligence PWA)

```
"Audit GiftMaster for demo-breaking issues only. Do not refactor anything. Specifically check:
- Does login -> add a person -> view their dashboard work end to end without a page error
- What happens if Supabase is slow or returns an error - does the UI hang silently or show something
- Does the agent cards endpoint return something meaningful or an empty state that looks broken
- Are there any hardcoded values or placeholder text still visible in the UI
- What does a brand new user see the first time they log in - is it clear what to do next

Rank each HIGH / MEDIUM / LOW. Fix HIGH only. Do not touch anything else."
```

---

## How to write your own

1. Read the pod's repo: `gh api repos/ORG/pod-X/contents --jq '.[].name'`
2. Open their index.html or main page to understand the user flow
3. For each feature, ask: "what's the dumbest thing a user could do here that would break it?"
4. Write 4-5 specific checks referencing actual feature names
5. Always end with "Rank HIGH / MEDIUM / LOW. Fix HIGH only."
