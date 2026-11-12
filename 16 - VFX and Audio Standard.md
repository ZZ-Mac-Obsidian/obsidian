# VFX and Audio Standard

Particles, light and sound: the layer that turns a working game into one that feels expensive. When and how much is set by [[13 - Game Feel and Juice]]. Values are starting points.

## Effects

### The standard kit

Build these once as reusable, colour-tintable effects and call them by name from anywhere.

| Effect | Use | Recipe |
|---|---|---|
| Sparkle burst | collect, small reward | 8 to 15 small stars thrown outwards, shrinking, 0.4 s |
| Coin burst | cash collected | coin sprites pop up and fall with gravity, then the interface coins fly to the counter |
| Ring shockwave | upgrade, landing, rebirth | a flat ring that expands and fades in 0.3 s |
| Light rays | epic and above | long soft beams rotating slowly behind the subject |
| Confetti | milestones, wins | multi-colour rectangles fired upward, tumbling down over 2 s |
| Glow pulse | affordable, interactive, rare | soft light or outline brightening and dimming on a 1 s loop |
| Trail | speed, carried items, rare pets | ribbon behind the mover, widening with speed |
| Dust puff | landings, doors, footsteps at speed | 3 to 5 soft grey puffs |
| Ground ring | interaction point | dashed circle rotating slowly |
| Beam | guide the player to an objective | line of light from player to target along the ground |
| Aura | rarity on characters | looping particles hugging the model in the rarity colour |
| Screen flash | jackpots only | white or rarity-colour full-screen fade, two to three frames in, 0.3 s out |
| Hazard warning | incoming danger | red edge vignette pulsing with the countdown |
| Speed lines | high speed | thin streaks at the screen edges |

### Rarity ladder

Each tier adds a layer on top of the one below, so rarity is readable from across the map.

| Tier | Layers |
|---|---|
| Common | none |
| Uncommon | faint coloured glow at the feet |
| Rare | glow plus a few floating sparkles |
| Epic | aura particles, soft light on the ground |
| Legendary | aura, rotating light rays, a ground ring, occasional sparkle burst |
| Mythic | all of that, plus a trail and a subtle pulse to the whole model |
| Secret | unique effect made for it: lightning, black flames, a rainbow outline |

Mutations get their own material look: Gold is metallic yellow with glints, Diamond is pale blue and shiny with sparkles, Rainbow cycles hue.

### World and lighting

- Bright, saturated, slightly stylised lighting. Soft shadows, a little bloom, a clear sky with a strong colour. Slop games look like toy boxes, not films.
- One strong accent light colour per area so areas are remembered.
- Use outlines or highlights sparingly for "this is interactive" and "this is yours"; the engine only draws a limited number at once.
- A low-detail mode that drops bloom, auras on other players and distant effects.

### Rules

- Tint effects from the rarity or theme table rather than making new ones.
- Play effects on each player's own device; the server only says what happened.
- Emit a fixed burst and clean up; never leave emitters running unseen.
- Budget: a tick 3 to 6 particles, a pop under 20, a jackpot under 150, per player.
- Keep particle images small and share them.

## Audio

Sound is half the feel and the cheapest to add. The biggest +1 game advertises its key sounds in its store description.

### The standard sound list

| Sound | Character |
|---|---|
| Core action tick | short, bright, pleasant on the thousandth repeat; the signature sound of the game |
| Coin or cash | light metallic blip; a rapid run when many arrive |
| Button press | soft click or pop, under 0.15 s |
| Window open and close | airy whoosh up, softer whoosh down |
| Purchase success | rising two- or three-note chime with a cash-register feel |
| Cannot afford or error | low, short, dull thud; never harsh |
| Upgrade | rising sweep ending in a sparkle |
| Level up or milestone | short fanfare, 1 s |
| Egg wobble and crack | creaks rising in pitch, then a crunch |
| Reveal stings | one per rarity tier, each fuller and longer than the last |
| Rebirth | deep whoosh, impact, shimmering tail |
| Steal alarm | urgent two-tone siren, only on the victim's and nearby players' devices |
| Hazard warning | siren or horn plus a ticking that quickens |
| Hit or caught | cartoon bonk, splash or boing |
| Footsteps at speed | lighter and faster with speed, with wind rising underneath |
| Notification | gentle bell |
| Countdown | tick, tick, tick, then a higher "go" |

### What makes a sound satisfying

- **Short and clean.** Fast start, no long tail. Most interface sounds are under a quarter of a second.
- **Pitch variation.** Shift each repeat by a random few percent so it never sounds mechanical.
- **Pitch ladders.** In a streak, raise each sound one step (about 6% faster playback per semitone) for eight to twelve steps, then hold; reset after a short pause. A run of pickups becomes a rising scale.
- **Layering by size.** A jackpot is a low impact, a mid chime and a high sparkle together.
- **Reward sounds use pleasant intervals** (major, rising). Errors are low and flat.
- **Sync.** Sound lands on the same frame as the visual hit.
- **Silence before a jackpot.** Duck the music for the wind-up, then bring it back with the sting.

### Music

- One upbeat, loopable track per world, light enough to sit under constant sound effects. Quiet by default (well below the effects).
- A short sting for jackpots that sits over the music.
- Event or hazard music that takes over briefly and returns.
- Music and effects on separate volume sliders, saved.

### Mixing

- Group sounds: music, interface, world effects, other players. Other players' sounds much quieter than your own.
- Limit how many copies of the same sound can play at once so a hundred coins do not become noise.
- World sounds get distance falloff; interface sounds do not.

### Sources and rules

- Roblox's own licensed audio library in the Creator Store is the safest source and already cleared for use.
- CC0 libraries and Freesound (check each licence) for effects; record every file in the game's credits.
- Audio must be owned by or shared with the game to play; test with a second account.
- Generation tools, where available, can make sound effects and music from text. Ask before spending paid credits and keep prompts and results in the credits file.
- No copyrighted songs or sounds ripped from other games.

## Checklist

- [ ] The core action has its own signature sound with pitch variation and a ladder
- [ ] Every rarity tier has a distinct sting and a distinct effect layer
- [ ] Coins have a burst, a flight and an arrival sound
- [ ] Music sits under the effects and ducks for jackpots
- [ ] Other players' effects and sounds are reduced and can be hidden
- [ ] Separate music and effects sliders, saved
- [ ] Low-detail mode holds frame rate on a weak phone
- [ ] Every outside sound and image is in the credits file

Deeper reference: `References/Filhao Roblox Vault/07 VFX/`, `06 SFX and Audio/`, `11 LihFolk V2/07 Lighting VFX and Audio/`. Catalogued sound and animation IDs: `References/Kaffein Dev Vault/01 - Asset Library/` (a listing is not a licence).
