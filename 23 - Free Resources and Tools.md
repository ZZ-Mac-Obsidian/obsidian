# Free Resources and Tools

Where to get models, textures, sounds, animations, fonts, code and learning material without paying, which tool to use for each job, and the licence rules that keep a published game safe. Researched 11 Nov 2026; tool pricing and licence terms change, so confirm on each site before relying on them.

Tags: (official) the provider's own statement, (third-party) reviews and guides, (rule of thumb) my recommendation.

## The short answer on 3D modelling

**Blender is still the right main tool,** and it is free. But for slop-genre games it is not the first thing to reach for on every asset. Use the cheapest route that reaches the quality bar:

| Route | Best for | Speed | Quality control |
|---|---|---|---|
| 1. Existing free asset (Creator Store, CC0 packs) | generic props, nature, buildings, fences, coins | minutes | low: it looks like everyone else's |
| 2. Roblox parts and Studio's own tools | blockouts, simple bases, pads, signs, conveyors | minutes | high for simple shapes |
| 3. AI generation, then clean-up in Blender | meme characters, one-off props, many variants fast | tens of minutes | medium: needs decimating and fixing |
| 4. Blender by hand or by script | hero characters, the base kit, anything that must be exactly right or animate well | hours | highest |
| 5. Blockbench | deliberately blocky or pixel-style characters | fast | high within that style |

A sensible split for one game: routes 1 and 2 for the world, route 3 for most collectible characters, route 4 for the five things that appear in the thumbnail.

The step-by-step pipeline, house style and import checks are in [[04 - Blender Pipeline]].

## Tools

### Modelling

- **Blender** (free, open source). The standard. Everything else on this list ends up passing through it for clean-up and export.
- **Blender driven by an AI builder.** Blender can be controlled through its scripting interface, and since April 2026 there is an official Claude connector for Blender alongside the community `blender-mcp` project (third-party reports). The builder can create and edit geometry by script, pull assets from Poly Haven, and render previews. Best at blocky, geometric, low-poly shapes and at batch jobs (decimate, apply transforms, rename, export fifty files). Weak at organic sculpting; pair it with generation for those.
- **Blockbench** (free, open source). Purpose-built for low-poly, boxy, pixel-textured models. Very quick for blocky creatures; exports to formats Blender reads.
- **Roblox Studio itself.** Parts, unions and the built-in material generator cover more than expected for bases and props. Studio's Assistant and generation tools can produce meshes and textures from a text prompt (see below).

### AI 3D generation

Useful for the genre because meme characters are forgiving: odd proportions are part of the joke.

| Tool | Free allowance (third-party, changes often) | Note |
|---|---|---|
| Roblox's own generation in Studio (Cube) | included in Studio | output lands directly in the game; simplest licence position; quality basic. API and availability have changed since the 2025 beta, so read the current docs |
| Hunyuan3D | about 20 generations a day on its site; open source and free without limits on your own NVIDIA GPU | most generous free option; confirm commercial terms |
| TRELLIS | open source, free on your own GPU | same |
| Tripo | 200 to 300 credits a month | good game-style topology; sources disagree on whether free output is non-commercial or CC BY, so check before use |
| Meshy | about 100 credits a month, roughly 3 textured models | free output may be public; check licence |

How to use them well (rule of thumb):

1. **Generate an image first, then image-to-3D.** A clean front-view concept on a plain background, in the game's style, gives far better and more consistent results than text-to-3D. It also lets all characters share one look.
2. **Always clean up in Blender:** decimate hard (these tools output hundreds of thousands of triangles; a collectible should be a few thousand), fix scale and origin, merge to one material, check normals.
3. **Expect to regenerate.** Budget three tries per character and keep the best.
4. **Check the licence of the free tier before publishing.** Several free tiers make output public or non-commercial. If in doubt, use Roblox's own generator, an open-source model run locally, or a paid month.
5. Record the tool, prompt and date in the game's credits file.

### Textures and materials

- For the house style (one shared palette texture, flat colours) no texture source is needed.
- **Poly Haven** and **ambientCG**: CC0 materials and sky images when a surface needs real texture.
- **Roblox's material generator** in Studio for quick tileable surfaces.

### Rigging and animation

- **Roblox's animation editor** (in Studio, free): the reliable path for avatar and simple rigs.
- **Blender** for bespoke rigs and animation.
- **Mixamo** (free with an Adobe account): auto-rigging and a large motion library for humanoid characters. Check Adobe's terms for game use, and note it suits human-shaped rigs only.
- **Quaternius's universal animation library** (CC0) for a shared humanoid set.
- **Moon Animator** (Studio plugin, paid tiers) is popular for cutscenes; not needed for this genre.
- Many slop characters need no rig at all: see the procedural motion list in [[15 - Animation Standard]].

### Images: icons, thumbnails, interface art

- **Staged in Studio or rendered in Blender** from the game's own models: free and guaranteed to match the game.
- **Photopea** (free, in the browser) or **GIMP** / **Krita** (free) for compositing, outlines and text.
- **Figma** (free tier) for laying out interface screens before building them.
- Image generators for backgrounds, bursts and concept exploration. Free tiers vary; check commercial terms.
- **Kenney's interface packs** and **game-icons.net** (CC BY, credit required) for icon starting points.

### Sound and music

- **Roblox Creator Store audio:** Roblox's licensed library, already cleared for use in games. First choice.
- **Kenney audio packs** (CC0): interface clicks, impacts, jingles.
- **Freesound:** huge, mixed licences. Filter for CC0; CC BY needs credit; avoid non-commercial.
- **Pixabay sound effects and music:** free under its own licence; read it.
- **sfxr-style generators** (jsfxr, ChipTone; free): make retro blips, coins and power-ups in seconds. Excellent for the core-action tick.
- **Audacity** (free) for trimming, pitching and layering.

### Code and engineering

- **Rojo, Wally, Selene, StyLua, Luau language server** (all free, open source): see [[11 - Tech Stack Standard]].
- **ProfileStore** for saving; **TopbarPlus** for top-bar buttons; a promise library and a cleanup library.
- **Roblox's official Studio MCP server** lets an AI builder read and edit the place, run code, play-test and capture the screen.
- **Agent skill packs** for Luau (for example `roblox-brain`, `luau-skills`) and knowledge servers (for example `roblox-logics-mcp`, Brickwise) found on GitHub: third-party, unreviewed; read before installing.

## Asset libraries

### 3D models

| Source | Licence | Style and use |
|---|---|---|
| **Roblox Creator Store** | Roblox's terms; free models usable in Roblox games | already in the right format; quality varies wildly; inspect for hidden scripts before use |
| **Kenney** (kenney.nl) | CC0 | 40,000+ assets in one consistent low-poly style; the best match for the house style |
| **Quaternius** | CC0 | cute stylised low-poly packs: characters, animals, nature, with animations |
| **Poly Pizza** | mostly CC BY, some CC0 | large searchable low-poly library; check each model and credit where required |
| **Poly Haven** | CC0 | realistic models, textures, skies; more detail than this genre needs |
| **Sketchfab** | per model | filter by downloadable and CC0 or CC BY; check every one |
| **OpenGameArt** | per asset | mixed quality and licences |
| **itch.io asset packs** | per pack | many free low-poly packs; read each licence |

Free models from the Creator Store are the fastest and the riskiest: they can contain scripts that do unwanted things, and popular ones make a game look like a clone. Open every one, delete all scripts inside it, and prefer mesh-only assets.

### A good starter shelf

Download once and keep in a shared folder: Kenney's nature, city, food and interface packs; Quaternius's animals and ultimate packs; a Poly Haven sky or two; Kenney's interface and impact sounds.

## Licences in one table

| Licence | Can use in a published, earning game | Must do |
|---|---|---|
| CC0 / public domain | yes | nothing (credit is polite) |
| CC BY | yes | credit the author as they ask |
| CC BY-SA | yes, with care | credit; derived assets carry the same licence |
| CC BY-NC, "personal use", "non-commercial" | **no** | do not use |
| Roblox Creator Store free assets | yes, inside Roblox | follow Roblox's terms |
| "Royalty-free" from a marketplace | usually | read that marketplace's terms |
| AI tool free tier | depends on the tool | read the current terms; many free tiers restrict commercial use |
| Ripped from another game, show or brand | **never** | |

Rules for the builder:

- Every outside asset goes in the game's `credits.md` with source link, author, licence and date, at the moment it is added.
- When a licence is unclear, do not use the asset.
- Recognisable characters, logos and music from other games, shows or brands are off limits whatever the download site says.
- A listing in the reference vaults' asset catalogues is not a licence.

## Learning and reference

- **Roblox Creator Docs** (create.roblox.com/docs): the authority on engine features and policy. Look things up here before trusting memory or a blog.
- **Roblox DevForum:** announcements and staff posts are reliable; community threads are opinions.
- **Roblox's own YouTube channel and "Learn" tutorials** for Studio workflows.
- **Blender Guru's beginner series**, and **Grant Abbitt's low-poly tutorials**, are the standard free starting points for the house style.
- **Trackers for market research:** Rolimons, RoMonitor-style sites, RoTrends, and the Charts page on Roblox itself.
- **The two downloaded vaults** in [[10 - Reference Vaults]] for teardowns, systems and modelling notes.

## Picking a route for a given asset

1. Is it generic and background? Take it from a CC0 pack or build it from parts.
2. Is it a collectible character? Concept image → image-to-3D → Blender clean-up → shared palette → procedural motion.
3. Is it in the thumbnail, or does it need real animation? Model it properly in Blender.
4. Is it a sound? Roblox library first, then a generator for the signature tick, then CC0 packs.
5. Is it interface art? Build from components and a theme; generate or draw only the icon set.

Then check it in the game, next to a character, on a phone-sized screen. The game is the only judge that counts.
