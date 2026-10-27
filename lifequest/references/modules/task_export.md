# Module: Task export

Quests are ticked off where the player already looks every day: a task app. This module writes one file per week that a task app can import. The skill only writes the file; importing it is up to the player's tool (a shortcut, a script, the app's import function).

## Formats

Set `export.target` in the config.

### `apple_reminders_json` / `generic_json`

`exports/quests_{YYYY}-W{WW}.json` — a JSON array, one object per quest:

```json
[
  {
    "title": "The Path of Ten Minutes – walk without phone",
    "due": "2026-03-02T17:00:00Z",
    "list": "Movement",
    "notes": "Full: 10-minute walk, no phone. Flex: 5 minutes, phone in the pocket."
  }
]
```

- `title`: quest name + a short plain description.
- `due`: think in the player's `timezone`, convert to UTC with a `Z` suffix. Mind daylight-saving changes.
- `list`: map categories with `export.list_names`; weekly quests go to the "Weekly" list, due Sunday evening.
- `notes`: always both Full and Flex.

Apple Reminders has no built-in JSON import. Players typically use a Shortcut ("Get contents of file → Repeat with each item → Add new reminder") or a small script. Point them to that; don't promise a one-click import.

### `todoist_csv`

`exports/quests_{YYYY}-W{WW}.csv`, following Todoist's CSV template (columns in this order: `TYPE,CONTENT,DESCRIPTION,PRIORITY,INDENT,AUTHOR,RESPONSIBLE,DATE,DATE_LANG,TIMEZONE`; leave unused cells empty). One row per quest:

- `TYPE` = `task` (lowercase).
- `CONTENT` = quest name + short description; `DESCRIPTION` = Full and Flex.
- `PRIORITY` = `4` — an empty cell would make every quest top priority.
- `DATE` = date and time in plain words (e.g. `Mar 2 18:00`); `DATE_LANG` = the code of the player's Todoist language (`en`, `de`, …).

Format reference: [Format a CSV file to import into Todoist](https://todoist.com/help/articles/360000748525).

## Completed quests back in

If the player can export completed tasks (a shortcut or the app's export) into `exports/completed_{YYYY}-W{WW}.json`, read it in Phase 1 and count from it for XP and KPIs. Accept messy files: read object by object and skip what you can't parse, then say how many entries you skipped.

## Safety

- Writing the file is always fine. Writing *into* a live task app (if the session has a tool for that) happens only after the player says yes in Phase 8.
- Never delete tasks in the player's app. If quests changed after an import, list the old ones so the player can remove them.
