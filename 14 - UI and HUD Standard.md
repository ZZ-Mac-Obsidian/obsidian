# UI and HUD Standard

The look, layout and motion of every screen. Slop games share a recognisable interface style (chunky, bright, outlined, bouncy) because it reads on a small phone and signals "simulator" at a glance. Use that language, then give each game its own palette, icon set and one signature flourish. Feel rules are in [[13 - Game Feel and Juice]]; the shop's contents are in [[03 - Monetization and Shop Standard]].

Sizes and timings are rule-of-thumb starting points. Check engine class and property names against current Roblox docs before use.

## The style in one paragraph

Rounded rectangles with thick dark outlines. Big white bold text with a dark outline so it reads over anything. A soft top-to-bottom gradient on every panel and button (lighter at top). A darker "lip" along the bottom edge of buttons so they look pressable. Glossy, slightly 3D icons, one object each. Saturated colour used with intent: green means buy or confirm, red means close or danger, gold means premium, rarity colours mean rarity and nothing else. Everything bounces a little when it appears or is touched.

## HUD layout

Phones in landscape are the design target. Thumbs live in the bottom corners, so the centre and upper edges are for information.

```
+--------------------------------------------------------------+
| [Roblox top bar]      OBJECTIVE LINE / event timer   [gear]  |
|                                                              |
| [Shop ]                                                       |
| [Index]                                        offer / boost |
| [Pets ]                                        timers        |
| [Rebir]                                                       |
|                                                              |
| $ 12.4K  (+1.2K/s)                              [action]     |
| gems 310                                      [action][jump] |
| (thumbstick)        [ hotbar / tool slots ]                  |
+--------------------------------------------------------------+
```

- **Left edge, vertical stack:** three to five square menu buttons, icon over a short label. Order by use: Shop, Index or Pets, Rebirth, then extras.
- **Bottom left, above the thumbstick area:** currencies, each as icon + number, the main one largest with its per-second rate beside it.
- **Top centre:** the single objective line, and under it any live event timer.
- **Right side:** contextual action buttons near the jump button on phones; boost timers and a small offer tile higher up.
- **Bottom centre:** hotbar or tool slots, only if the game has tools.
- **Top right:** a small settings gear. Keep clear of Roblox's own top bar.
- **Maximum five permanent buttons.** Everything else lives inside a menu.
- Leave the centre of the screen empty. That is where the game is.

## Sizes

- Touch targets at least 48 by 48 pixels on a phone; main HUD buttons nearer 64 to 80.
- Body text no smaller than about 14 pixels on a phone; numbers the player watches at 24 or more.
- Size with Scale, not fixed pixels, and lock shapes with aspect-ratio constraints so squares stay square. Put text-size limits on scaled text so it cannot shrink into mush.
- Respect safe areas: notches, rounded corners and Roblox's top bar. Test at a small phone, a tablet and a wide monitor.
- Outlines 2 to 4 pixels; corner radius about 15 to 25% of the element's height.

## Colour and type

- **Palette per game:** one background tone for panels, one accent, plus the fixed meaning colours below. Five colours total is plenty.
- **Fixed meanings:** green = buy, claim, confirm. Red = close, cancel, danger. Gold or yellow = premium and Robux. Blue = neutral info.
- **Rarity colours, never reused for anything else:** Common grey, Uncommon green, Rare blue, Epic purple, Legendary gold, Mythic red or hot pink, Secret black with a moving rainbow edge.
- **Fonts:** one chunky display face for numbers, titles and buttons (the Fredoka, Luckiest Guy or Bangers family of looks), one clean face for small text. White fill, dark outline.
- **Robux prices** always carry the Robux icon and sit on the gold or green button; in-game currency prices carry that currency's icon. The two must never look alike.

## Components

Build each once as a reusable component.

- **Button:** states for idle, hover, pressed, disabled and "cannot afford" (greyed with red price). Optional notification badge.
- **Panel or window:** title bar, big red close button top right, optional tabs down the left side, scrolling content. One window open at a time.
- **Card (item, pet, pass):** rarity-coloured frame, 3D preview of the model (not a flat picture where a model exists), name, one-line effect, price button, "Owned" or "Equipped" state, a "New!" corner tag.
- **Currency counter:** icon, rolling number, bump on change, small "+" button only if the currency can be bought.
- **Progress bar:** fill with a moving shine, numbers on top ("62 / 100"), and a marker for the reward at the end.
- **Toast:** small message sliding in from an edge, stacking up to three, gone in about 3 seconds.
- **Reward pop-up:** the centre-screen "You got!" card for anything Moment-sized or larger.
- **Billboards in the world:** price signs, income per second over earners, name and rarity over characters, overhead player tags with rebirth count. Fade them with distance.
- **Prompts:** a ring on the ground plus a floating key or tap hint for anything interactive.

## Motion

Interfaces in these games are never still when touched and never moving when not.

| Event | Motion | Time |
|---|---|---|
| Button hover (PC) | grow to 105% | 0.1 s |
| Button press | shrink to 92% | 0.06 s |
| Button release | spring to 106%, settle at 100% | 0.18 s, overshoot ease |
| Window open | scale from 80% with overshoot, fade in, backdrop dims to about 40% | 0.25 s |
| Window close | scale to 90% and fade | 0.12 to 0.15 s |
| Tab switch | content slides a short way and fades | 0.15 s |
| List appears | items pop in one after another, 0.03 s apart | under 0.5 s total |
| Counter change | number rolls, counter bumps to 115% | 0.4 to 0.8 s |
| Affordable upgrade | slow pulse 100% to 106% | 1 s loop |
| Toast | slide in with slight overshoot, hold, slide out | 0.2 in, 3 hold, 0.2 out |
| Cannot afford | two quick sideways shakes | 0.2 s |

Rules: opening is slower than closing; nothing takes longer than 0.3 s to become usable; input is accepted during animations; idle loops are limited to things that want attention (a claimable reward, an affordable upgrade, a live offer).

## Screens every game has

- **Shop:** see [[03 - Monetization and Shop Standard]].
- **Index or collection book:** a grid of every character by rarity. Owned ones in colour, missing ones as dark silhouettes with "???". A completion percent and a reward per finished row.
- **Inventory or pets:** grid with sort by rarity and power, equip-best button, multi-select delete with confirmation, lock for favourites.
- **Rebirth:** what resets, what is gained, a progress bar to the requirement, one big button.
- **Rewards hub:** daily reward, playtime gifts, group reward and codes behind one button with a badge.
- **Settings:** music, effects, reduced effects, hide others' effects, fast hatch, low-detail mode. Saved.
- **Odds screen:** opened from a clearly worded "Odds" button on anything random. See the rules in note 03.
- **Welcome back:** offline earnings summary on join. See [[18 - AFK Idle and Offline Systems]].

## First-session interface

- Show only what the player can use. The first minute has the objective line, the currency and nothing else. Buttons arrive one at a time as their feature unlocks, each with a pop and a pointing arrow.
- A bouncing arrow or a soft pulsing ring marks the next thing to press. No blocking text boxes.
- No offers, pop-ups or shop prompts until the tutorial is finished.

## Devices

- **Phone:** everything reachable by thumbs; no hover-only information; no tiny close buttons.
- **PC:** hover states, keyboard shortcuts shown on buttons, mouse wheel scrolling.
- **Controller:** every screen navigable by stick with a visible selection; back button closes.
- Hide the HUD during Jackpot reveals and cutscenes; bring it back with a fade.

## How to build it

- Reusable components driven by a theme table (colours, fonts, corner sizes) in shared config, so a new game is a new theme.
- Motion through the engine's tween system on a scale object attached to each element, so layout is never disturbed.
- 3D previews in cards use the engine's viewport frames; reuse a small pool.
- If image generation or a UI generation tool is available, use it for icon sets and panel art in one consistent style, and ask before spending paid credits.

## Checklist

- [ ] Readable and tappable on a small phone held in two hands
- [ ] Five or fewer permanent buttons; centre of screen clear
- [ ] Every button has pressed, disabled and cannot-afford states
- [ ] Robux and in-game prices cannot be confused
- [ ] Rarity colours used for rarity only
- [ ] Windows open in 0.25 s or less and close faster
- [ ] New features unlock their button with a pop and an arrow
- [ ] Safe areas respected on notch phones
- [ ] One signature flourish that belongs to this game alone

Deeper reference: `References/Filhao Roblox Vault/04 UI and GUI/`, `09 Visual References/` (screenshot boards of real game interfaces), `11 LihFolk V2/05 UI and UX/` and `21 LihFolk UI Design System/`.
