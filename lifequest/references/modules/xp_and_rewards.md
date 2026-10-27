# Module: XP and rewards

Two numbers, earned together, used differently:

- **Lifetime XP** — only ever goes up. It is the progress score and drives the level.
- **Spendable currency** (name from `xp.currency_name`, e.g. Threads, Gold, Credits) — earned 1:1 with XP, goes down when the player redeems a reward.

Spending a reward never costs progress. That is the point of two numbers.

## State file

`state/xp_state.json` — create it on the first run with zeros:

```json
{
  "lifetime_xp": 0,
  "spendable": 0,
  "level": 1,
  "history": [ { "week": "2026-W01", "earned": 0 } ],
  "spending_log": [ { "date": "2026-01-12", "reward": "a book", "cost": 1000 } ]
}
```

## Earning (defaults — the config may override)

| Event | XP |
|---|---|
| a daily quest done (Full or Flex) | +5 |
| all daily quests of one day done | +25 |
| a main-quest subquest done | +50 |
| every quest of the week done | +75 |
| something creative published or shared | +100 |

Count from what the player reports: the journal, reflection answers, or a completed-tasks export from their task app. If nothing tells you what was done, don't award anything; ask in the review.

## Levels

Default: one level per 500 lifetime XP (`level = floor(lifetime_xp / 500) + 1`). Announce a level-up in the review with one line of in-world flavour.

## Rewards

The catalogue lives in the config (`xp.rewards`), in tiers with a cost and examples. Default tiers: small 750 · medium 1000 · large 2000 · epic 3000.

- The player redeems by saying so. Subtract the cost from `spendable`, add a line to `spending_log`, never touch `lifetime_xp`.
- Show in the quest log which tier is in reach.
- Don't nudge the player to spend or to save. It's their currency.

## Pitfalls

- If the player starts doing tiny quests just to farm XP, say so kindly. XP should follow life, not lead it.
- Streaks are optional. If the config has `xp.streaks: true`, a missed day ends the streak without any penalty to XP.
