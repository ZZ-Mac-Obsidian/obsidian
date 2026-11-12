# Roblox Game Factory

One standard for making Roblox games that get clicked, feel great, bring players back and earn, built mainly for the fast meme genres ("+1" games, "Steal a ...", "... for Brainrots") and usable for any genre. Every game shares the same skeleton, interface, shop, pipeline and launch steps, so a new game is mostly a new twist, a new cast of characters and new numbers.

The vault is written for an AI builder (Claude Opus 5.5) working with a solo developer. Each note says what good looks like and why, gives numbers to start from, and leaves the creative choices open.

## Map

**Decide what to make**

| Note | Answers |
|---|---|
| [[20 - Slop Game Blueprints]] | The main genres in detail: loops, first minute, numbers, what sells, what kills them |
| [[12 - Genre Playbooks]] | Every other genre that charts, and how well each fits one person |
| [[09 - Slop Game Research]] | How quick AI-built games are picked, promoted and paid (creator claims) |
| [[24 - Names and Titles]] | What chart games are called, why those names get clicked, how to name a new one |

**Make it good**

| Note | Answers |
|---|---|
| [[01 - Game Standard]] | What every game shares: first five seconds, tutorial, HUD, early wins, ladders |
| [[02 - Engagement Playbook]] | What Roblox measures and what makes players stay and return |
| [[13 - Game Feel and Juice]] | Why the core action is satisfying; the four sizes of feedback; reveals |
| [[14 - UI and HUD Standard]] | Layout, style, components, motion timings, screens |
| [[15 - Animation Standard]] | Characters, pets, world objects, camera, easing |
| [[16 - VFX and Audio Standard]] | Effects kit, rarity ladder, sound list, music, mixing |
| [[04 - Blender Pipeline]] | 3D models: style, budgets, characters at volume, Blender steps |
| [[19 - Economy and Numbers]] | Cost curves, rarity, rebirth, sinks, tuning method |
| [[18 - AFK Idle and Offline Systems]] | Offline earnings, AFK features, the 20-minute rule |
| [[25 - Luck Markets and First Purchase]] | The first-minute beat sheet, fair luck, rotating shops and trading, the buying flow |
| [[11 - Tech Stack Standard]] | Project layout, tools, libraries, architecture |

**Make it earn and get seen**

| Note | Answers |
|---|---|
| [[03 - Monetization and Shop Standard]] | What to sell, prices, random-item rules, ads, purchase rules |
| [[17 - Icons Thumbnails and CTR]] | Winning the click honestly: icon, thumbnails, video, title |
| [[06 - Marketing Playbook]] | Ads, free reach, picking the idea, riding a trend |
| [[05 - Publish Checklist]] | Everything before and on launch day |
| [[22 - Live Ops and Updates]] | The weekly rhythm, events, reading the numbers, when to stop |

**Do the work**

| Note | Answers |
|---|---|
| [[21 - Build Order]] | The sequence, with a gate at every step |
| [[07 - Build Prompt Template]] | The brief to fill in and hand to the builder |
| [[23 - Free Resources and Tools]] | Free models, sounds, tools, AI generators, licences |
| [[10 - Reference Vaults]] | Two downloaded libraries for depth |
| [[08 - Sources and Unknowns]] | Where every number comes from, and what is unverified |
| [[Games/Scrub Club]] | A complete filled-in example |

## How the factory works

1. **Pick** a blueprint and write the one-sentence twist.
2. **Prove the toy:** the core action alone, fun for two minutes.
3. **Build the loop, the twist, the collection** with placeholder art.
4. **Make it beautiful:** models, animation, effects, sound, interface.
5. **Tune the first fifteen minutes** against the early-wins table.
6. **Add return reasons and the shop.**
7. **List it:** icon, thumbnails, video.
8. **Launch, update weekly, decide at day 14.**

Full sequence and gates in [[21 - Build Order]].

## What makes a Roblox game good

The short version of everything in this vault:

1. **The tile is honest and exciting.** It shows the real verb and the twist, and the player who clicks gets what was promised.
2. **Playing within five seconds.** No menus, no reading.
3. **The core action feels great on its own.** Motion, sound and a number on every input.
4. **A reward every minute or two for fifteen minutes.**
5. **One twist that is its own,** visible in the thumbnail.
6. **A number that always goes up and a collection that is never finished.**
7. **Rarity that is felt.** Rarer is bigger, brighter, louder, longer.
8. **Something at risk, with a fair way back.**
9. **A reason to return in hours, days and weeks.**
10. **Better with friends.**
11. **A shop that is easy to find and never pushes.**
12. **Runs on a cheap phone.**
13. **Updates on the same day every week.**

## What stays the same in every game

- Data saving, receipts, analytics, networking
- Interface components, motion timings, shop, rewards hub, settings, index
- Offline earnings and daily systems
- The effects kit and sound structure
- The build order and its gates

## What changes per game

- The core action and how it feels
- The twist
- Characters, names, palette, music
- The numbers
- Icon, thumbnails, title

## Honest limits

- **Copies of a hit keep almost nothing.** Among 105 "Steal a..." games, the original held about 92% of players (third-party). Roblox stops prioritising games whose listing and place file closely resemble existing ones (official).
- **Roblox ranks on return play over 28 days,** not quick clicks (official). Games that hook and empty out get fewer impressions.
- **Trend windows are weeks.** Peaks fall 90% or more. The aim is a steady floor, then the next game.
- **Most games fail.** Median creator payout across Roblox was about $1,500 over 12 months (press). The factory's edge is speed and a skeleton that improves each time.
- **Much of this vault's market data is third-party or creators' own claims.** Tags say which. Roblox policy changes often; check the live docs.

## Keep, fix or kill (day 14)

Measured in Roblox analytics against the benchmark it shows for similar games.

| Metric | Kill below | Keep above | Reference |
|---|---|---|---|
| Left within 60 s | n/a | under 25% | counts against the game |
| Day 1 return | 8% | 12% | median 10.3% (GameAnalytics 2026) |
| Day 7 return | 1% | 3% | median 1.6% |
| Average session | 7 min | 12 min | median 9.8 min; trend hits run 9 to 16 |
| Rating | 80% | 90% | calm designs reach 93 to 97% |

Between the two columns: fix the first fifteen minutes for one more week, then decide.
