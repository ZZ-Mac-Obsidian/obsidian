# Luck, Markets and First Purchase

Four systems that decide whether a slop game feels exciting and trustworthy: the luck system, the market, the buying flow, and the opening minute. Each is written so it can be built fair, because in this genre trust is what the rating, the return visits and the spending all rest on.

"Market" here covers both meanings: the in-game shop whose stock changes, and players trading with each other. Tags: (official) Roblox docs read 11 Nov 2026, (rule of thumb) starting points, (reference) worked through in the downloaded vaults.

Related: prices and rules in [[03 - Monetization and Shop Standard]], curves in [[19 - Economy and Numbers]], reveal staging in [[13 - Game Feel and Juice]].

---

## Part 1. The first minute

The opening is a planned run of small wins, close together, each a little bigger than the last. The aim is that inside sixty seconds the player has done the verb, been rewarded, bought something, and seen something they want.

### The beat sheet

| Time | Beat | What the player feels |
|---|---|---|
| 0 to 3 s | Spawns facing the thing to do, already moving or one tap away. A number ticks on the first input. | "It works." |
| 5 s | First pickup or payout, with sound, a pop and a flying "+N". | "That felt nice." |
| 10 to 15 s | Enough currency for the first purchase, which is right in front of them and glowing. | "I can afford that." |
| 20 s | First purchase. Visible change in the world. Income or gain visibly rises. | "I am stronger." |
| 30 s | **First lucky moment:** a reveal that lands on something clearly better than common. | "I got a good one!" |
| 40 s | A glimpse of something far beyond them: a neighbour's glowing rare, a locked world, a huge number on a leaderboard. | "I want that." |
| 50 s | Second and third purchases come quickly; a progress bar is already a third full. | "This is going fast." |
| 60 s | One clear next goal on screen, a minute or two away. | "Just one more." |

Then keep a reward landing every minute or two through minute fifteen, per the early-wins table in [[01 - Game Standard]], ending with the first rebirth.

### The first lucky moment

- Every new player's first few **free** rolls follow a fixed starter sequence that includes one Rare. It is the tutorial for rarity: they see the colours, the longer reveal, the sound. Say so nowhere and hide it nowhere; it is simply the starting kit delivered with a flourish.
- **Never script, stage or boost a roll the player pays for.** Paid rolls use the real table and the odds shown.
- The starter Rare should earn enough to matter for the first ten minutes, then be naturally outgrown.

### What makes the opening work

- **Front-load generosity.** The first five of anything cost less than the curve says. Starting cash covers the first purchase.
- **Head start.** Progress bars and checklists begin partly filled; the first starter goal is ticked for arriving.
- **Stack the senses** on every early win: motion, sound, number, colour. See the four sizes of feedback in note 13.
- **Escalate.** Each early reward is a bit bigger and a bit louder than the last, so the minute has a shape.
- **Show the dream early.** A new player should see the best thing in the game, owned by someone else, before the first minute ends.
- **End each beat on the next want.** The moment something is bought, the next thing becomes visible with its price.
- **Nothing in the way:** no menu, no text box that must be read, no offer, no long load.

### Keep it honest

The opening is generous, not deceptive. The game after minute fifteen must still be the same game, slower. If players feel the early pace was bait, the first-session numbers look good and the day-1 return and the rating collapse.

---

## Part 2. Fair luck

A luck system is fair when the chances shown are the chances used, nobody can tamper with a roll, bad streaks have a ceiling, and every result is worth something.

### Build it as data

- **Every random source is a named, versioned table in shared config.** No odds written inside scripts.
- **One table feeds everything:** the roll, the odds screen, the index, the "1 in N" labels. They cannot disagree because they read the same numbers.
- **Roll in two steps:** pick the rarity tier (a list of six to ten), then pick the item inside the tier. Simple, fast and easy to check.
- **Mutations and sizes roll separately** after the item, from their own small tables.

### Roll it on the server

- All rolls happen on the server with a random generator the client never sees. The client receives the result and plays the reveal.
- Never send a seed or a future result to the client, not even to pre-load the animation.
- Rate-limit roll requests and check the player can pay before rolling.
- Deduct the cost and grant the result in one step, then save.

### Luck boosts

- Luck multiplies the weights of the higher tiers. Cap total luck so the table cannot be flattened.
- Show the **current** odds, with the player's luck applied, on the odds screen. If luck can be bought, that is required (official).
- Say what each boost does in numbers ("Rare and above 2x more likely for 15 minutes").
- Use a handful of fixed luck levels rather than continuous values; simpler to show and to test.

### Pity: a ceiling on bad streaks

- A counter per tier guarantees that tier or better within N rolls. It resets when that tier or a higher one drops.
- **Publish the rule** ("Epic or better guaranteed within 50 rolls") and show the counter. Hidden pity gets found within days and reads as a secret.
- Know what it does to the real rate: with a 0.6% chance and a guarantee at 90, the effective rate becomes about 1.4% and most players hit the guarantee rather than the chance (reference). Show the effective rate, not only the base chance.
- In a multi-roll pack, evaluate the counter roll by roll in order. Checking once per pack is the commonest pity bug.
- Decide and document: does a higher tier reset a lower counter (usually yes), and does a guaranteed result count toward the next tier's counter (it should).

### Every result has value

- Duplicates feed something: fusing three into the next tier, selling for currency, filling a mastery bar. A roll should never feel wasted.
- Duplicate protection on the top tier only, if at all; it changes the odds per player and removes duplicates as a resource.

### Check it

- Before launch, simulate a million rolls per table and compare with the configured odds. Repeat whenever a table changes.
- In live play, count rolls and top-tier hits per table per day and compare with the expected rate.
- Log the table name and version with every notable drop, so a disputed result can be explained.

### Show it

- An **Odds** button, with the word, on every random source; the full list with percentages summing to 100.
- "1 in N" beside each item in the index.
- A server-wide message when someone lands a top tier. It proves the odds are real, and one player's luck becomes everyone's event.
- A personal luck log ("Your last 20 rolls") is cheap and builds trust.

### Paid randomness

The full required list is in note 03: complete odds before purchase, live odds under boosts, a policy check per player with restricted players given a non-random path, trading gated separately, and one config switch to turn it all off. The recommended default remains free rolls on earned currency, with Robux selling boosts and guaranteed items.

### Not fair, and not built

- A reveal staged to look like it nearly landed on something better.
- Odds that quietly worsen as a player spends or improves.
- Different odds for different players without saying so.
- A "limited" pool that returns the day after it ends.
- Any paid roll with a fixed outcome.

---

## Part 3. The market

### A. The rotating shop

The shared, timed shop is the heartbeat of grow, steal and collect games: stock changes on a public clock and everyone looks at once.

- **Restock on a fixed interval** (every 5 minutes is the genre norm), derived from server time so every server and player sees the same countdown.
- **Stock is rolled from a table** like any other luck source: common items almost always present, rare ones occasionally, a top item rarely. Publish the chances.
- **Per-player stock,** so one player cannot buy out the server. Limited quantity per restock per player.
- **A visible countdown** on the shop sign and the HUD. The seconds before a restock are when the whole server gathers.
- **Announce rare stock** to the server when it appears.
- **Restock now** as a small product is acceptable when the natural wait is honest and short. Rewarded ads are a good fit here.
- **A daily deal** that really is different each day and really ends.
- Shared conveyors work the same way: one stream everyone sees, first to pay gets it, so a rare appearing is a scramble.

### B. Player trading

Trading adds a long-lived social economy and a great deal of risk. Add it after the game has proved it will live, never at launch.

**What it changes:** rare items become a store of value, players invent a de facto currency item, duplication bugs become catastrophic, and scams and off-platform selling arrive. Every source of items now matters permanently, because every copy lives forever.

**Decide what can be traded**

| Binding | Use for |
|---|---|
| Tradeable | collectibles and cosmetics meant to circulate |
| Tradeable after a cooldown | fresh drops and anything purchased |
| Never tradeable | progression power, starter items, premium currency |

**Formats, simplest first**

1. **Direct trade window** between two players in the same server. Start here.
2. **Trading hub** area or server.
3. **Listing board** across servers ("I offer X, want Y"), needing escrow and a mailbox.
4. **Fixed-price market** in soft currency. Most liquid, most abused: bots, sniping, price manipulation.

**The fair trade window**

- Both sides add items; both see everything offered.
- Any change by either side clears both confirmations.
- Two-step confirm with a short countdown (three to five seconds) after both accept, during which either can cancel.
- A plain summary before the final accept: "You give ... You receive ...".
- A warning when a trade looks very lopsided by recent-trade value, without blocking it.
- The swap is one atomic step on the server: both inventories change together or neither does. Session-locked profiles; no trade while either profile is saving.
- A trade history each player can open.

**Protecting players**

- Trading unlocks after real progress (a playtime and rebirth requirement), which makes throwaway accounts costly.
- A cooldown before newly obtained items can be traded.
- Caps on how much a young account can receive per day.
- Check each player's paid-item trading policy flag and block where restricted (official). Roblox's regional pricing guide also advises trading paid items only between players at the same price level (official).
- Rate-limit every trade and market request.
- Report and decline buttons; never show off-platform contact details.

**Showing value without being gamed**

- Derive values from completed trades using a median over many trades between different pairs of players. A last-trade price can be set by two friends in one swap.
- Ignore trades involving very new accounts.
- Prefer a lopsided-trade warning to a precise price tag.

**Keeping the economy healthy**

- Sinks players want: fusing, upgrading, crafting, all consuming copies.
- New top tiers rather than more copies of old ones.
- Limited items with a published final count.
- A small flat fee or a consumable "trade ticket" per trade as a sink. Taxes above roughly 10 to 15% push trading out of the system (reference). Never take a cut that feels like taxing a Robux purchase.

---

## Part 4. Easy purchase

Easy means the player who wants to buy can do it in seconds and knows exactly what they are getting. It does not mean buying by accident: purchases a player did not intend are what Roblox's rules forbid and what cost Fortnite's maker $245 million. Clear and quick is both the honest design and the one that converts.

### The path

1. **Find:** the Shop button is always visible; the relevant item is also offered at the place it is needed (a stall by the conveyor, a sign on the storage).
2. **Understand:** the card shows a picture, one line saying exactly what it does in numbers, the price with the Robux icon, and whether it is permanent or timed.
3. **Tap once** on a dedicated price button that does nothing else.
4. **Confirm** in Roblox's own purchase prompt.
5. **Receive at once:** the effect is live within a second, with a "Purchased!" pop sized as a Moment, the item's effect visibly switching on, and the card changing to "Owned" or the timer appearing.

Two taps from wanting to having, with one honest confirmation in between.

### Removing friction that helps nobody

- Prices shown before the prompt, read live from Roblox so they are always right and regional pricing applies.
- The shop opens instantly and remembers the last tab.
- Not enough in-game currency? Show what is missing and the fastest free way to earn it, with the paid option beside it.
- Passes take effect without rejoining.
- A purchase is never lost: grant, save, then confirm the receipt; re-grant on rejoin if a save failed.
- "Buy 1, 3, 10" in a row so a bulk buyer does not repeat the flow.
- Gifting as its own clear button.
- Controller and phone can both complete a purchase comfortably.

### Friction to keep on purpose

- Roblox's confirmation prompt, always.
- A buy button that never shares a place or input with a gameplay action.
- No prompt during the tutorial, active play, loading, on joining, right after a loss, or within a second of a screen change.
- A second confirmation for anything large or irreversible in in-game currency.

### The first purchase

Most players never buy; those who buy once are far more likely to buy again. So the first offer should be the best value in the game.

- **One starter pack, once only,** around 79 to 149 Robux: a good early character or a permanent small boost plus some currency. Plainly better value than anything else, and say so only because it is true.
- **When:** not before the tutorial ends. A card in the shop and a small HUD tile from about minute five, when the player already knows what the contents are worth.
- **No fake clock.** If it is a once-only offer, it stays available. A countdown that is not real, or that restarts, is against the rules (official).
- **Value shown concretely:** "Earns 10x your best character", not "Amazing deal".
- **After buying:** a celebration, the benefit felt immediately, and no second offer straight away.

### Where spending fits the game

Offer at the moment of wanting, not the moment of pain.

| Moment | Honest offer |
|---|---|
| Storage full on return | "Longer storage would have earned X more" beside the Claim button |
| Rare appears on the conveyor, just out of reach | nothing mid-chase; the shop's guaranteed character is there afterwards |
| Boost timer about to end | a "+" beside the timer |
| Server is lively | a server-wide boost button everyone can see used |
| Collection one short of a row | the direct-purchase version of that character |
| After a loss | nothing |

### Measure the funnel

Shop opened → item viewed → prompt shown → purchased. A big drop between viewed and prompt means the value is unclear or the price is wrong; between prompt and purchased means the price surprised them. Also track time from first join to first purchase.

---

## Checklist

**First minute**
- [ ] Acting within 3 seconds; first purchase by 20; first lucky moment by 30
- [ ] The best thing in the game is seen before 60 seconds
- [ ] Starter sequence applies to free rolls only

**Luck**
- [ ] Every table is named, versioned config feeding roll, odds screen and index
- [ ] Server rolls; client only reveals
- [ ] Pity rule published and counter visible; packs evaluated roll by roll
- [ ] Million-roll simulation matches configured odds
- [ ] Odds button on every random source; live odds under boosts

**Market**
- [ ] Restock clock from server time, countdown visible, stock per player
- [ ] Trading held back until after launch; atomic swaps; two-step confirm
- [ ] Unlock requirement, cooldown on new items, policy flag checked

**Purchase**
- [ ] Two taps and one Roblox confirmation from wanting to having
- [ ] Effect live within a second; nothing ever lost
- [ ] No prompts in tutorial, play, loading or after a loss
- [ ] One once-only starter pack, shown from about minute five, no fake clock

Deeper reference: `References/Filhao Roblox Vault/11 LihFolk V2/48 Economy Design Deep Dive/Drop Tables Rarity and Pity Systems`, `Player-Driven Trading Economies`, `11 Monetization Publishing and Live Ops/Paid Random Items and Odds Disclosure in Practice`, `Developer Products and ProcessReceipt`, `58 Player QoL and Game Tweaks/Confirmation and Undo Patterns for Destructive and Paid Actions`.
