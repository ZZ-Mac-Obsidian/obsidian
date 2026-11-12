# Animation Standard

How things move: players, characters and pets, world objects, the camera. Interface motion is in [[14 - UI and HUD Standard]]; the reasons behind it are in [[13 - Game Feel and Juice]]. Timings are starting points to tune by eye.

## The house style

Snappy, bouncy and slightly exaggerated, like a toy. Fast into the pose, a soft settle out of it. Nothing drifts or eases slowly unless it is meant to feel heavy or dramatic.

**Six principles to apply everywhere**

1. **Squash and stretch.** Things compress on impact and stretch when moving fast. Keep volume: wider means shorter.
2. **Anticipation.** A small move the opposite way before the main move (crouch before jump, pull back before throw).
3. **Overshoot and settle.** Go slightly past the target, then come back. This single habit makes motion feel alive.
4. **Offset timing.** Parts of a body arrive at slightly different times: ears, tails and antennae lag behind.
5. **Arcs.** Things travel on curves, not straight lines.
6. **Hold the pose.** After a big move, hold for a beat so it reads.

## Player character

Most games keep the default Roblox avatar animations and add a few custom ones for the core action.

| Animation | Notes | Length |
|---|---|---|
| Core action (tap, swing, grab, throw) | strong anticipation and follow-through; must loop cleanly when held | 0.25 to 0.5 s |
| Carry | arms up holding the item overhead or hugged; walk and run variants or an upper-body layer | loop |
| Victory | jump, fist pump or spin on a win or rare result | 1 to 1.5 s |
| Hit or caught | flinch into ragdoll or a comic tumble | 0.5 to 1 s |
| Sit, ride or mount | if the game has mounts or seats | loop |

- Use upper-body-only animations for actions so the legs keep walking.
- Set priorities so actions override movement and movement overrides idle.
- At high speed in a +1 game, lean the body forward, lengthen the stride and add a trail.

## Collectible characters and pets

These are the stars. A character that only slides around looks cheap; one with a personality idle sells the whole game.

**Minimum set per character**

| Animation | Notes |
|---|---|
| Idle | breathing bob plus one personality tic every few seconds (blink, wiggle, look around). Rarer characters get fancier idles. |
| Walk or hop | used on the conveyor, when following, when being placed |
| Spawn | scale up from nothing with overshoot and a little jump |
| Earn tick | a tiny bounce or nod when it pays out, in time with the money number |
| Carried | dangling, flailing or frozen stiff while a player holds it; funny helps |
| Celebrate | on rarity reveal and when upgraded |

**Ways to get there, cheapest first**

1. **Procedural motion in code**, no rig needed: bob up and down on a sine wave, squash and stretch with scale, lean into turns, hop along a path, spin slowly on a pedestal. For simple meme characters this is often enough and costs nothing per character.
2. **A shared simple rig** (root, body, head, two arms, two legs, optional tail and ears) used by every character, so one set of animations fits all of them.
3. **Bespoke animation** for the top rarities only.

Following pets: float or hop behind the player in a loose formation, each with a slightly different bob phase so they do not move in unison. Ease towards the target position instead of snapping.

## World objects

| Object | Motion |
|---|---|
| Coins and pickups | slow spin and bob; when collected, shrink towards the player and vanish with a pop |
| Buttons and pads on the ground | sink when stepped on, spring back, flash |
| Conveyor | scrolling surface texture; items ride at belt speed with a small wobble |
| Eggs and boxes | idle wobble every few seconds so they ask to be opened |
| Doors and gates | slide or swing with overshoot and a dust puff; never just disappear |
| Base lock or shield | slam shut with a shake and a flash; a visible timer ring |
| Machines | pistons, spinning parts, puffs of smoke, speeding up with upgrade level |
| Hazard (wave, lava, monster) | a readable leading edge, a warning phase, a consistent speed |
| Upgraded things | grow into the new size with overshoot rather than swapping instantly |
| Signs and price tags | gentle sway or bob so the world never feels frozen |

Animate world objects on each player's own device from a shared clock, so the server stays light and everyone sees the same thing.

## Camera

- **Default:** standard third-person follow. Do not fight the player's control.
- **Field-of-view punch** on a Jackpot: widen by about 8 degrees over 0.1 s, return over 0.4 s.
- **Speed feel:** widen the field of view gradually with speed, up to about 15 degrees.
- **Shake:** short and small, only for Moment and Jackpot events, never on ordinary actions, off in the reduced-effects setting.
- **Reveal framing:** for hatches and rolls, bring the result in front of the camera rather than moving the camera away from the player's world.
- **Rebirth or world unlock:** a two to three second move to show the new thing, skippable, control returned promptly.

## The reveal sequence

The most-watched animation in the game. Structure and rarity lengths are in [[13 - Game Feel and Juice]]; the motion beats are:

1. Egg drops in with a bounce and settles.
2. Wobbles left and right, each wobble larger and faster, cracks appearing.
3. A held beat of stillness just before the burst (the longer the rarer).
4. Shell pieces fly outwards and fade; a flash covers the swap.
5. The character scales up with overshoot, turns once, plays its celebrate.
6. Name and rarity banner slam in; the character hops away to its slot.

## Easing guide

| Feel wanted | Use |
|---|---|
| Pop in, bouncy arrival | overshoot ("back") ease out |
| Wobbly, springy settle | elastic ease out, used sparingly |
| Quick, clean interface moves | quad or quint ease out |
| Disappearing | quad ease in, fast |
| Floating, bobbing | sine, looping |
| Landing or dropping | bounce ease out |
| Constant motion (conveyors, spins) | linear |

## Making and importing

- **Roblox's own animation editor** is the reliable path for avatar and simple-rig animations.
- **Blender** for bespoke character animation, exported with the rig; test one character end to end before making a batch. See [[04 - Blender Pipeline]].
- **Generation tools**, where available, can rig and animate a model or produce an animation from a text prompt. Treat results as a first pass and check them in the game.
- **Free library animations** from the Creator Store are fine for avatar actions; check licence and credit them.
- **Ownership catch:** an uploaded animation only plays in games owned by the same account or group that uploaded it. Upload under the group that owns the game.
- Preload animations and sounds for the first minute so nothing pops in late.

## Checklist

- [ ] The core action animation loops cleanly and has anticipation and follow-through
- [ ] Every collectible character has at least an idle, a spawn and an earn tick
- [ ] Rarer characters move more and better than common ones
- [ ] Nothing in the world appears or disappears without a transition
- [ ] Pets follow with easing and offset bobbing
- [ ] Camera effects are reserved for big moments and can be reduced
- [ ] The reveal sequence has a clear wind-up, a held beat and a burst
- [ ] Animations are uploaded under the game's owner

Deeper reference: `References/Filhao Roblox Vault/05 Animation and Cutscenes/`, `11 LihFolk V2/08 Animation/` (130 notes), `18 Rigs and Skeletons/`.
