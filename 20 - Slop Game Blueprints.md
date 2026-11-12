# Slop Game Blueprints

The fast, silly, meme-flavoured games this vault is mainly for: "+1" stat games, "Steal a ..." tycoons, "... for Brainrots" hazard runs, roll-for-rarity games, tappers and grow-a-thing idlers. Each blueprint gives the loop, the first minute, the numbers to start from, what to sell, what makes it feel good, and what kills it. Wider genres are in [[12 - Genre Playbooks]].

Tags: (official) Roblox docs, (measured) public Roblox API or tracker figures recorded in the reference vaults in Oct to Nov 2026, (rule of thumb) a starting point to tune by playing.

## What all of these have in common

Every chart-topping slop game of 2025 to 2026 is a known loop plus one sentence of difference:

| Known loop | Plus one twist | Result |
|---|---|---|
| Collect and earn on a base | other players can steal it | Steal a Brainrot |
| Steal a Brainrot | a speed-gated chase | Steal An Egg |
| Collect and earn | the world (a wave) takes what you carry | Escape Tsunami for Brainrots |
| +1 stat every step | more speed makes the course harder | +1 Speed Keyboard Escape |
| Pet collection | the pet is the mount | Ride A Pet |
| Planting | defeated enemies become income units | Plants vs Brainrots |

So the builder's first job on any new game is to write that sentence. If the twist cannot be seen in the thumbnail, it is not a twist yet.

**The seven parts every slop game needs**

1. **A verb a seven-year-old gets from a 15-second clip.** Walk, grab, tap, roll, throw.
2. **A number that goes up every second** and is shown big: speed, cash per second, power.
3. **A collection with rarity.** Characters, pets or items in six or more tiers, each visibly fancier.
4. **Something at risk.** Other players, a hazard, or a hard course. Loss always has a counterplay.
5. **A base or avatar that shows off progress** to the rest of the server.
6. **Rebirth.** A reset that makes the next run faster, with a visible badge.
7. **A weekly reason to return.** New characters, a new world, an event at a fixed time.

**Server size is a design choice (measured):** steal and hazard games run 5 to 8 players per server so each has a base and a rival; +1 obby games run about 22 so the course is a crowded stage; roll games run about 20.

**Sessions are short (measured, third-party):** about 9 minutes for the biggest +1 game, 15 to 16 for steal games. Roblox credits at most 60 minutes of playtime per player per day (official). Design for several short visits a day, not one marathon. See [[18 - AFK Idle and Offline Systems]].

## Theme and characters: the "brainrot" layer

- The theme is a skin over the loop: meme creatures, food with faces, animals crossed with objects, absurd names. It should be funny in a thumbnail before anyone plays.
- **Invent the characters.** The original Italian-brainrot memes have contested ownership; one hit had to remove a character in a licensing dispute and its owners have sued clones (third-party press). Use the style (two unrelated things fused, a rhyming nonsense name, a deadpan face), never the existing characters, names or art.
- A character recipe that works: `animal or creature` + `everyday object or food` + `rhyming or sing-song name` + `one exaggerated feature`. Give the builder freedom here; this is where a game gets its own identity.
- Make 30 to 40 characters for launch across the rarity tiers, then 3 to 5 new ones a week. Rarer means bigger, glowier, more animated, louder. See [[04 - Blender Pipeline]] and [[16 - VFX and Audio Standard]].
- Mutations (Gold, Diamond, Rainbow, seasonal) multiply the collection without new models: same mesh, new material, colour and particle.

## Blueprint A: "+1" stat game

**One line:** a stat rises with every step, second or click, and a course or gate tests how far it gets you.

**Loop:** move or act (+1 stat) → attempt the course → fail and restart already stronger, or finish for a Win → Wins buy multipliers, pets and the next world → rebirth.

**First minute**
- 0 to 5 s: the counter above the head is already ticking up, with a sound on every tick.
- 10 s: the course is in view from spawn; the player tries it.
- 30 s: first fall. They respawn visibly stronger. Failure is progress.
- 60 s: first Win or first upgrade pad (a treadmill, a multiplier) near spawn.

**Make the twist do work.** The stat must change how the game plays, not only what gates open: more speed is harder to steer, more size knocks things over, more jump overshoots platforms. Each new world should add a movement rule (ice, bounce, moving parts), not just a bigger number.

**Starting numbers (rule of thumb)**

| Thing | Start from |
|---|---|
| Gain | +1 per step of about 4 studs, or +1 per second |
| First gate | reachable in 20 to 30 s |
| World 1 clear | 3 to 5 minutes for a new player |
| Wins per world clear | 1, then 5, 25, 100 as worlds rise |
| Multiplier pads | x2 for 5 Wins, x5 for 50, x10 for 500 |
| Rebirth | resets stat, keeps Wins; +50% to +100% gain each |
| Pets | 3 equipped, each +10% to +200% by rarity |

**Sells well (measured from the genre leader's public pass list):** a long cosmetic ladder of trails and auras from about 19 to 2,999 Robux, treadmills or gain pads from 79 to 1,199, x2 Wins around 95, more equip slots around 299, sound packs around 85. Almost all fixed-price, so no odds rules apply.

**Feel:** the tick sound is the product. Give it a pitch that climbs with streaks, a trail that thickens with speed, wind lines and a wider field of view at high speed. See [[13 - Game Feel and Juice]].

**Technical:** the server credits the stat from distance it actually measured; never trust a client-reported value. At high speed thin parts get tunnelled through, so use thick collision and simple shapes. Let players hide others' trails.

**Dies when:** the stat only opens gates, every update is the same course with a bigger number, or there is nothing to do with Wins.

## Blueprint B: "Steal a ..." collect tycoon

**One line:** buy random characters, stand them on your base where they earn every second, steal better ones from neighbours and stop them stealing yours.

**Loop:** buy from a shared conveyor or hatch → place on a base slot → it earns per second → collect → upgrade slots, speed, defences → steal from others → rebirth.

**First minute**
- 0 to 5 s: the player is standing on their own base with starter cash, facing the conveyor.
- 15 s: first character bought and walking to its slot. A money number starts ticking above it.
- 30 s: first cash collected with a burst of coins.
- 45 s: they see a neighbour's base with something much rarer on it, and a visible lock timer.
- 60 s: second purchase; the objective line says "Steal one from a neighbour" once new-player protection ends.

**The parts**
- **Base:** one plot per player around a central lane. 8 to 10 slots at first, floors unlock later. An income sign floats over every character.
- **Conveyor or hatchery:** the shared shop. Everyone sees the same stock roll past, so a rare one appearing is a server-wide scramble. That scramble is the best moment in the genre; announce rares to the whole server.
- **Stealing:** grab → carry (slower while carrying, visible to all, alarm on the victim's screen) → reach your own base to keep it. The owner can hit the thief to drop it.
- **Defence layers:** a base lock on a button with a cooldown (for example 60 s locked, then open), a protection window on newly bought characters, cheap traps, and never letting a thief take a player's last earner.
- **New-player shield:** no theft from or by a player in their first 5 minutes.
- **Rebirth:** needs a cash total plus specific characters; resets cash and characters, grants a permanent income multiplier, another slot or floor, and a number on the overhead tag.

**Rarity table to start from (rule of thumb, tune it)**

| Tier | Chance | Income vs Common | Colour |
|---|---|---|---|
| Common | 55 to 65% | 1x | grey |
| Uncommon | 20 to 25% | 4x | green |
| Rare | 8 to 12% | 15x | blue |
| Epic | 2 to 4% | 75x | purple |
| Legendary | 0.5 to 1% | 500x | gold |
| Mythic | 0.1% | 5,000x | red or pink |
| Secret | 0.01% or event-only | 50,000x+ | black with rainbow edge |

One weighted table in shared config feeds both the roll and the odds screen, so the two can never disagree.

**Sells well:** x2 cash, luck, extra slots, faster carry speed, lock upgrades, offline-earnings extension, limited characters, and in-play products (a server-wide luck boost everyone thanks you for). Rules for anything random are in [[03 - Monetization and Shop Standard]].

**Feel:** the purchase walk-in, the per-second cash ticks, the alarm when robbed, the chase, the slam of a base lock. Being robbed must feel dramatic and fair, with a clear way to chase.

**Dies when:** new players are stripped in their first minutes, paying is the only defence, exploiters auto-farm (make every grab, carry and deposit server-checked), or it looks like one of the hundred clones. The original held about 92% of players across 105 clones (third-party).

## Blueprint C: "Escape ... for Brainrots" hazard run

**One line:** run out along a track to grab characters, get back before the wave, lava or monster sweeps it, bank them on your base, buy speed to reach further.

**Why it works:** it keeps the collect-and-earn loop and replaces theft with a world hazard. Losing a carried character to a wave feels fair; losing a placed one to another child does not. The genre leader went from launch to about 5 million concurrent in six weeks (measured, tracker).

**Loop:** base → sprint out → grab up to your carry limit → hazard warning → race back or duck into a safe pocket → place for income → buy speed, carry, slots → rebirth.

**First minute**
- 0 to 5 s: base with empty slots, track straight ahead, nearest characters a few steps away.
- 15 s: one grabbed, carried back, placed. Money ticks.
- 30 to 45 s: first hazard warning: countdown, siren, screen-edge flash. The first wave teaches the rule: carried is at risk, placed is safe.
- 60 s: first +1 speed bought; the next zone is now reachable.

**Rules of the hazard**
- Derived from server time so every player sees the same wave; the server decides who was hit.
- Always telegraphed: sound, countdown, edge flash. A hit with no warning reads as cheating.
- Distance equals rarity. Further zones hold rarer characters; that is the whole risk curve.
- Safe pockets along the track turn a straight run into route planning.
- Vary the hazard per update (double wave, slow tide, zig-zag) before adding bigger numbers.

**Starting numbers (rule of thumb):** wave every 45 s, 8 players per server, carry 1 rising to 7, speed bought in +1, +5 and +10 steps, zone 2 reachable after about 3 upgrades, top zone needing a clearly long-term speed.

**Sells well (measured from the leader's pass list):** speed boost about 129, super speed about 329, double-jump item 160, shield 295, anti-hazard device 699, VIP 175 and a VIP+ at 888 as the price anchor. Keep paid items acting on the hazard or the buyer, not on other players.

**Dies when:** the whole track is loaded on phones (use streaming), paid knock-back gear griefs other players, or the wave never changes.

## Blueprint D: roll for rarity

**One line:** one big Roll button; each roll shows a result with "1 in N" odds; rarer results equip as auras or pets; an index wants filling.

- **First minute:** the Roll button is the only thing on screen. First roll at 3 seconds. A scripted early "1 in 100" inside the first ten rolls (a fixed starter sequence, not a paid roll).
- **Depth:** luck from potions and gear crafted out of low-tier results, biomes or weather that change the table for a few minutes, auto-roll unlocked by rolling.
- **Reveal lengths scale with rarity** and are skippable. See [[15 - Animation Standard]].
- **Sells:** auto-roll speed, inventory slots, cosmetic titles. Luck sold for Robux counts as a paid random item and must update the shown odds live (official).
- **Honest note:** this genre is mostly idle. Playtime past 60 minutes a day earns no discovery credit, and regulation of paid randomness for minors is tightening. Free rolls with earned luck are the safer core.

## Blueprint E: tapper or clicker

**One line:** tap for currency, hatch pets that multiply taps, rebirth, new worlds.

- **First minute:** tap at 2 seconds with numbers flying; first egg affordable at 30 seconds; first pet equipped and following by 45; first rebirth offered at about 5 minutes.
- **The tap must feel great:** squash on the tapped object, a number that flies out, pitch rising with tap speed, a combo meter. Hold-to-tap on phones.
- **Sells:** auto-tap, x2 taps, triple hatch, egg luck, extra pet slots.
- **Dies when:** nothing happens besides bigger numbers. Give each world a small new toy.

## Blueprint F: grow and wait

**One line:** plant or place, wait a short timer, harvest, sell, reinvest; shop stock rotates on a public clock.

- **First minute:** plant at 5 seconds, first harvest by 20, first sale by 30, three plots running by 60.
- **The shared restock clock** (every 5 minutes, same for the whole server) is the hook: everyone gathers at the shop on the tick.
- Growth continues offline. Size and mutation rolls on harvest give a "look what I got" moment.
- **Sells:** speed-up, rare stock, sprinklers or helpers, extra plots.
- **Dies when:** between events there is nothing to do. Add stealing-lite, trading or visitors.

## Mixing blueprints

The strongest new entries splice two: a +1 stat that gates a steal game (speed to out-run the owner), a hazard run whose characters fuse on the base, a tapper whose pets are mounts. Pick one loop as the spine, borrow one mechanic, and stop there.

## Fast-follow rules

- Enter in the first weeks of a rising trend or not at all. Watch Top Trending and Up-and-Coming for a new verb with a rating above 90%.
- Change the verb, hazard or setting, not just the skin. Roblox stops prioritising games whose listing and place file closely resemble existing ones (official).
- Own the name, characters, icon and UI. Mechanics are free to reuse; art and names are where the legal risk sits (third-party press, not legal advice).
- Ship the next mechanic before clones finish copying the last one. Clones can copy a map but not a schedule.
- Expect a 90% fall after the peak. The goal is a steady floor with weekly bumps, then the next game on the same skeleton.

## Where to look deeper

- Teardowns with public pass lists and player figures: `References/Filhao Roblox Vault/11 LihFolk V2/59 Viral and Trend Game Teardowns/`
- The steal formula: `References/Filhao Roblox Vault/02 Game Design/Steal and Collect Tycoon Formula`
- Numbers and curves: [[19 - Economy and Numbers]]
- Build sequence: [[21 - Build Order]]
