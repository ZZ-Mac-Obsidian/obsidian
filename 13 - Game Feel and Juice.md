# Game Feel and Juice

Why pressing the button feels good. In slop games the core action is tiny (a step, a tap, a grab), so nearly all of the satisfaction comes from how the game answers it. This note sets the answer for every size of event. Motion details are in [[15 - Animation Standard]], effects and sound in [[16 - VFX and Audio Standard]], interface motion in [[14 - UI and HUD Standard]].

All timings are rule-of-thumb starting points. The builder should tune by playing and is free to find something better, as long as the principles hold.

## Principles

1. **Every input gets an answer within one frame.** Play the sound and the motion on the client at once; let the server confirm afterwards. If the server rejects it, correct quietly.
2. **Answer in three channels:** something moves, something sounds, a number changes. On phones add a fourth: a light haptic tick.
3. **Size the answer to the event.** Small for every action, medium for a milestone, huge and rare for a jackpot. If everything shakes the screen, nothing feels special.
4. **Anticipation, then payoff.** A short wind-up before a big result (the egg wobbles, the screen dims, a drum roll) makes the result land harder.
5. **Numbers must be seen to travel.** Coins fly from the world to the counter; the counter bumps when they arrive.
6. **Variation keeps repetition pleasant.** Vary pitch, angle and scale slightly on every repeat.
7. **Rarity is felt before it is read.** Colour, light, sound and duration should tell the player how rare something is before the text does.
8. **Moderate beats extreme.** A study of 3,018 players found moderate feedback beat both none and heavy. Offer a reduced-effects setting.

## The four sizes of feedback

| Size | When | Duration | What plays |
|---|---|---|---|
| Tick | every step, tap, coin, per-second income | under 0.2 s | tiny scale pop, pitch-varied blip, small floating "+N", haptic tick |
| Pop | upgrade bought, item collected, common hatch | 0.3 to 0.6 s | button punch, sparkle burst of 8 to 15 particles, rising chime, counter bump |
| Moment | level up, new area, rare or epic result, rebirth available | 1 to 2 s | banner slides in, light burst, short fanfare, camera nudge, confetti |
| Jackpot | legendary or better, rebirth, world complete, steal succeeded | 2.5 to 4 s, skippable | screen dims, wind-up, flash, big reveal, music sting, field-of-view punch, server-wide announcement |

Only Moment and Jackpot may move the camera. Only Jackpot may dim the screen.

## The core action

Build this first, alone, and do not move on until it is fun in an empty place.

- **The object reacts:** the thing tapped, grabbed or stepped on squashes to about 90% and springs back past 100% before settling (about 0.15 s).
- **The world changes:** a coin leaves, a tile lights, a counter above the head ticks. Something is different after every action.
- **A number flies out:** "+1" or "+$12" in a bold outlined font, rising about a character's head height over 0.6 s while fading, with slight random sideways drift so repeats do not stack.
- **Sound climbs:** each action in a quick run plays slightly higher than the last, resetting after a pause, so a streak sounds like a scale.
- **Critical hits:** roughly 1 in 10 actions is a bigger, brighter, louder version worth more. Cheap variety.
- **Combo meter:** if the genre suits it, a meter that fills with fast actions and pays a small bonus.

## Money and counters

- When cash is collected, 6 to 12 coin icons burst outwards from the source, pause for a beat, then fly to the cash counter along a curve, arriving over about 0.5 s with a rapid run of coin sounds.
- The counter number rolls up to the new total over 0.4 to 0.8 s rather than snapping, and the counter scales to about 115% and back as coins land.
- Income per second is shown as a rate ("$1.2K/s") next to the total. A rate going up is the most satisfying number in an idle game.
- Shorten big numbers consistently: 1.2K, 3.4M, 5.6B, 7.8T, then Qa, Qi, Sx, Sp, Oc, No, Dc. Never show more than four significant digits on the HUD.
- "Cannot afford" is also feedback: the price turns red, the button shakes sideways twice, a dull thud plays.

## Upgrades and purchases

- The upgrade is visible in the world at once: a bigger tool, a new floor, a glow, a trail. Never only a stat.
- The button punches, a ring of particles expands from the upgraded thing, the stat line shows old value → new value with the new one in green, counting up.
- When the next upgrade becomes affordable, its button pulses gently and a small badge appears. The player should never have to open a menu to discover they can buy something.

## Reveals: eggs, rolls, conveyor pulls

The emotional peak of the genre. Structure every reveal the same way and stretch it with rarity.

1. **Commit** (0.1 s): the button punches, the world dims slightly.
2. **Wind-up:** the egg or box wobbles with growing strength, cracks spread, a rising tone plays. Light leaking from the cracks is already the rarity colour, so the player feels it coming.
3. **Burst:** a white flash for two or three frames, particles in the rarity colour, the shell pieces fly off.
4. **Present:** the character scales up from nothing with overshoot, spins once, strikes its idle. Name, rarity banner and "1 in N" appear.
5. **Settle:** it hops to its slot or into the inventory icon, which bumps.

| Rarity | Wind-up | Extras |
|---|---|---|
| Common | 0.3 s | plain pop |
| Uncommon, Rare | 0.6 s | coloured burst, chime |
| Epic | 1.0 s | light rays, bigger sting, camera nudge |
| Legendary | 1.8 s | screen dim, beams, music sting, confetti, server chat line |
| Mythic, Secret | 2.5 s or more | full-screen colour wash, slow motion, unique sound, global announcement |

Rules: tap to skip always; a "fast hatch" toggle after the first few; multi-hatch shows results side by side and lingers only on the best one. Show the true result. A reveal that pretends to almost land on a better prize is a near-miss trick and is out.

## Rebirth

The biggest moment in the game, because the player is giving something up. Make the gain feel larger than the loss.

- A confirmation that shows exactly what resets and what is gained, with the new multiplier large.
- Then: a shockwave ring from the player, the world flashing white, numbers visibly spinning down to zero, a new badge slamming onto the overhead tag, and the first income tick arriving at the new, faster rate within two seconds.
- The base or character changes permanently: a new colour, a crown, a floor.

## Loss and danger

- **Telegraph first.** A hazard gets a countdown, a siren and a screen-edge flash. A thief triggers an alarm and an arrow on the owner's screen.
- **Make it readable and slightly funny:** ragdoll, a cartoon splash, the dropped item bouncing. Loss that looks funny gets clipped and shared.
- **Never stack punishment with a sales prompt.** No offers after a loss.
- **Show the way back at once:** "Chase them!" with a beam, or the respawn already facing the track.

## Tension tools

- Speed lines, wider field of view and rising wind as the player gets faster.
- A heartbeat or ticking that quickens as a hazard nears.
- A slow-motion beat (about 0.3 s) on a last-moment escape or a successful steal.

## Budget on phones

Most players are on phones, many low-end.

- Cap particles: a tick emits 3 to 6, a jackpot under 150 total.
- Other players' effects are drawn smaller or not at all beyond a short distance; include a "hide others' effects" setting.
- Reuse a pool of floating-number labels instead of creating new ones.
- Avoid stacks of see-through layers.
- Reduced-effects setting: no shake, no flashes, shorter reveals.

## Feel checklist

- [ ] The core action is fun for two minutes with nothing else in the game
- [ ] Every action answers in motion, sound and a number
- [ ] Four clearly different sizes of feedback exist and the biggest is rare
- [ ] Coins travel to the counter and the counter reacts
- [ ] Rarity is obvious with the sound off, and with the screen covered
- [ ] Every reveal can be skipped
- [ ] The first affordable upgrade announces itself
- [ ] Loss is telegraphed, readable and followed by a way back
- [ ] Runs smoothly on a low-end phone with a full server

Deeper reference: `References/Filhao Roblox Vault/11 LihFolk V2/47 Game Feel and Juice/` and `06 SFX and Audio/What Makes a Sound Satisfying`.
