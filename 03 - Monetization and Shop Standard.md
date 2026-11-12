# Monetization and Shop Standard

One shop design for every game, what to sell in it, what it costs, and the rules that keep it legal and well rated. Tags: (official) Roblox docs read 11 Nov 2026, (measured) public pass lists of chart games recorded Oct 2026, (third-party) reports and creator claims, (rule of thumb) starting points.

## How the money works

- Roblox keeps 30% of pass and product sales; the creator receives 70% in Robux. Earned Robux cash out at about $0.0038 each (third-party sources agree on this rate from Sept 2025; confirm on the Developer Exchange page).
- **Spend is a discovery signal.** Spend days per user and Robux spent per user are ranking signals, and Roblox says games strong in both retention and monetization "might receive broader distribution" (official). A fair shop that many players use a little helps the game get shown.
- **Most money comes from few players and from repeatable purchases.** Median revenue per paying player is about $0.70; the top 10% of games reach $2.33, the top 1% about $55 (GameAnalytics). About 1 to 3% of daily players buy anything (third-party). One small game reported nearly all income from repeatable in-play products while passes "made nothing" (creator claim).
- **Regional pricing** is on by default for passes and must be switched on for developer products. Prices drop by up to 70% in lower-income regions and never rise (official). Switch it on.
- **Price optimisation** tests prices automatically once a game has about 60,000 transactions in 30 days, and only applies changes that raise total revenue. It needs prices read from Roblox at run time, not typed into scripts (official). So never hard-code a price in the interface.
- **Creator rewards:** 5 Robux a day for each active spender who plays 10+ minutes when the game is among their first three that day; 35% of a new or returning user's first $100 of platform purchases if they arrived by the game's share link, direct link or name search, provided the game holds 100+ daily users for 60 days (official).

## Three kinds of thing to sell

| Kind | Bought | Best for |
|---|---|---|
| **Game pass** | once, kept forever | permanent multipliers, auto features, slots, VIP |
| **Developer product** | any number of times | timed boosts, in-play spectacles, skips, guaranteed items, gifts |
| **Subscription** | monthly | a bundle of comfort perks plus a daily gift, once the game has loyal daily players |

Lead with passes on day one because they are simple to understand. Add repeatable products early because that is where sustained income comes from.

## The standard shop

- Opens only from the Shop button and from clearly labelled stalls in the world. Big red close button top right.
- **Featured banner** across the top: one item, bright gradient, a "New!" or event tag, a real end time if it is limited.
- **Tabs** down the left: Featured, Passes, Boosts, Characters or Eggs (if the game has them), Cosmetics.
- **Cards:** 3D preview or glossy icon, name, one line stating exactly what is received, price button with the Robux icon, "Owned" when owned.
- **Pack sizes** in a row for repeatables: 1, 3, 10 with a real saving on larger packs. Mark one "Best value" only if it is.
- **Gift button** on passes and packs.
- **Odds button**, worded "Odds", on anything random.
- Every purchase goes through Roblox's own purchase prompt.
- Look and motion follow [[14 - UI and HUD Standard]].

## Robux price ladder

Roblox players think in familiar price steps. Use them (rule of thumb, from market observation):

| Tier | Robux | Typical use |
|---|---|---|
| Impulse | 19 to 49 | small boost, one-off spectacle, cheap cosmetic |
| Low | 79 to 149 | starter pack, minor pass, speed boost |
| Core | 199 to 399 | x2 currency, auto-collect, VIP, extra slots |
| High | 499 to 899 | super boosts, big packs, VIP+ |
| Anchor | 999 to 2,999 | top cosmetic, "admin" item, mega pack |

- Have something at every tier. The most-bought items are Impulse and Core; the Anchor makes Core look reasonable and a few players do buy it.
- Passes above about 500 Robux convert poorly unless the value is obvious (third-party).
- The biggest +1 game lists 64 passes from 19 to 2,999 Robux, almost all cosmetics and self-only multipliers (measured). A long ladder means every budget finds a purchase.

## Standard passes for slop games

Pick six to ten for launch. Names and exact effects are the builder's to theme.

| Pass | What it does | Robux |
|---|---|---|
| x2 Cash (or the main currency) | doubles income, forever | 199 to 299 |
| x2 the core stat (speed, power, taps) | doubles gain | 149 to 299 |
| VIP | name tag, chat colour, small income bonus, VIP area or daily gift | 175 to 399 |
| VIP+ | a larger version; mainly a price anchor | 799 to 999 |
| Auto-collect | income goes straight to the wallet | 149 to 299 |
| Offline time extension | offline cap from 2 hours to 12 or 24 | 149 to 249 |
| Extra slots | more earners, pets or equips | 199 to 399 |
| Faster carry or movement | genre-specific mobility | 129 to 329 |
| Fast or triple hatch | opens faster or three at once | 199 to 399 |
| Hazard or base defence item | shield, stronger lock, double jump | 160 to 699 |
| Trail and aura ladder | cosmetics from cheap to absurd | 19 to 2,999 |
| Sound or effect packs | changes the signature sound or effect | 79 to 149 |

Passive-progress passes are explained in [[18 - AFK Idle and Offline Systems]].

## Standard repeatable products

Two to five per game. Bought from the shop or a clearly marked world button, never prompted mid-action.

| Product | What it does | Robux |
|---|---|---|
| Timed boost | x2 income or luck for 15 to 30 minutes; timer on the HUD | 25 to 79 |
| Server boost | the same for everyone in the server; buyer's name announced | 49 to 149 |
| Big moment | a one-off spectacle in the core loop that everyone nearby sees | 25 to 99 |
| Skip or instant | finish a timer, restock now (only for honestly designed waits) | 19 to 99 |
| Starter pack | once only: a good early character or boost bundle, shown in the shop | 79 to 149 |
| Guaranteed character | a specific featured character, bought directly, no randomness | 99 to 799 |
| Reroll token | reroll a mutation or stat | 25 to 49 |

Server-wide boosts are the standout: the buyer gets thanks from the whole server, everyone benefits, and others copy them.

## Random items: eggs, rolls, crates, conveyor luck

These are central to several slop genres and they carry the most rules. Build the compliance in from the start.

**Required (official)**

- **Show every possible outcome and its real numerical chance before purchase,** as percentages summing to exactly 100% (rounding allowed with a note).
- This covers anything bought with Robux **or with in-game currency that can be bought with Robux**, including keys, spin tickets and reroll tokens.
- A long list may live in a pop-up opened by a button with a descriptive word such as "Odds" or "Details". A bare "(i)" icon is not enough.
- **Luck boosts, pity systems and rate-ups are covered.** If they are paid, explain them before purchase and update the displayed odds live while they are active.
- If an outcome can only be obtained once, update that player's remaining odds.
- **Check each player's policy** with the engine's policy service. Where paid random items are restricted for that player, they must not be able to use them. Permitted alternatives: a free earnable path, a fixed disclosed order, a direct guaranteed purchase priced at the expected value, hiding the item, or an error message. Do not hard-code a country list; ask the service, and treat a failed check as restricted.
- **Trading** of paid items needs its own policy check per player.
- Free random rewards earned by play need no odds disclosure. Show them anyway; players like "1 in N".

**House rules on top**

- One weighted table in config feeds the roll and the odds screen ([[19 - Economy and Numbers]]).
- The server rolls. The client only plays the reveal.
- The reveal shows the true result; no near-miss staging.
- A limited egg ends when its timer says.
- Always offer a non-random way to get a featured character (the Guaranteed character product), which also serves restricted regions.
- Put anything random behind one config switch so it can be turned off by region or entirely if rules change.

**Know the risk.** Paid randomness aimed at children is where regulators are moving: the US FTC's 2025 Genshin Impact settlement, restrictions in several countries, and studies linking loot-box spending with problem gambling. A game whose core rolls run on earned currency, with Robux selling boosts and guaranteed items, still earns well and carries far less exposure. That is the recommended default; switch paid rolls on as a deliberate choice per game.

## Rewarded video ads

- A player chooses to watch a short video and receives a reward. Built with the engine's ad service, using a developer product as the reward (official).
- **Eligibility:** owner 13+, ID-verified, public game with at least 2,000 unique visitors a month. Check each player's policy flag for whether ads are allowed (official).
- **Rewards cannot be randomised items** (official).
- Good placements: "Claim x2" on the welcome-back screen, a free timed boost, a free restock, an extra daily spin with a fixed reward.
- Always optional, never needed to progress, never interrupting play.

## Subscriptions

- From 49 Robux a month, or fixed local-currency prices of $2.99 to $14.99. Creator share is 70% in Robux; local-currency plans pay 70% the first month and 100% after (official).
- No bronze, silver, gold tiers. Benefits may not be gated behind extra tasks or revoked (official).
- Worth adding once daily players are loyal: auto-collect, longer offline time, a daily gift and a name tag in one plan.

## Purchase rules

From Roblox's monetization rules (official) and the FTC's $245 million Fortnite order.

- Players "must never be misled, confused, or pressured into purchases in ways they did not intend."
- **Discounts must be genuine and fair.** Not genuine if the item is always "on sale" at the same price. Not fair if offered only for a very short time to pressure. A struck-through price must be one the item really sold at.
- **No false scarcity.** Do not say something is nearly gone or short-lived if it is not.
- **No inaccurate countdowns,** and none that restart for the same item. Roblox's own example is a "deal of the day" showing 24 hours at every login.
- **Calm wording for a young audience:** "View item" and "Open shop", not "GET IT NOW" or "BUY BEFORE IT'S GONE".
- Never open a purchase prompt during the tutorial, active play, loading, on joining, or within a second of a screen change.
- The buy button never shares a position or input with another action.
- No offers triggered by a loss or setback.
- Do not sell relief from an annoyance the game created on purpose.
- Shop text states exactly what is received. Owned items are marked.
- Grant the item, save, and only then confirm the receipt; a purchase must never be lost.

## Where buying is offered

- **The shop**, always one tap away.
- **In the world, at the point of need:** a stall beside the conveyor, a pad beside the rebirth altar, a sign on the offline storage. The player walks up and chooses to interact.
- **On the HUD:** one small featured tile, and a "+" beside a boost timer.
- **Soft upsell inside free screens:** the welcome-back screen shows what a longer cap would have earned; the inventory shows locked extra slots. Information with a button, never a pop-up.
- **First offer timing:** nothing before the tutorial ends. A starter pack card can appear in the shop and as a small HUD tile from about minute five.

The step-by-step buying flow, the first-purchase offer, fair luck and trading are in [[25 - Luck Markets and First Purchase]].

## Measuring

Track per item: views, purchases, revenue, and time from first join to first purchase. Compare payer share and spend per payer with the benchmark Roblox shows for similar games. Move, reprice or replace the bottom third of items every few weeks.

## Checklist

- [ ] Something at every price tier; prices read from Roblox, not hard-coded
- [ ] Six to ten passes, two to five repeatable products, one once-only starter pack
- [ ] Regional pricing on for products as well as passes
- [ ] Anything random: odds screen from the same table as the roll, policy check per player, config switch
- [ ] No prompts in tutorial, active play, loading or after a loss
- [ ] No fake discounts, false scarcity or restarting timers
- [ ] Receipts granted and saved before being confirmed
- [ ] A free player can reach everything

Deeper reference: `References/Filhao Roblox Vault/11 LihFolk V2/11 Monetization Publishing and Live Ops/` (20 notes, including price points, receipts and unit economics) and `References/Kaffein Dev Vault/03 - Reusable Systems/S-purchase-fulfillment-center`, `S-receipt-fulfillment-contract`, `S-ui-shop-catalog-layout`. Sources in [[08 - Sources and Unknowns]].
