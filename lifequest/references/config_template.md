# lifequest_config.md — template and defaults

The config is a Markdown file with one YAML block. The player owns it and can edit it by hand at any time. The setup interview fills it in; anything left out falls back to the defaults below.

Copy the block, replace the values, delete what you don't need.

```yaml
# ── Player ────────────────────────────────────────────────
player:
  name: "Mara"                       # how to address the player
  character: "Mara the Steady"       # character name on the sheet
  class: "Wayfinder"                 # a class that fits their year
  address: informal                  # informal | formal
  language: English                  # all outputs in this language
  timezone: Europe/Berlin            # used for due times

# ── Tone ──────────────────────────────────────────────────
tone:
  flavour: medium                    # light | medium | full  (how much RPG wording)
  genre: "cosy fantasy"              # fantasy, sci-fi, noir, cosy village, pirates, …
  voice: "warm, dry humour, never preachy"

# ── Weekly rhythm ─────────────────────────────────────────
rhythm:
  planning_day: Sunday
  work: "Mon–Fri 09:00–17:30, office Tue+Thu"   # free text is fine
  energy: "slow mornings, best focus in the evening"
  bedtime: "23:30"
  daily_quest_ceiling: 5             # max quests per day, including all categories

# ── Daily categories (one quest each per day) ─────────────
categories:
  - name: Morning
    window: "07:00–08:30"
    ideas: "tea, breathing, a short intention"
  - name: Movement
    window: flexible
    ideas: "walks, stretching, desk yoga, gym"
  - name: Chores
    window: "evening or weekend"
    ideas: "one surface, one drawer, kitchen reset"
  - name: Creative
    window: "20:00+"
    ideas: "writing, drawing, music, reading, a good film"
  - name: Journaling
    window: "before bed"
    ideas: "three lines, one question, a win"

# ── Weekly quests (due by Sunday) ─────────────────────────
weekly:
  - "Money check (10 min)"
  - "Reach out to one person"

# ── Goals for the year ───────────────────────────────────
goals:
  - "Write 24 short stories"
  - "Walk 150 times"
  - "Clear out the spare room"

# ── Modules (on/off) ──────────────────────────────────────
modules:
  xp: true          # XP + spendable currency + rewards
  kpis: true        # yearly targets with pace
  flagship: false   # one main project per season
  export: false     # task-app file

# Settings for modules that are on (see references/modules/)
xp:
  xp_name: "XP"
  currency_name: "Threads"
  rewards:
    small: { cost: 750,  examples: ["fancy coffee", "a new notebook"] }
    medium: { cost: 1000, examples: ["a book", "cinema"] }
    large: { cost: 2000, examples: ["a board game"] }
    epic: { cost: 3000, examples: ["a day trip"] }

kpis:
  - { name: "Stories", target: 24, unit: "stories" }
  - { name: "Walks",   target: 150, unit: "walks" }

flagship:
  project: ""
  roadmap_file: "planning/roadmap.md"
  hours_per_week: 4

export:
  target: apple_reminders_json      # apple_reminders_json | todoist_csv | generic_json | none
  list_names: { Morning: "Morning", Movement: "Movement", Chores: "Chores", Creative: "Creative", Journaling: "Journaling", Weekly: "Weekly" }

# ── Care ──────────────────────────────────────────────────
care:
  gentle_topics: []        # topics to handle softly, e.g. "family", "money"
  avoid_topics: []         # topics never to raise
  player_notes: ""         # what the player wants the Lifeweaver to know, in their own words

# ── Folders (only if you renamed them) ───────────────────
folders:
  root: "Lifequest"
```

## Defaults when a value is missing

| Key | Default |
|---|---|
| `player.language` | the language the player writes in |
| `player.address` | informal |
| `tone.flavour` | medium |
| `tone.genre` | cosy fantasy |
| `rhythm.planning_day` | Sunday |
| `rhythm.daily_quest_ceiling` | number of categories |
| `categories` | the five above |
| `weekly` | none |
| `modules` | all off |
| `care.*` | empty |

## Rules for editing the config

- Change it only when the player asks or agrees. Show the changed lines.
- Keep the player's wording in `player_notes` exactly as they wrote it.
- Never store sensitive details the player didn't put there themselves.
