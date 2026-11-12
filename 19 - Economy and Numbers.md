# Economy and Numbers

How fast things are earned, what they cost, and how the curve bends so the game is quick at the start and still has goals after a month. Everything here is a starting point (rule of thumb) to put in the shared config tables and tune by timed playthroughs. Genre-specific numbers are in [[20 - Slop Game Blueprints]].

## The one rule

**Design the time between rewards, then derive the prices.** Decide how long a player should wait for the next purchase at each stage, measure how much they earn per second at that stage, and the price is the product of the two.

| Stage | Time to next meaningful purchase |
|---|---|
| First 2 minutes | 10 to 20 seconds |
| Minutes 2 to 15 | 30 to 90 seconds |
| Rest of first session | 2 to 5 minutes |
| Days 2 to 7 | 5 to 15 minutes of play, or one offline collection |
| Weeks | a session or two for the big ones |

If a new player waits more than two minutes for anything in the first fifteen, the curve is too steep.

## Currencies

Keep it small. Every extra currency is something a child has to learn.

- **Main currency** (cash, coins): earned constantly, spent constantly. Numbers grow huge on purpose.
- **Progress token** (Wins, rebirth points, trophies): earned by finishing something; buys permanent multipliers. Small numbers.
- **Optional premium-feel currency** (gems): earned slowly from quests, index rows and daily rewards; buys cosmetics, slots and rerolls. If it can be bought with Robux, anything random bought with it falls under the paid-random rules.
- **Event currency:** only during an event, expires clearly.

## Upgrade costs

Use a geometric curve: each level costs the previous level times a growth factor.

`cost(level) = base × growth ^ level`

| Growth | Feel | Use for |
|---|---|---|
| 1.07 to 1.10 | gentle, many levels | the main per-click or per-step stat |
| 1.12 to 1.18 | standard idle-game curve | earners, pets, machines |
| 1.25 to 1.5 | steep, few levels | capacity, slots, speed tiers |
| 2 to 10 per tier | big jumps | worlds, rebirth requirements |

- Each level's benefit should grow slower than its cost, so progress naturally slows and rebirth becomes attractive.
- Make the first five levels of anything cheaper than the curve says. Early generosity is the tutorial.
- Offer "buy 1, buy 10, buy max" as soon as the player can afford more than a few.
- Show the benefit as old → new on the button.

## Earners and rarity

- Income per tier rises much faster than the chance falls, so a rare drop is a real jump: see the rarity table in note 20 (1x, 4x, 15x, 75x, 500x, 5,000x).
- Price of a character on a conveyor or in a shop: roughly 60 to 120 seconds of its own income at the low end, rising to 5 to 10 minutes for top tiers. It should pay for itself while the player is still in the session.
- Slots are the real limit. A cap on slots forces "replace the weakest" decisions, which is where the game is.
- Mutations multiply income on top of rarity: Gold x1.5, Diamond x2, Rainbow x5, event x3. Keep chances low (10%, 3%, 0.5%).

## Rebirth

- **First rebirth inside the first session**, around minute 15 to 25. It teaches the system while the player is still engaged.
- Each rebirth: permanent multiplier (+50% to +100% early, flattening later), one new unlock (slot, floor, world, pet slot), a visible badge.
- Requirement grows by 3x to 10x each time, and after the first few asks for specific items as well as a total, so it is a goal and not just a wait.
- After a rebirth, getting back to where they were should take about a third of the time it took before. The reset must feel like speeding up.
- Keep through a rebirth: collection index, cosmetics, passes, pets (usually), premium currency.

## Luck and rolls

- One weighted table in config. The roll reads it; the odds screen reads it. Never two sources.
- Luck multiplies the weights of the higher tiers and the shown odds change with it.
- A pity counter (a guaranteed Epic or better every N rolls) softens bad streaks. If the rolls can be paid for, the counter and its effect on odds must be shown.
- A scripted first experience (the starter sequence everyone gets) is fine for free rolls and makes the first minute reliable. Never script paid rolls.
- "1 in N" is how players talk about rarity. Show it everywhere.

## Sinks and inflation

More currency enters an idle game every day than leaves it. Plan for where it goes.

- Upgrades with no ceiling (a "+1% forever" stat).
- Rerolls of mutations or stats.
- Cosmetics bought with the main currency at absurd prices, as a late-game brag.
- Fusing: three of a tier into one of the next, burning duplicates.
- Limited stock in a rotating shop.
- When numbers get silly, add a new world with its own currency rather than more zeros.

If players can trade, every faucet matters far more, duplication bugs are fatal, and paid items need Roblox's trading policy check. Launch without trading; add it only once the game has proved it will live.

## Free versus paying

- A player who never pays reaches everything, slower. Passes roughly double a rate; they do not unlock the game.
- A x2 pass should feel great in week one and still matter in week four. Apply multipliers at the end of the formula so they scale with progress.
- Do not let stacked boosts exceed about 10x a free player in the same situation, or free players feel the game is not for them and ratings fall.
- Tune the free experience first. Then add what is sold.

## Tuning method

1. Put every number in one config module with comments.
2. Build a tiny simulation, or simply a debug command, that prints time-to-afford for the next twenty purchases at the current income.
3. Play a fresh save with a timer against the early-wins table in [[01 - Game Standard]]. Write down every moment of waiting.
4. Fix the worst wait, replay.
5. After launch, read the funnel: where do players stop buying upgrades? That step is priced wrong or explained badly.

## Analytics events for the economy

Record currency earned and spent by source, each upgrade level bought, each rebirth, time from join to first purchase of each kind, and what the player had when they left. Roblox's analytics has economy and funnel events for this; check the current docs.

Deeper reference: `References/Filhao Roblox Vault/11 LihFolk V2/48 Economy Design Deep Dive/` (pricing curves, drop tables and pity, simulating before launch) and `40 Game Math/`.
