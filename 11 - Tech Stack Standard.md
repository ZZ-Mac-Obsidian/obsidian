---
type: standard
area: engineering
status: draft
updated: 2026-11-11
tags: [factory, toolchain, architecture]
---

# Tech Stack Standard

The same engineering setup for every factory game, so code, fixes and systems carry from one game to the next. Part of the standard in [[00 - Start Here]]; gameplay rules are in [[01 - Game Standard]].

**Status: draft from general knowledge, not checked against current releases.** Roblox tooling changes quickly. The AI builder must confirm each tool is current and maintained before adopting it, and say so if a better option exists.

## Project layout

One repository per game, scripts kept as files and synced into Studio.

```
src/
  server/      game logic, data, purchases (server only)
  client/      input, camera, effects, interface
  shared/      config tables, types, constants, networking definitions
  ui/          interface components
assets/        exported models, palette textures (see [[04 - Blender Pipeline]])
docs/          state, decisions, credits
```

- **All tuning numbers live in shared config tables**: prices, upgrade costs, early-wins timings, area sizes. A new game is mostly new config and new models.
- One module per system, with a small public interface. No system reaches into another's internals.

## Toolchain

| Job | Tool to check first | Note |
|---|---|---|
| Sync files to Studio | Rojo | Lets the AI builder work in files |
| Packages | Wally | Pin versions |
| Lint and format | Selene, StyLua | Run before every commit |
| Types | Luau strict mode | On for all shared and server code |
| Version control | Git, one repository per game | Commit at each milestone |
| Checks on push | A simple GitHub Actions workflow running lint and format | Optional for a solo developer |

## Libraries

Prefer few, well-maintained libraries. Check each before use.

| Need | Check first | Avoid |
|---|---|---|
| Player data with session locking | ProfileStore (successor to ProfileService) | Hand-written saving |
| Interface | React for Luau, or Fusion | Roact (superseded) |
| Service structure | Plain modules with a small loader | Knit (author no longer recommends it for new work) |
| Promises, cleanup | A promise library; Trove or Janitor | |
| Top bar buttons | TopbarPlus | |

## Architecture rules

- **Server decides everything that matters**: currency, progress, purchases, world state. Clients send intentions; the server checks distance, rate and ownership.
- **Networking defined in one shared file.** Every remote has a typed payload and a rate limit.
- **Compact payloads for high-frequency actions** (strokes, clicks, hits): pack position, tool and radius into a buffer and send on an unreliable channel; send state changes that must arrive on a reliable one.
- **State as bit arrays** for large grids of on/off cells.
- **Purchases** handled in one receipt function that grants the item, saves, and only then confirms.
- **Data**: one profile per player, versioned with a migration step, saved on leave and on an interval.
- **Tags and attributes** mark world objects (interactive part, drop point, spawn) so scripts find them without hard-coded paths.
- **Streaming on**, effects and fine detail created only near the player.

## Performance budget

- Target 60 frames a second on PC and a steady 30 on a low-end phone with four players and helpers active.
- Profile with Roblox's built-in profiler at each milestone from the first area onward.
- Watch memory on phones; avoid stacks of semi-transparent surfaces.

## Testing

- Play in Studio after every change, including a phone-sized screen and a multi-player test session.
- Fresh-save run timed against the early-wins table.
- Leave mid-area and rejoin; shut the server down and rejoin.

## Where to look things up

Deeper notes live in the downloaded libraries indexed in [[10 - Reference Vaults]]:

- Reusable systems and code snippets: `References/Kaffein Dev Vault/03 - Reusable Systems/`, `11 - Templates and Schemas/Luau Snippets/`
- Server authority, remotes, data safety: `References/Kaffein Dev Vault/02 - Roblox Development/`
- Open-source libraries and frameworks: `References/Filhao Roblox Vault/08 Coding/`
- Engine and API reference cards: `References/Filhao Roblox Vault/11 LihFolk V2/57 API and Concept Atlas/`, `62 Engine Reference Cards/`
- Security: `References/Filhao Roblox Vault/11 LihFolk V2/22 Anti-Exploit and Security/`

## Systems every slop game needs

Build these once in the shared package; each game configures them.

| System | Notes |
|---|---|
| Player profile with session locking, versioning and migration | everything else depends on it |
| Config module | every price, rate, timing, rarity weight and theme colour |
| Currency and income tick | server-side, one loop for all earners, batched updates to clients |
| Weighted roll | one table feeds the roll and the odds screen |
| Plot or base assignment | one per player, released on leave |
| Carry, steal and deposit | server-checked distance, ownership and rate |
| Hazard clock | derived from server time so all clients agree |
| Rebirth | one function that resets and grants, atomically |
| Offline earnings | saved server time, clamped and capped ([[18 - AFK Idle and Offline Systems]]) |
| Receipts and passes | grant, save, then confirm; policy checks per player |
| Rewards hub | daily calendar, playtime gifts, codes, group reward |
| Announcements | server-wide and cross-server messages for rare finds and events |
| Leaderboards | ordered store, refreshed on an interval |
| Analytics | funnel and economy events with the same names in every game |
| Settings | saved per player: volumes, reduced effects, hide others, low detail |
| Effects and sound player | named effects called from anywhere, played on the client |
| Interface components and theme | [[14 - UI and HUD Standard]] |

## Working with an AI builder in Studio

- Roblox's Studio MCP server lets the builder read the place, run code, start and stop play-tests, capture the screen and read the console. Use it to verify every change by playing and by looking.
- Keep code in files synced to Studio where possible so changes are reviewable and versioned.
- The builder should check the output console after every play-test and treat a warning as a bug.
- Never build in the live place. Use a test place; publish deliberately.

Related: [[03 - Monetization and Shop Standard]], [[05 - Publish Checklist]], [[07 - Build Prompt Template]], [[08 - Sources and Unknowns]], [[21 - Build Order]], [[23 - Free Resources and Tools]].
