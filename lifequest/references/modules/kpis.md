# Module: KPIs

A few yearly targets, tracked weekly with pace and a traffic light. Keep it to the handful that matter (3–8).

## State file

`state/kpi_state.json`:

```json
{
  "year": 2026,
  "kpis": [
    { "name": "Stories", "unit": "stories", "target": 24, "current": 0, "history": [] }
  ]
}
```

Targets come from the config (`kpis:`). The player updates `current` by telling you, or you count it from the journal or a task export. Append `{ "week": "2026-W14", "value": 11 }` to `history` each run.

## Scoreboard

For each KPI at the end of week *n* (ISO week of the last completed week):

- **Pace** = `current / n × 52` — where the year ends if the rate holds.
- **Status**: 🟢 pace ≥ target · 🟡 pace ≥ 70 % of target · 🔴 below that.
- **Gap** = `(target − current) / (52 − n)` — what's needed per remaining week.
- Show Δ since last week.

Targets that only start later in the year (e.g. "monthly from June") use the weeks since their start instead of *n*.

## How to talk about it

- Honest numbers, kind words. A red light gets a concrete, small adjustment in this week's plan — not a lecture.
- At most one or two KPIs get special attention per week.
- When a target is clearly out of reach, offer to re-set it. The player decides.

## Two rules that save the system

1. **Count the attempt where the outcome isn't yours.** For goals that depend on others (replies, sales, acceptances, invitations), track what the player does: messages sent, pieces submitted. Otherwise a good week can show red for reasons outside their control.
2. **Goodhart check.** When a number becomes the goal, it stops measuring. Watch for signs — the measure is met but the purpose isn't (a 2-minute "walk" to keep a count, logging instead of doing). Name it once, gently, and propose a better measure.
