# 3D Models and Blender Pipeline

How every model gets made, from a collectible meme character to the base it stands on. Which tool to use for which asset, and the free sources, are in [[23 - Free Resources and Tools]]. How models move is in [[15 - Animation Standard]]; their effects in [[16 - VFX and Audio Standard]].

Check Roblox's current import limits on create.roblox.com before the first export of each project. Sources disagree on the per-mesh triangle cap (older guides say 10,000, recent ones about 20,000), so stay well under either.

## House style

- **Stylised, chunky, rounded, toy-like.** Slightly oversized heads, hands and details so they read on a phone.
- **Big readable silhouette.** Every character should be recognisable as a black shape at thumbnail size. Two characters must never share a silhouette.
- **Flat colours from one shared palette texture per game** (a small grid of colour squares). Every model maps its faces onto that grid: one material, few draw calls, and the whole game matches. A new game is a new palette.
- **Faces sell characters.** Big eyes, simple mouth, one clear expression. Painted or simple geometry, not detail.
- **No parts thinner than a character's hand.** Thin parts flicker at distance and break at speed.
- The style is a floor, not a cage. Each game should push one thing of its own: a material (jelly, chrome, plush), a shape language (all cubes, all blobs), or a lighting mood.

## Budgets

| Asset | Triangles | Notes |
|---|---|---|
| Collectible character, common | 500 to 1,500 | dozens on screen at once |
| Collectible character, top rarity | 1,500 to 4,000 | extra detail comes from effects, not polygons |
| Small prop | under 500 | |
| Large prop or machine | under 3,000 | |
| Base or building piece | under 5,000 | modular pieces reused |
| Texture | one 256 or 512 palette per game | larger only for a hero asset |

A server of 8 bases with 20 characters each is 160 characters before pets and players. Keep them light and let effects and animation carry rarity.

## What to make, in order

1. **The hero five:** the characters and object that will be in the thumbnail. Best quality in the game.
2. **The base kit:** plot floor, slot pedestal, walls, gate or lock, upgrade pads, income sign.
3. **The hub kit:** conveyor or hatchery, shop stall, rebirth altar, leaderboard board, spawn.
4. **The collectible set:** 30 to 40 characters across rarities. Batch these.
5. **World dressing:** ground, sky, fences, trees, signs. Mostly from CC0 packs.
6. **Per-update sets:** 3 to 5 characters and one world piece a week.

Take one character through the entire pipeline into the running game before batching the rest.

## Characters at volume

The genre needs many characters cheaply. A repeatable recipe:

1. **Name and idea first** from the recipe in [[20 - Slop Game Blueprints]]: two unrelated things fused, a sing-song name, one exaggerated feature.
2. **Concept image:** front three-quarter view, plain background, the game's palette. All characters drawn in one consistent style.
3. **Model** by the cheapest route that meets the bar: image-to-3D generation then clean-up, or build from primitives in Blender (many meme characters are a few spheres and cylinders plus a face).
4. **Clean up in Blender** (steps below).
5. **Rarity dressing in Studio,** not in the mesh: aura, glow, trail, size. One mesh can serve several rarities and all mutations.
6. **Motion:** procedural bob and squash by default; a shared simple rig for the ones that need limbs to move.

Give the builder room here. Character design is where the game gets its personality, and odd, funny, slightly wrong proportions are an asset.

## Blender steps

1. **Scale.** Set units so 1 Blender unit is 1 stud. Keep a character-sized box (about 5 studs tall) in the scene for comparison.
2. **Block out** rough shapes at true size.
3. **Model.** Bevel large edges once for the rounded look. For generated meshes: decimate to budget, then fix what the decimation broke.
4. **Split what moves.** Anything that spins, slides or opens is its own object with its origin at the pivot.
5. **Split what is acted on.** Each part the player acts on separately is its own object, named for what and where it is.
6. **UV to the palette.** Scale each face island into the colour square it needs.
7. **Clean up.** Apply scale and rotation, recalculate normals outward, merge doubles, delete faces nobody will see (undersides, insides).
8. **Origins.** Base centre for props and characters; pivot for moving parts.
9. **Collision plan.** A simple box or hull per object, set in Studio. Never the detailed mesh.
10. **Export FBX,** selected objects only, transforms applied, one file per asset or per kit.
11. **Import to Studio,** check size against a character, set collision, anchor, group as a model, tag for scripts, set its pivot.

When Blender is driven by the AI builder, do steps 6 to 10 as one script run over a whole batch, and render a preview image of each asset to check by eye before import.

## Folder layout per game

```
Games/<Game Name>/
  blend/      source .blend files, one per asset group
  export/     .fbx files ready for Studio
  textures/   palette and any image textures
  refs/       concept and reference images
  credits.md  every outside asset and generation: source, licence, date
```

## Rigged characters

- Model in a T or A pose with simple separate limbs.
- One shared small skeleton (root, body, head, two arms, two legs, optional tail and ears) with clear bone names, so one animation set fits every character.
- Standard set: idle, walk, carried, celebrate.
- If Blender animation import misbehaves, animate in Roblox's own editor.
- Upload animations under the group that owns the game or they will not play.

## Standard kit to build once and reuse

- Base plot, slot pedestal, gate and lock, upgrade pad, income sign, conveyor segment, egg and hatch stand, shop stall, rebirth altar, leaderboard board, interaction ring, signposts, fence, lamp.
- Re-skin per game by swapping the palette and a few signature shapes. Change enough that the place file is not a near-copy of the last game.

## In Studio

- Anchor everything that does not move.
- Simplest collision that works; none on decoration.
- Streaming on; far zones use simpler versions.
- Group by purpose and name clearly so scripts and the builder can find things.
- Lighting and sky set per game: see the world section of note 16.

## Checks before a model is done

- [ ] Recognisable as a silhouette at thumbnail size
- [ ] Looks right next to a Roblox character in Studio
- [ ] Inside the triangle budget
- [ ] One material, palette texture only
- [ ] Origin and pivot correct; moving parts pivot properly
- [ ] Simple collision set
- [ ] Named, grouped and tagged
- [ ] Source saved; listed in credits if anything came from outside
- [ ] Still reads on a phone-sized screen at normal play distance

Deeper reference: `References/Filhao Roblox Vault/03 3D Assets and Models/`, `11 LihFolk V2/14 3D Modeling/`, `45 Procedural Blender Assets/`, `54 Untextured Stylised Modelling/`, `55 Modelling Nuance and Readability/`, `18 Rigs and Skeletons/`.
