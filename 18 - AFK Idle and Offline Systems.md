# AFK, Idle and Offline Systems

Letting progress continue while the player is not actively playing. Passive income is the strongest return reason in the slop genres: the player leaves, a number grows, and they come back to collect it. This note is how to build that so it helps the game instead of filling servers with empty avatars.

Tags: (official) Roblox docs read 11 Nov 2026, (rule of thumb) design starting points.

## The facts to design around

- **Roblox disconnects a player who has been idle for at least 20 minutes** (official). There is no setting to turn this off.
- The engine's idle event fires on the player's device about two minutes after it decides the player is idle, then every 30 seconds; activity resets it (official).
- **Playtime counts towards discovery only up to 60 minutes per player, per game, per day** (official). An overnight AFK session earns the game nothing beyond the first hour.
- **Days played matters more than hours.** The ranking signals are days played in day 1, days 2 to 7 and days 8 to 28 (official). One login a day for ten minutes beats one six-hour sit.
- Roblox's creator reward pays for a spender playing 10 or more minutes when the game is among their first three of the day (official). Again: a short daily visit.
- Roblox's docs say nothing about idle time being penalised. Claims either way are unverified.

**What this means:** design for *offline* progress (the player closes the game and comes back) first, and for *in-game AFK* (the player stays connected but away) second. Offline progress creates the daily return that Roblox rewards. In-game AFK is a comfort feature and a thing to sell.

## The three kinds of passive progress

| Kind | Player is | Earns | Purpose |
|---|---|---|---|
| Active | playing | 100% | the real game |
| In-game AFK | connected, hands off | 25 to 50% of active | comfort while eating dinner; auto features to sell |
| Offline | not connected | 10 to 30% of active, capped by hours | the reason to open the game tomorrow |

Active play must always be clearly the best. If AFK pays as well as playing, players stop playing, servers look dead to newcomers, and the economy inflates.

## Offline earnings

- On leaving, save the server's own time. On joining, work out time away, clamp it to zero or more and to the cap, multiply by the player's passive rate. Use server time only, never the player's clock.
- **Cap:** 2 hours for a free player, upgradable with in-game currency to 4 and 8, with a pass taking it to 12 or 24. A cap makes the player want to return *before* it fills.
- **Rate:** a fraction of what the base earns while online. Upgradable.
- **Welcome-back screen:** on join, a card saying "While you were away: 2h 14m" with the amount counting up, coins flying to the counter, and a "Claim" button. This is the first thing a returning player sees, so make it a Moment (see [[13 - Game Feel and Juice]]).
- **Offer on that screen (optional):** "Claim x2" by watching a rewarded video ad where the player is eligible, or with a small product. It must be clearly optional, with plain Claim the bigger button. Rewarded-ad rewards cannot be randomised items (official).
- If the storage was full, say so: "Storage full at 2h. Upgrade to earn longer." That is the natural upsell, and it is honest.
- In a steal game, decide what happens to an offline player's base: the usual answer is that it is locked and safe while they are away, so nobody returns to nothing.

## In-game AFK

Features that let a connected player rest. Each is a design choice, not a requirement.

- **Auto-collect:** income goes straight to the wallet instead of piling up to be collected. Usually a pass or a late upgrade. Keep manual collecting satisfying for those without it.
- **Auto-action:** auto-tap, auto-roll, auto-train, auto-hatch. Unlock a slow version through play, sell a faster one. The auto version should be slower or weaker than skilled manual play.
- **AFK zone or AFK mode:** a marked area or a toggle that parks the avatar, dims the screen, and pays a small, clearly labelled trickle plus a timed chest ("stay 10 minutes for a gift").
- **Playtime rewards:** a strip of gifts unlocking at 5, 10, 20, 30, 45 and 60 minutes of the session. Stop at 60: time past that earns the game nothing. Reset daily.
- **Helpers and pets** that gather or earn on their own while the player does the interesting part.

**Rules for AFK rewards**

| Rule | Why |
|---|---|
| AFK pays less than active play | active play stays the best choice |
| Capped per session or per day | overnight farming cannot dominate the economy |
| Clearly labelled, including the cap | hidden caps feel like being tricked |
| Timed gifts need some activity in each interval | otherwise they reward bots |
| Paid boosts state whether their timer runs while AFK or offline | avoids refund complaints |
| Nothing rare or tradable from pure AFK | protects the collection's value |

## The 20-minute disconnect

- **Do not fake input or script around it.** It keeps empty avatars in servers, and it is the kind of artificial engagement Roblox works to discount. Treat it as off-limits.
- Do warn the player: at about 18 minutes idle, a message and a sound, "Move to stay connected."
- Make the disconnect harmless: save continuously, and make offline earnings take over the moment they leave. A player who is kicked while AFK should lose nothing and still come back to a welcome-back screen.
- If servers are full of idle players in a small-server game, move them to an AFK state that frees their base slot visually, or kick earlier with a friendly warning. Never do this in private servers.

## Activity tracking

- The server keeps its own "last active" time per player from things it can verify: accepted actions, real movement, purchases, menu use. Do not trust a device saying "I am active".
- Movement alone is fooled by conveyors and auto-walk; combine signals.
- A player reading the shop or the index is not AFK. Count menu interaction.
- Exploit scripts fake activity. Rewards that matter should depend on actions the server validated, not on being present.

## Selling passive progress

These are among the best-selling items in idle and collect games because the benefit is felt every single session. Prices are in [[03 - Monetization and Shop Standard]].

- Auto-collect (pass)
- Offline time extension: 2 hours to 12 or 24 (pass)
- Offline earnings x2 (pass)
- Faster auto-action (pass)
- "Claim x2" on the welcome-back screen (rewarded ad or small product)
- A subscription that bundles auto-collect, longer offline time and a daily gift, if the game has enough daily players to justify one

Keep it honest: the free version of each must work and be worth using. Sell more comfort, not relief from something made painful on purpose.

## Return rhythm

Build the loop so there is a reason to open the game at three scales.

| Scale | Hook |
|---|---|
| Hours | offline storage filling towards its cap; a restock or rotation on a public clock |
| Days | daily reward calendar, daily quest, the playtime gift strip resetting |
| Weeks | a fixed-day update, a weekend event, a season track |

Opt-in notifications (13 and over, limited per day by Roblox) can say "Your storage is full" or "The new world is open". Use them for facts, not guilt.

## What not to build

- A streak that destroys progress when a day is missed. A calendar that simply continues is kinder and works.
- Progress that decays while away.
- AFK income equal to active income.
- Any reward for sitting on a screen that plays no game.
- Scripts that simulate input to dodge the idle kick.

## Checklist

- [ ] Offline earnings computed on the server from saved server time, clamped and capped
- [ ] Welcome-back screen with a count-up and a plain Claim button
- [ ] Offline cap visible and upgradable
- [ ] AFK and auto features pay less than active play and say so
- [ ] Playtime gifts stop at 60 minutes and reset daily
- [ ] Idle warning before the 20-minute disconnect; nothing lost when it happens
- [ ] Server-side activity tracking; no trust in the device
- [ ] No faked input

Deeper reference: `References/Filhao Roblox Vault/11 LihFolk V2/58 Player QoL and Game Tweaks/AFK Detection Idle Kicks and AFK Reward Rules` (includes a server-side activity module), `References/Kaffein Dev Vault/03 - Reusable Systems/S-daily-retention-engine` and `S-session-reward-grid`.
