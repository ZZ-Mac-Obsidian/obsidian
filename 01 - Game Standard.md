# Game Standard

What every factory game shares, whatever the genre. The genre-specific loop comes from [[20 - Slop Game Blueprints]] or [[12 - Genre Playbooks]]; engineering from [[11 - Tech Stack Standard]]; the order to build it in from [[21 - Build Order]].

Each layer has its own detailed note: feel in [[13 - Game Feel and Juice]], interface in [[14 - UI and HUD Standard]], motion in [[15 - Animation Standard]], effects and sound in [[16 - VFX and Audio Standard]], numbers in [[19 - Economy and Numbers]], passive progress in [[18 - AFK Idle and Offline Systems]].

## The universal layer

Every game that charts has these, in some form. Build them once as a template place and reuse them.

| Layer | Standard |
|---|---|
| First 5 seconds | Player is already doing the core action. No menu, cutscene or pop-up. |
| Tutorial | Guide character, one line at a time, ground beam, ten steps or fewer |
| Objective | One line always on screen saying the next goal |
| HUD | Five buttons maximum, big icons with short labels |
| Early wins | A reward every minute or two for 15 minutes |
| Progression | At least three ladders running at once (short, medium, long) |
| Social | Solo always works; playing with up to four friends is better |
| Return reasons | Something grew, something is new today, something is unfinished |
| Shop | One layout, one set of purchase rules ([[03 - Monetization and Shop Standard]]) |
| Feedback | Every action answered with sound, motion and a number |
| Save and analytics | Same data layout and the same event names in every game |

## Core loop slot

The genre fills this slot. Whatever it is, it must pass three tests:

1. **Fun alone in an empty test place** before anything else is built.
2. **Explainable in one clip of five seconds** (this is also the thumbnail and the video).
3. **Feeds a number or a collection that visibly grows.**

## Tutorial

- A small guide character gives one line at a time, eight words or fewer, with a beam on the ground to the next thing to touch.
- Each step waits for the action, then celebrates it. Nothing requires reading.
- Standard shape: do the core action, get the first reward, spend it on the first upgrade, reach the first milestone, see the next goal.
- No shop prompts or menus during the tutorial.
- Skip button after 30 seconds; returning players skip automatically.
- Each later mechanic gets one line, one beam, one action.
- Round-based games teach inside a first practice round instead, with the same rules.

## Navigation and HUD

- **One objective line** at the top, always. Tap it for a beam to the target.
- **Edge markers** for the two or three places the player returns to most.
- One button back to the lobby or base.
- **Five buttons maximum** during play. Layout from the reference games: big icon buttons with a short label (Shop, Index) on the left edge, currency and main stat bottom left, tool bar bottom centre.
- Interaction points use a dashed ring on the ground and a floating label.
- Phones first: left thumb moves, right side acts, generous aim assist, no precise tapping.

## Early-wins timetable

A new reward every minute or two for 15 minutes. Rename the rows per genre; keep the timings.

| When | Reward |
|---|---|
| 5 s | Core action already working |
| 30 s | First small payoff |
| 90 s | First currency, first upgrade (visibly different) |
| 2 min | Second upgrade of a different kind |
| 3 min | First milestone; first helper, pet or unlock |
| 5 min | New area, mode or tier; rank up |
| 7 min | Third kind of upgrade |
| 10 min | New tool, ability or mechanic |
| 15 min | Second milestone; clear view of the long-term goal |

Rule: if a new player goes two minutes without a reward in the first 15, it is too slow.

## Progression ladders

Run at least three at once so something is always close to finishing.

- **Short (minutes):** tool, speed, capacity or stat upgrades.
- **Medium (sessions):** areas, tiers, helpers or pets, a machine or base that visibly grows.
- **Long (weeks):** collection book, ranks, rebirth or prestige, cosmetics, medals.
- **Rank bar** with fast early ranks. **Starter goals:** eight easy tasks, first one pre-ticked.
- Every upgrade must be visible in the world, not only a number.
- Offline progress where the genre allows it, capped at a few hours ([[18 - AFK Idle and Offline Systems]]).
- First rebirth reachable inside the first session.

## Social standard

- Lobby or shared world for about 12 players where progress is on show.
- Start anything solo or as a crew of up to four; friends can join midway.
- Shared rewards so nobody loses by teaming up; small bonus per extra crew member.
- Content never scales beyond what one player can finish.
- Private servers are free.
- Competitive genres replace "crew" with fair matchmaking and a party queue.

## Feedback rules

- Per action: small pop, pitch-varied sound, tiny "+number", light phone haptic.
- Per milestone: chime, flash, tick on a checklist.
- Per big moment: lights, music, confetti, short camera move.
- Per jackpot (rare reveal, rebirth): wind-up, flash, sting, server-wide announcement, skippable.
- Strong contrast between done and not done, in brightness as well as colour.
- Moderate effects beat extreme ones. Reduced-effects setting.
- Full treatment, with timings, in [[13 - Game Feel and Juice]].

## Launch scope for one person

One core loop, four areas or the equivalent, three upgrade types, lobby, crews, tutorial, one daily reason to return, collection book, shop. Everything else waits until the game passes the day-14 gates in [[00 - Start Here]].

## Technical standard

See [[11 - Tech Stack Standard]]. In short: server decides everything that matters, streaming on, session-locked saving, standard analytics events (every tutorial step, each early-wins row, each upgrade, solo or crew, session length), default Roblox chat and age settings, no personal data.
