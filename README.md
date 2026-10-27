# Lifequest — a weekly quest ritual for Claude

Lifequest turns your week into a small RPG. Once a week, Claude reads your journal, checks how the last week went and builds a quest log for the next one: a themed week, one main quest, a short quest per area each day — every one with a **Full** version and a **Flex** version for bad days — plus a few reflection questions.

It grew out of more than a year of running this ritual for myself, from a ChatGPT chat through a self-built app and a nine-agent crew to a single Claude skill. This is that skill with everything personal taken out and replaced by a config you fill in yourself.

## What's in the box

| File | What it's for |
|---|---|
| `lifequest/SKILL.md` | the skill: setup check, the 8-phase weekly ritual, design principles |
| `lifequest/references/setup_interview.md` | the character-creation interview on the first run |
| `lifequest/references/config_template.md` | every setting with defaults |
| `lifequest/references/quest_design.md` | quest rules plus a starter pool of 39 quests, journal questions and writing prompts |
| `lifequest/references/questlog_template.md` | the weekly quest log layout |
| `lifequest/references/modules/` | optional: XP and rewards, KPIs, a flagship project, task-app export |
| `PERSONALIZE.md` | the prompt that sets up your own version |

## Setup in three steps

1. **Add the skill.** Upload `lifequest.zip` (the ready-zipped `lifequest` folder) as a custom skill in Claude. If you change files, zip the folder again; it must stay named `lifequest`. Anthropic's help article describes where: [Use skills in Claude](https://support.claude.com/en/articles/12512180-use-skills-in-claude).
2. **Personalise.** Open a new conversation and paste the prompt from `PERSONALIZE.md`. Claude interviews you and writes your `lifequest_config.md`.
3. **Play a week.** Keep a few lines of journal each day. On your planning day, say "Lifequest, plan next week".

Works best when Claude can read and write files in a folder of yours (for example through the desktop app). Without file access, Claude gives you the quest log in the chat and you keep the files yourself.

## The weekly loop

```
journal during the week → planning day: Claude reads, reviews, plans
→ quest log (+ optional task-app file) → tick off quests → repeat
```

## Modules

| Module | Turn on when … |
|---|---|
| XP and rewards | you like points and treating yourself; two numbers so spending never costs progress |
| KPIs | you have a few yearly targets you want to see pace on |
| Flagship | one big project should move a bit every week |
| Task export | you tick things off in Apple Reminders, Todoist or similar |

## Three lessons baked in

- **Flex is mandatory.** A bad day with three tiny quests done beats a perfect plan with nothing done.
- **Count the attempt where the outcome isn't yours.** Messages sent, not replies received.
- **One coordinator with full context beats a chain of specialists.** Every hand-off loses nuance.

## Licence

Free to use and adapt for personal use. If you share a remix, a link back is appreciated.
