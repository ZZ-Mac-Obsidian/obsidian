# Live Ops and Updates

Keeping a game alive after launch. Slop games rise fast and fall fast; what separates the ones with a steady floor from the ones that vanish is a rhythm of updates. Trackers record cleaning and brainrot games losing 90 to 99% of players within months of stopping (third-party).

## Why it matters to discovery

- Roblox ranks on days played across a 28-day window: day 1, days 2 to 7, days 8 to 28 (official). The last window is only fed by reasons to return in weeks two to four.
- Signals use a moving window and "there is no penalty for games that did not perform well at first" (official). A good update can lift a game that launched weakly.
- Around 40% of the weekly top 100 recommended games were under three months old (Roblox, Q3 2026). New games do get their chance; keeping it is the hard part.

## The weekly rhythm

One update a week, same day, same hour, announced in advance. Saturday is the peak day for Home traffic.

| Day | Work |
|---|---|
| Sunday | read the numbers and feedback, pick the update |
| Monday to Wednesday | build |
| Thursday | content complete; new icon badge and thumbnail made |
| Friday | playtest with a handful of testers; fix |
| Saturday | release at a fixed time with a live moment |

This is the schedule one creator of a 21,000-player game describes (creator claim).

## What an update contains

Pick one headline and two or three small items. Sizes, smallest first:

- **Content drop (every week):** 3 to 5 new characters across rarities, one of them a chase item; a code; a balance pass.
- **Feature (every 2 to 4 weeks):** a new mechanic that changes play: fusing, a new hazard type, trading, a minigame, a pet system. This is what stops clones catching up.
- **World (every 3 to 6 weeks):** a new area with its own look, its own rule and its own top-tier collectibles. Changes the title tag and the thumbnail.
- **Event (monthly or seasonal):** a limited-time mode or currency with exclusive rewards and a real end date.

Rules:
- **Add, never take away.** New content must not make old progress worthless. Put the new best things above the old best things, not in place of them.
- **Each update needs a five-second clip** just like the game did.
- **Ship less, on time.** A small update on schedule beats a big one that slips.

## Live moments

The scheduled spectacle is the genre's signature. Peaks in the big brainrot games line up with these (third-party).

- **Release countdown** in every server ending at the update hour, with the new thing appearing in front of players.
- **"Admin" events:** the developer visibly triggers things for the whole server: rare spawns, a luck surge, a silly hazard, a boss. Run from a server-timed schedule so every server gets it, with a way to trigger by hand.
- **Server-wide luck or x2 hours** at the weekend.
- **Shared goals:** all servers fill one bar towards a reward everyone gets.
- **A guest or crossover** only with permission and only when the game is big enough to matter.

Honesty rules: an event that says it ends on Sunday ends on Sunday and does not return on Monday. Countdowns are real and do not restart for the same item (official).

## Refreshing the listing

With every headline update:

- New title tag with the update's name.
- One new thumbnail showing the new thing, added to the personalised set; retire the weakest.
- A corner badge or recolour on the icon, same silhouette.
- Description's update lines rewritten.
- A short clip for short-video platforms using the share link.

See [[17 - Icons Thumbnails and CTR]].

## Talking to players

- **In game:** an update board near spawn, a "What's new" card on first join after an update, a countdown to the next one.
- **Roblox group or community:** every update posted; a small in-game reward for joining.
- **Codes:** released at like and member milestones and with each update. Cheap goodwill, and a reason to follow.
- **Notifications:** opt-in, 13 and over, limited per player per day. Announce the update or a full offline storage. Never guilt.
- **Patch notes:** short, as verbs, biggest thing first.

## Reading the numbers

Weekly, in Roblox analytics against the benchmark it shows for similar games:

| Number | If it is weak |
|---|---|
| Play-through rate | icon, thumbnails, title |
| Left in under 60 s, and 61 to 180 s | loading time, first five seconds, thumbnail over-promising |
| Day-1 return | first session too slow, no offline reason to return |
| Days 2 to 7 | no daily reason, progression wall around hour two |
| Days 8 to 28 | no weekly content, nothing left to collect |
| Average session | core action dull, or goals too far apart |
| Paying players and spend per payer | shop hard to find, unclear value, wrong prices |
| Rating | unfair loss, pay-to-win feeling, bugs, lost data |

Also read: the funnel of tutorial steps, where upgrade buying stops, Roblox's own feedback summary, and what the nearest competitors shipped this week.

## Operating safely

- **Feature flags in config** so a new system can be switched off without republishing.
- **Test place** separate from the live game; never build in the live place.
- **Version the save data** and write a migration for every change. Lost progress is the fastest way to a low rating.
- **Soft shutdowns:** when updating, move players to new servers with a message instead of cutting them off.
- **Roll back** to the last published version at once if something breaks; apologise with a code.
- **Compensate** for outages generously. It costs nothing real.

## When interest falls

Every one of these games drops after its peak. Decide by the numbers.

- **Still above the day-14 gates:** keep the weekly rhythm.
- **Falling, but with a loyal core:** fewer, larger updates; add depth (trading, fusing, prestige layers).
- **Below the gates for three weeks despite updates:** stop. Move the skeleton, and the lessons, to the next game. Leave the old one running; a floor of players still pays.
- **Relaunch** only with a real new twist and a new listing, never as a re-upload of the same thing.

## A portfolio, not one game

The creators doing this well run several games on one shared skeleton. Expect most to fail the day-14 gates. Each one makes the skeleton better and the next attempt faster. Keep a "lessons" note per game in its folder under `Games/`.

Deeper reference: `References/Filhao Roblox Vault/11 LihFolk V2/38 Live Ops Deep Dive/`, `27 Marketing and Growth/Update Cadence and Hype Cycles`, `Launch Strategy - The First Two Weeks`, `Rescuing a Weak Launch`.
