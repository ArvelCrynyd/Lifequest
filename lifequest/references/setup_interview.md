# Setup interview

Run this when there is no `lifequest_config.md` yet, or when the player asks to redo their setup. Goal: a working config in about 10 minutes, then a first quest log so the player sees what they built.

## How to interview

- Ask in **rounds of at most three questions**. Offer a sensible default with every question so the player can just say "default".
- If the player already pasted information (e.g. through the personalisation prompt), use it and only ask what's missing.
- Mirror their language from the first message on; confirm it in round 1.
- Keep it light and a little playful — this is character creation, not a form.
- Never ask for health details, diagnoses, finances in numbers, or other sensitive data. If the player offers some, ask whether it belongs in `care.player_notes` and keep their wording.

## Rounds

**Round 1 — Who's playing**
1. What should I call you, and what's your character's name? (default: your name + an epithet I suggest)
2. Which world feels like yours: cosy fantasy, sci-fi, noir, pirates, something else? And how much game language do you want — light, medium, full?
3. Language for the quest logs?

**Round 2 — Your week**
1. What does a normal week look like: work hours, office or home, fixed commitments?
2. When do you have energy, when not? Roughly when do you go to bed?
3. Which day do you want to plan on? (default: Sunday)

**Round 3 — Daily categories**
Show the five defaults (Morning, Movement, Chores, Creative, Journaling) with time windows. Ask:
1. Keep, rename, drop or add any? (3–6 categories work best)
2. A time window for each?
3. How many quests a day at most? (default: one per category)

**Round 4 — The year**
1. Two to five things you want this year to be about.
2. Should any of them be counted (e.g. "24 stories", "150 walks")? → offers the `kpis` module.
3. Is there one big project you'd like steady weekly progress on? → offers the `flagship` module.

**Round 5 — Game mechanics**
1. XP and a spendable reward currency with a reward catalogue? (`xp` module) If yes: what would you treat yourself to, in four sizes from small to epic?
2. Should quests land in a task app? Which one? (`export` module: Apple Reminders via JSON, Todoist via CSV, or a generic JSON file)
3. Weekly quests that don't belong to a day (admin, money check, reaching out)?

**Round 6 — Care**
1. Any topics I should handle gently, or never bring up?
2. Anything you'd like the Lifeweaver to know about you, in your own words? (optional — stored as written)

## After the interview

1. Write `lifequest_config.md` from `references/config_template.md`, filled with the answers. Show it to the player.
2. Create the folders from SKILL.md (and the `state/` files for modules that are on, with zeros).
3. Explain the weekly loop in four lines: journal during the week → planning day → quest log → tick off quests.
4. Offer to plan the first week right away. With no journal yet, plan a gentle **Week 0**: Flex-heavy, one main quest about settling in, and reflection questions that help calibrate next week.
