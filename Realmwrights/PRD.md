# Product Requirements Document (PRD) — Realmwrights

## 1. Overview
- **Elevator pitch**: A single‑file, turn‑based 4X settlement builder. Guide a faction across a seeded map, harvest resources, research technology, and pursue multiple victory conditions against AI rivals.
- **Primary goal**: Deliver a readable, self‑contained prototype that captures the explore‑expand‑exploit‑exterminate loop.
- **Secondary goals**: Showcase faction asymmetry, basic diplomacy/trade, and clear end‑of‑turn feedback within one HTML file.

## 2. Audience and Platforms
- **Audience**: Fans of 4X and strategy builders, game‑jam players, and developers studying compact prototypes.
- **Platforms**: Modern desktop browsers (Chrome/Edge/Firefox). Desktop‑first; minimal mobile support.
- **Performance target**: Responsive UI and quick turns on maps up to 160×160 tiles.

## 3. Design Pillars
- **Tiny yet complete 4X**: All four Xs represented with streamlined mechanics.
- **Self‑contained**: One HTML file, no external assets or build steps.
- **Multiple victory paths**: Conquest, Technology, Culture, Trade, Political.
- **Readable decisions**: Clear resource bars, tooltips, and feedback each turn.

## 4. Core Gameplay Loop
1. Choose faction, map seed/size, AI count, difficulty, and victory conditions.
2. Explore with hero/worker, harvest resources, build structures, train units.
3. End turn → resources deposit, tech progresses, AI acts, year/turn advances.
4. Repeat until any victory condition is met or all players are defeated.

## 5. MVP Scope (current build)
- **Factions & Setup**
  - Seven playable factions (Human, Dwarf, Elf, Goblin, Orc, Highfolk, Scav Horde) with unique perks, units, and buildings.
  - Start menu for seed, map size (32–160 tiles), AI players (0–5), difficulty (Chill–Relentless), and togglable victories.
- **Map & Exploration**
  - Seeded map generation with forests, stone, food, crystal, gold, water, and fog of war.
  - Minimap and camera controls (zoom, pan, center on hero).
- **Economy & Buildings**
  - Resources: wood, stone, food, crystal, gold, population, culture, science, influence, trade routes.
  - Construct Town Hall, Houses, Sawmill, Quarry, Farm, Market, Temple, Barracks, Archery Range, Stable, University, Workshop, Crystal Lab, faction uniques.
  - Assign workers to resource nodes for automatic shuttling each turn.
- **Units & Combat**
  - Units: Worker, Militia, Archer, Knight, Hammerer, Berserker, Ranger, Druid, Slinger, Raider, Brute, Warg, Sage.
  - Basic melee/ranged combat with movement points and fog‑based visibility.
- **Technology & Progression**
  - Five‑tier tech tree culminating in Grand Theorem (technological victory). Tech costs increase by tier; unlocks buildings and bonuses.
- **Diplomacy & AI**
  - AI factions expand, harvest, research, trade, and sign treaties. Difficulty modifies aggression/efficiency.
- **Victory Conditions**
  - Conquest, Technological (Grand Theorem), Cultural (100 culture), Trade (1000 gold + 3 routes), Political (treaties with all + 100 influence).

## 6. Out of Scope (for MVP)
- Multiplayer or hot‑seat play.
- Detailed tactical combat or animations.
- Persistence (save/load) and complex UI scaling.

## 7. Content Details
- **Factions**: Each faction defines color, resource perks, unit roster, and a unique building granting special bonuses.
- **Resources**: Harvested from map tiles or buildings; carried resources deposit only at Town Hall.
- **Buildings**: Provide population, yields, trade routes, culture, science, or unit unlocks.
- **Units**: Have HP, attack, defense, move, and some special traits (ranged, heal, hero bonuses).
- **Tech Tree**: Tiered progression (Logging → Stonework → … → Grand Theorem) with prerequisites and unlock texts.

## 8. Win Conditions & Tuning
- Turn counter increments yearly every 10 turns.
- Resource nodes spawn with ~80–120 units; buildings and perks boost yields.
- Tech costs: 10 (tier1), 20 (tier2), 35 (tier3), 55 (tier4), 120 (tier5).
- Workers carry up to 20 resources; combat stats vary by unit type.

## 9. UX Requirements
- Start overlay with setup options and control legend.
- In‑game HUD: top resource bar, turn/year indicator, left panel tabs (Build/Units/Tech/Diplomacy/Help), right panel selection info, bottom action/log area, minimap, tooltips.
- Victory modal with summary and restart button.

## 10. Technical Approach
- Single HTML file with inline CSS/JS; Canvas 2D for map rendering.
- Procedural map generation via simple noise blobs; mulberry32 RNG for seeding.
- Per‑turn update loop triggered on "End Turn"; simple pathfinding and AI routines.
- Works offline once downloaded.

## 11. AI Behaviors
- AI places starting town, gathers nearby resources, expands with buildings/units, researches tech, and checks for victories.
- Difficulty levels modify production bonuses and aggression.

## 12. Accessibility & Options
- High‑contrast UI palette; tooltips for controls and resources.
- Options for map size, AI count/difficulty, and starting visibility.
- Roadmap: color‑blind friendly accents, UI scaling, configurable hotkeys.

## 13. Risks
- UI density and cognitive load despite small screen footprint.
- AI pathfinding/decision cost on large maps.
- Balance of tech tree and victory condition pacing.

## 14. Milestones
- **v0.1 (done)**: Core loop with factions, resources, buildings, units, tech, AI, and all victory conditions.
- **v0.2 (polish)**: Audio/visual feedback, smarter AI diplomacy, save/load, improved animations.
- **v0.3 (content)**: Additional factions, units, buildings, and late‑game tech.

## 15. Acceptance Criteria (MVP)
- Start screen lets players pick faction, map, AI, difficulty, and victory types; clicking Start enters game.
- Fog‑of‑war map renders; hero/worker can move, harvest, and return resources to Town Hall.
- Buildings construct when resources are available; units train from appropriate structures.
- Ending a turn processes resource shuttling, tech progress, AI turns, and year advancement.
- Victory modal appears when any enabled condition is satisfied; restart returns to setup screen.

