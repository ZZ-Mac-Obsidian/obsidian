# Build Order

The sequence for making every game, from idea to day 14, and what "good enough to move on" means at each step. The order exists because the expensive mistakes are all about sequence: art made before the loop is fun, a shop built before anyone wants to stay, a launch before the first minute works.

Each step ends with something the owner can press Play on. The builder stops, says what works and what does not, and waits.

## The principle

**Prove fun with grey boxes, then make it beautiful, then make it sell.** Feel is the exception: sound, numbers and bounce go in at step 1, because without them nobody can tell whether the loop is fun.

## Step 0. Pick and pitch (before any building)

- Demand check from [[09 - Slop Game Research]]; blueprint from [[20 - Slop Game Blueprints]] or [[12 - Genre Playbooks]].
- Write the one-sentence twist, the 15-second clip, the title (method in [[24 - Names and Titles]]), and sketch the thumbnail. If the thumbnail cannot show the twist, change the idea, not the thumbnail.
- Search Roblox for the name and premise.
- Fill in [[07 - Build Prompt Template]].

**Gate:** someone who has not heard the idea can say what you do in the game after seeing the sketch.

## Step 1. The toy

The core action alone in an empty place, with grey boxes, on PC and on a phone-sized screen.

- The action, its number, its sound with pitch variation, its floating "+N", the object's squash.
- Server-checked from the start, so nothing is rebuilt later.

**Gate:** it is pleasant to do for two minutes with nothing to earn. If not, stay here. Nothing later fixes a dull toy.

## Step 2. The loop

Action → reward → spend → stronger action.

- Main currency, the counter with its roll-up and flying coins, the first three upgrades, the first earner or gate.
- All numbers in the shared config from [[19 - Economy and Numbers]].
- Saving, with a proper profile library, from this step on.

**Gate:** a tester plays ten minutes without being told what to do next and wants to continue.

## Step 3. The twist and the tension

The thing that makes this game its own: stealing, the hazard, the stat that changes the course.

- Full rules, the telegraphing, the counterplay, new-player protection.
- Tested with at least three or four players at once.

**Gate:** losing feels fair and a little funny; winning feels earned; exploits tried and closed.

## Step 4. Collection and rarity

- The rarity table, the conveyor or egg, the reveal sequence, the index screen. Fair-luck rules and the rotating shop are in [[25 - Luck Markets and First Purchase]].
- Placeholder characters are fine: coloured blobs with rarity colours.

**Gate:** a rare result makes the tester react out loud, with placeholder art.

## Step 5. Art pass

Now the game is known to be fun, make it look like something.

- Characters first (they are the thumbnail), then the base and hub, then the world. See [[04 - Blender Pipeline]].
- One character through the whole pipeline (model, materials, rig or procedural motion, effects, in game) before the batch.
- Lighting, sky, palette.

**Gate:** a screenshot looks like it belongs on the Home page.

## Step 6. Animation, effects and sound pass

- Character idles and spawns, world object motion: [[15 - Animation Standard]].
- The effects kit and rarity ladder, the full sound list, music: [[16 - VFX and Audio Standard]].
- Revisit every event against the four sizes in [[13 - Game Feel and Juice]].

**Gate:** rarity is obvious with the sound off and with eyes closed. A jackpot is unmistakable.

## Step 7. Interface pass

- Final HUD, windows, cards, components and motion: [[14 - UI and HUD Standard]].
- Buttons unlock one at a time through the first session.

**Gate:** playable on a small phone with two thumbs; five or fewer permanent buttons.

## Step 8. First session and tutorial

- The guided first minutes, objective line, beams and arrows: [[01 - Game Standard]]. The second-by-second opening is the beat sheet in [[25 - Luck Markets and First Purchase]].
- Timed fresh-save playthroughs against the early-wins table until every row lands on time.
- First rebirth reachable in the first session.

**Gate:** a new player is acting within 5 seconds, has their first upgrade by 90 seconds, and never waits two minutes for a reward in the first fifteen.

## Step 9. Return reasons

- Offline earnings and the welcome-back screen, playtime gifts, daily reward, daily quest: [[18 - AFK Idle and Offline Systems]], [[02 - Engagement Playbook]].
- Rebirth depth, index rewards, leaderboards, friend boosts.

**Gate:** closing the game and reopening it an hour later is rewarding, and there are clear goals left for next week.

## Step 10. Shop and monetization

- The standard shop, passes, repeatable products, receipts, odds screens, policy checks: [[03 - Monetization and Shop Standard]].
- The buying flow and the once-only starter pack from [[25 - Luck Markets and First Purchase]].
- A real test purchase of each kind.

**Gate:** every item says exactly what it gives; nothing prompts during the tutorial or active play; a free player can finish everything.

## Step 11. Hardening

- Low-end phone pass with a full server; streaming; particle budgets.
- Exploit review of every remote; rate limits.
- Data: leave mid-action, server shutdown, two devices at once.
- Analytics events firing for the funnel.

**Gate:** steady frame rate on a weak phone; no way to gain currency from the client; no lost progress.

## Step 12. Listing

- Icon, three to five thumbnails, video, title, description: [[17 - Icons Thumbnails and CTR]].
- Everything in [[05 - Publish Checklist]].

**Gate:** the thumbnail checklist passes at 150 pixels next to real competitors.

## Step 13. Launch and the first 14 days

- Publish, small ad test, share links: [[06 - Marketing Playbook]].
- Daily: bounce, day-1 return, session length. Fix the worst tutorial step first.
- First content update inside week one: [[22 - Live Ops and Updates]].
- Day 14: keep, fix or kill using the gates in [[00 - Start Here]].

## How long

A solo developer with an AI builder and the shared skeleton: steps 1 to 4 in days, 5 to 12 in one to two weeks, for a slop-genre game. The second game on the same skeleton is much faster because steps 2, 7, 9, 10 and 11 are mostly reuse. Trend entries may compress steps 5 to 7; never compress 1, 3 or 8.

## What carries over between games

| Reused as is | New each game |
|---|---|
| Data, receipts, analytics, networking | The core action and its feel |
| Interface components and motion | The twist |
| Shop, rewards hub, settings, index | Characters, names, palette, music |
| Offline earnings, daily systems | Config numbers |
| Effects kit and sound structure | Icon, thumbnails, title |

Keep the reusable parts in a template place and a shared code package. Never publish the template unchanged: near-duplicate place files lose discovery priority.

## Rules for the builder at every step

- Play it in Studio after each change, on a phone-sized screen too. Report what was tested and what could not be.
- Look at screenshots of the result, not only the code. Interfaces and art are judged by eye.
- Keep a short state note in the game folder: done, in progress, known issues, decisions and why.
- Ask before anything that spends Robux, money or paid generation credits, publishes, or changes account settings.
- If a standard in this vault is wrong, outdated or worse than an alternative, say so and recommend the better option.
