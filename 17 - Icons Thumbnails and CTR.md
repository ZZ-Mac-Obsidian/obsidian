# Icons, Thumbnails and CTR

The tile is the advert. Over 90% of play starts from the Home page, and the first thing Roblox measures about a game is how many people who see its tile go on to play. This note is how to win that click honestly, because a click that bounces in the first minute now counts against the game.

Tags: (official) Roblox docs read 11 Nov 2026, (third-party) blogs and trackers, (rule of thumb) design guidance to test.

## How the click is counted

- **Play-through rate** is "the rate at which users play your game after seeing it" in Recommended For You. It is one of the four most important ranking signals (official).
- **First-play bounce** (leaving in under 60 seconds, and in 61 to 180 seconds) is a negative signal measured on the same first session (official). A thumbnail that over-promises raises the first number and wrecks the second.
- Roblox says its move to a 28-day view was aimed at games "that win attention with exciting thumbnails but don't deliver long-term value" (official).
- Thumbnail personalisation reports a *qualified* play-through rate: only plays where the user stays for a meaningful time (official).
- **So the goal is not the most clicks. It is the most clicks from people who then stay.** Show the real game at its most exciting moment.

## Specs and rules (official)

| Asset | Spec |
|---|---|
| Icon | square, at least 512 by 512; shown as small as 150 by 150. One per language. |
| Thumbnail | 16:9, ideally 1920 by 1080; jpg, png, gif, tga or bmp. Other shapes get stretched. |
| How many | up to 10 images or videos on the game page |
| Personalisation | turn on 2 to 5 thumbnails; keep each under 3 MB |
| Video | free, 3 uploads a month (rejections count); reviewed before showing; can appear on Home |

- **A custom thumbnail is required** to receive Home recommendations at all. A default one makes the game ineligible.
- **Bottom edge:** keep essential elements out of the bottom of the thumbnail; the player count and other labels can cover it.
- **Must match the game.** A game whose thumbnail shows one thing and whose gameplay is another is not recommended and drops in search.
- **Must be the game's own.** Titles and images that repeat previously published ones, or listings that closely resemble existing games, lose priority.
- **Video rules:** real gameplay only. No real-life footage, no spoken audio (voice-over, narration or lyrics), no claims or adverts such as "50% off" or "Free UGC". In-game interface text and catalogue music are fine. Overlay text sparingly. Video thumbnails do not play on consoles or VR.
- **Titles** that lead with money or giveaways ("Robux! Play now!") get less exposure. Do not put irrelevant keywords in the title or description.
- Everything is moderated against Roblox's community rules.

## The icon

It is seen at the size of a thumbnail. Design it at 512, judge it at 150.

- **One subject filling 60 to 80% of the square.** The game's star character or the core object, never a scene.
- **A face with a big emotion** if there is a character: shock, glee, greed. Eyes large, looking at the viewer or at the object.
- **Thick outline and a rim of light** so it separates from any background.
- **A simple two-tone background:** a radial burst or gradient in a colour that contrasts with the subject. Blue and orange, purple and yellow, green and pink.
- **Almost no text.** At most one huge element that is part of the genre language: "+1", "x2", "$", an arrow going up. One creator's click rate improved when icon text was removed (creator claim).
- **Recognisable as yours.** After a week on the charts, players find the game by the icon's colour and silhouette. Keep those when refreshing for an update.
- **Update dress:** a small corner badge or a seasonal recolour for an event, same silhouette.

## The thumbnail

It has one second. In that second the eye finds the brightest, most contrasted shape, reads its emotion or action, and guesses what kind of game it is.

**Composition**

- **One hero** covering roughly 30 to 45% of the frame, placed on a left or right third, upper half. Under 20% it is a detail; over 60% the context that explains the game is lost.
- **One supporting element** that completes the sentence: the hero and the thing they want, or the hero and the thing chasing them.
- **The hero looks or moves into the frame**, towards the second element.
- **Separation in this order:** brightness first, then colour, then a rim light. Check it in greyscale: if the hero does not stand out in grey, it will not stand out in colour.
- **Depth:** a blurred or simpler background, a strong foreground. No wide establishing shots of the map.
- **Keep the bottom strip and the corners empty** of anything important.

**Content: show the verb and the twist**

| Genre | Frame that works |
|---|---|
| Steal a ... | a thief mid-sprint clutching a glowing rare character, the furious owner or a slamming gate behind |
| Hazard run | a runner carrying a character with a towering wave right behind |
| +1 stat | the same avatar small on the left and huge or blazing fast on the right, an arrow between, the stat number big |
| Roll or hatch | an egg cracking with light pouring out in a legendary colour, a "1 in 1,000,000" tag |
| Tapper | a giant object being hit with numbers exploding off it |
| Grow | a tiny seed on one side, an absurdly huge result on the other |

- **Before and after** is the strongest structure for progression games: weak on the left, absurdly powerful on the right.
- **Numbers that pull:** income as a rate ("$1M/s"), odds as a denominator ("1 in 1M"), a multiplier ("x100"). Use numbers a player can really reach.
- **Text:** zero to three words, huge, outlined, in the upper two-thirds. The image should work without it.
- **Emotion over accuracy of pose.** Exaggerate the expression and the stretch of the run. Do not exaggerate what the game contains.

**The set of thumbnails**

Upload three to five that each sell a different promise, and let personalisation show each player the one that works on them. In testing, games using it averaged +8.5% qualified play-through, some +50% (official). Keep several active rather than picking one winner.

1. The core verb and twist.
2. The rarest collectible, as a "you could own this" shot.
3. The power fantasy: late-game base, top speed, biggest number.
4. The social moment: friends, a chase, a crowded server.
5. The current update or event.

## Making them

- **Stage it in the game.** Pose real models in a small studio scene: strong key light from one side, coloured rim light from behind, plain or blurred backdrop, camera low and close with a narrow field of view for drama. This guarantees the thumbnail matches the game.
- **Or render in Blender** with the same models for better lighting, depth of field and outlines.
- **Image generation** is fine for backgrounds, bursts and polish, and for exploring compositions quickly. The characters and objects shown must be the ones in the game. Ask before spending paid credits.
- **Finish:** push contrast and saturation, add the outline and rim, add glow to the rare thing, add the one number or word.
- **Judge at real size:** shrink to 150 pixels wide next to four real competitors' tiles. If it does not win the eye, redo it.

## The video

- 15 to 30 seconds, silent-friendly, catalogue music only.
- First two seconds: the core verb with its feedback. No logo, no build-up.
- Then one beat each for: the twist, a rare reveal, the power fantasy, other players.
- Fast cuts, each shot one idea. End on the most impressive image.
- Record clean footage: hide other interface clutter, use a free camera, 60 frames a second, a full and lively server.
- Games with video on Home saw up to 39% more playtime from Home in Roblox's tests (official, from the earlier vault research).

## Title and description

Full naming research and method: [[24 - Names and Titles]].

- **Title:** the verb and the noun. "Steal a ...", "+1 ... Every Step", "Escape ... for ...". Under about 30 characters before any tag so it is not cut off on the tile.
- **Tags in brackets** for freshness: "[UPD]", the update name, a season. Change them when the update lands, not daily.
- **Emoji** at the start is common in the genre; one or two that match the theme.
- **Description:** line one says what you do in a sentence. Then three to five short lines of how to play as verbs. Then the latest update. Then group and code information. Natural keywords only.
- **Never:** another game's name, promises of free Robux, unrelated keywords.

## Testing and reading results

- Thumbnails: Creator Hub shows impressions and qualified play-through per thumbnail. Give each at least a few thousand impressions before judging. Replace the loser with a new idea, not a variation.
- Icons have no built-in test. Change one thing, hold it a full week (to cover the weekend peak), compare play-through for the same weekdays.
- Read play-through together with the under-60-second bounce. Up and up means the thumbnail is over-promising.
- Change one thing at a time, and never the same week as a big game update.

**Benchmarks (third-party and creator claims, treat as rough):** sponsored tiles click at about 1 to 2%; organic Home play-through for a healthy game is several percent. Compare against the benchmark Roblox shows in its own analytics for similar games rather than outside numbers.

## Review checklist

Score each thumbnail before upload. Anything missed goes back.

- [ ] One hero, readable at 150 pixels wide
- [ ] The verb and the twist are both visible
- [ ] Passes the greyscale test
- [ ] Face or focal point on a third, looking into the frame
- [ ] Nothing important in the bottom strip
- [ ] Zero to three words of text
- [ ] Everything shown exists in the game and is reachable
- [ ] Looks different from the top five games in the genre
- [ ] Wins the eye in a row of real competitor tiles
- [ ] Three to five different promises uploaded, personalisation on

Deeper reference: `References/Filhao Roblox Vault/11 LihFolk V2/61 Thumbnails and CTR/` (eight notes including a scoring rubric), `27 Marketing and Growth/Game Icon Design - Readable at Small Sizes`, and `09 Visual References/Roblox Game Thumbnail Board`. Sources in [[08 - Sources and Unknowns]].
