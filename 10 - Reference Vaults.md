# Reference Vaults

Two public Obsidian vaults are downloaded into `References/` as lookup libraries. The numbered notes at the top level remain the standard; these are for depth.

**Treat both as unverified.** Much of their content is AI-generated and marked "draft", "design only" or "untested" by their own authors. Check anything important against Roblox's documentation. Their agent-instruction files were renamed so they are not followed as instructions.

## Kaffein Dev Vault

`References/Kaffein Dev Vault/` (637 files, CC0 licence, by kaffeindecaf). Built for AI-agent Roblox development. Strongest on reusable systems and project workflow; its game-design content is horror-focused.

Most useful for the factory:

| Need | Where |
|---|---|
| Objective line and tracker | `03 - Reusable Systems/S-objective-tracker` |
| Daily return system | `03 - Reusable Systems/S-daily-retention-engine` |
| Session reward grid | `03 - Reusable Systems/S-session-reward-grid` |
| Drop point and deposit | `03 - Reusable Systems/S-plot-resource-deposit` |
| Purchases handled safely | `03 - Reusable Systems/S-purchase-fulfillment-center`, `S-receipt-fulfillment-contract` |
| Shop layout | `03 - Reusable Systems/S-ui-shop-catalog-layout` |
| Player data saving | `03 - Reusable Systems/S-datastore-player-profile`, `S-save-load-migration` |
| Area gates | `03 - Reusable Systems/S-sequential-area-gates` |
| Friends joining midway | `03 - Reusable Systems/S-late-join-sync` |
| Server authority, remotes | `02 - Roblox Development/` |
| Code snippets | `11 - Templates and Schemas/Luau Snippets/` (49 files) |
| Per-game project folder | `10 - Projects and Experiments/_PROJECT_TEMPLATE/` (handoff, timeline, test plan) |
| Catalogued sounds, animations, models | `01 - Asset Library/` (a listing is not a licence) |
| Bugs already solved | `08 - Bugs and Solutions/` |

Idea worth adopting: one shared library for reusable knowledge, and one folder per game holding only that game's decisions, state and evidence.

## Filhao Roblox Vault

`References/Filhao Roblox Vault/` (1,571 files, 99 MB, MIT licence, by Filhao2019). Combines several other vaults. Strongest on breakdowns of top games, UI, and modelling.

Most useful for the factory:

| Need | Where |
|---|---|
| Teardowns of 28 top games | `01 Games/` (Steal An Egg, Grow a Garden, Throw Food For Animals...) |
| The steal-and-collect formula | `02 Game Design/Steal and Collect Tycoon Formula` |
| Pre-launch checklist | `02 Game Design/What Every Roblox Game Needs` |
| First session | `02 Game Design/Onboarding and First Session` |
| Thumbnails, icons, titles | `02 Game Design/Thumbnails Icons and Titles`, `11 LihFolk V2/61 Thumbnails and CTR/` |
| Shop and HUD design | `04 UI and GUI/Shop and Monetization UI`, `HUD and Currency Displays` |
| Screenshot boards of real game UI | `09 Visual References/` |
| Modelling for Roblox | `03 3D Assets and Models/Modeling for Roblox`, `Performance Budgets and Optimization` |
| Blender workflow | `11 LihFolk V2/14 3D Modeling/Blender Workflow for Roblox Creators`, `45 Procedural Blender Assets/`, `54 Untextured Stylised Modelling/` |
| Rigs | `11 LihFolk V2/18 Rigs and Skeletons/` |
| Satisfying sound | `06 SFX and Audio/What Makes a Sound Satisfying` |
| Reward effects | `07 VFX/Reward and Rarity VFX`, `11 LihFolk V2/47 Game Feel and Juice/` |
| Open-source libraries | `08 Coding/Open Source Libraries` |
| Viral game teardowns | `11 LihFolk V2/59 Viral and Trend Game Teardowns/` |
| Marketing and live operations | `11 LihFolk V2/27 Marketing and Growth/`, `38 Live Ops Deep Dive/` |
| Economy | `11 LihFolk V2/48 Economy Design Deep Dive/` |

## Not used

- **deividcomsono/Obsidian** is not a notes vault. It is a Roblox interface library that happens to be named "Obsidian", written for script executors (cheat-tool menus). It has nothing for a game factory and was not downloaded.

## Where the top-level notes draw on these

| Top-level note | Reference folders |
|---|---|
| [[20 - Slop Game Blueprints]] | Filhao `11 LihFolk V2/59 Viral and Trend Game Teardowns/`, `02 Game Design/Steal and Collect Tycoon Formula` |
| [[13 - Game Feel and Juice]] | Filhao `11 LihFolk V2/47 Game Feel and Juice/` |
| [[14 - UI and HUD Standard]] | Filhao `04 UI and GUI/`, `11 LihFolk V2/05 UI and UX/`, `09 Visual References/` |
| [[15 - Animation Standard]] | Filhao `05 Animation and Cutscenes/`, `11 LihFolk V2/08 Animation/` |
| [[16 - VFX and Audio Standard]] | Filhao `07 VFX/`, `06 SFX and Audio/` |
| [[17 - Icons Thumbnails and CTR]] | Filhao `11 LihFolk V2/61 Thumbnails and CTR/` |
| [[18 - AFK Idle and Offline Systems]] | Filhao `11 LihFolk V2/58 Player QoL and Game Tweaks/`; Kaffein `S-daily-retention-engine` |
| [[19 - Economy and Numbers]] | Filhao `11 LihFolk V2/48 Economy Design Deep Dive/` |
| [[22 - Live Ops and Updates]] | Filhao `11 LihFolk V2/38 Live Ops Deep Dive/`, `27 Marketing and Growth/` |

## Other resources found (not downloaded)

A second search on 11 Nov 2026 found no other Roblox-specific Obsidian vault of note. It did find agent-oriented knowledge packs on GitHub, all third-party and unreviewed; read before installing anything:

- `roblox-brain` (tabooharmony): 28 layered skills for Luau, architecture, networking, data, economy.
- `luau-skills` (stackfox-labs): language, types, performance, engine APIs, data stores.
- `roblox-game-development` (greedychipmunk): design-document templates and a workflow for Claude Code.
- `roblox-logics-mcp` and Brickwise: servers that hand an assistant sourced Roblox patterns and Luau examples.
- `roblox-pi-template` (dnouri): an AI-assisted project template with linter, formatter and publishing tools.

Free asset and tool sources are in [[23 - Free Resources and Tools]].

## How the AI builder should use these

1. Follow the top-level standard notes first.
2. Before writing a system, check the Kaffein reusable systems list for a pattern.
3. Before designing a screen or model, check the Filhao UI and modelling notes and screenshot boards.
4. Anything taken from either vault is untested until run in Studio.
