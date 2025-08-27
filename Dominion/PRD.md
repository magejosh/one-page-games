# Product Requirements Document (PRD) — Hearth & Dominion

## 1. Overview
- **Elevator pitch**: A single-file settlement RTS. Choose a fantasy faction, gather wood, crystal, and gold, build a town, research techs, train units, and fend off raider camps on your march toward cultural, technological, diplomatic, trade, or military victory.
- **Primary goal**: Deliver a playable, self-contained prototype of a classic base-building RTS with multiple victory paths in one HTML file.
- **Secondary goals**: Distinct faction bonuses, readable SVG map, minimal UI for build/tech panels, and a light enemy AI loop.

## 2. Audience and Platforms
- **Audience**: Fans of Age-of-Empires/Warcraft-style RTS games, designers looking for compact strategy prototypes.
- **Platforms**: Modern desktop browsers (Chrome/Edge/Firefox). Mouse + keyboard.
- **Performance target**: 60 FPS on typical laptops/desktops.

## 3. Design Pillars
- **One-page strategy**: Everything from UI to simulation lives in a single HTML file.
- **Meaningful choices**: Factions and techs meaningfully alter build orders and unit rosters.
- **Clarity over complexity**: Readable map tiles, units, and panels keep the game approachable.

## 4. Core Gameplay Loop
Gather → Deposit resources → Construct buildings → Train units & research → Defend against raiders → Push toward any victory condition → Repeat.

## 5. MVP Scope
- **Factions**
  - Six core factions (Human, Dwarf, Elf, Goblin, Orc, plus Alliance/Horde hybrids) each with economic mods and a unique unit.
- **Resources & Economy**
  - Wood, Gold, and Crystal; workers harvest then deposit at the Town Hall or resource camps.
  - Population cap managed via Houses/Farms; victory points accumulate passively through certain buildings.
- **Buildings**
  - Town Hall, House, Lumber Camp, Mine, Farm, Barracks, Archery Range, Mage Tower, Market, Embassy, Shrine, Theater, Library, Workshop.
  - Build menu (B) with placement previews and cost checks.
- **Units**
  - Hero, Worker, Soldier, Archer, Mage, plus faction uniques (Knight, Defender, Ranger, Sapper, Berserker, Paladin, Warchanter) and Caravan.
  - Selection groups (1 Hero / 2 Workers / 3 Army); attack mode and rally-to-hero toggles.
- **Tech Tree**
  - Research panel (T) with prerequisite chains unlocking buildings/units and culminating in a Grand Invention tech victory.
- **Enemies**
  - Raider camps spawn enemy units roughly every 5 seconds that path toward player structures.
- **Victory**
  - Five categories (Culture, Tech, Diplomacy, Trade, War) with threshold targets; achieving any triggers a win screen.
- **UI & UX**
  - Top bar shows resources, population, and VP progress; left/right panels for build and tech; help dialog (H) with control summary.

## 6. Out of Scope (for MVP)
- Multiplayer or PvP.
- Advanced enemy factions, sieges, or boss units.
- Persistent saves, campaign, or map editor.
- Audio, extensive animations, or localization.

## 7. Content Details
- **Resource nodes**: ~220 trees, 28 crystals, 20 gold deposits scattered across a 48×30 tile map.
- **Victory points**: Shrine/Theater generate Culture; Library/Workshop enable Tech; Embassy for Diplomacy; Market/Caravan for Trade; destroying camps grants War points.
- **Pathfinding**: A* over a grid with basic obstacle checks.

## 8. Economy & Tuning (as implemented)
- Buildings cost 40–180 resources; techs require 40–180 resources and 6–20s research times.
- Units move between 60–90 speed; combat uses simple attack timers with melee/ranged ranges.
- Raider spawn timer ~5s per camp; victory targets: Culture 1000, Tech 1, Diplomacy 1000, Trade 1000, War 3.

## 9. UX Requirements
- Click-and-drag selection box; right-click movement and attack when attack mode active.
- Build placement shows blocked tiles in red; cursor feedback on gatherable resources and enemy targets.
- Responsive panels with scroll for long lists.

## 10. Technical Approach
- Single HTML file using vanilla JS and SVG for rendering; no external dependencies.
- Deterministic game loop tied to `requestAnimationFrame`; grid stored in arrays for collision and pathfinding.

## 11. Telemetry / Debug
- None. Console logs for significant events and on-screen log panel.

## 12. Accessibility & Options
- High-contrast palette and scalable SVG icons.
- Roadmap: pause menu, hotkey remapping, and colorblind-friendly resources.

## 13. Risks
- Pathfinding performance with many units.
- UI scaling on very high resolutions.
- Balance between economic growth and defense.

## 14. Milestones
- **v0.1 (done)**: Faction selection, core economy, build/tech panels, raider AI, victory checks.
- **v0.2 (polish)**: Sound, improved unit feedback, minimap, keyboard remapping.
- **v0.3 (content)**: Additional tech tiers, diplomacy/trade mechanics, varied enemy waves.
- **v0.4 (stretch)**: Map seeds, saving/loading, campaign scenarios.

## 15. Acceptance Criteria (MVP)
- Start screen lists factions; picking one begins a game with a Town Hall, House, hero, and resources.
- Workers harvest and deposit resources; population cap increases with Houses/Farms.
- Build menu places valid structures and deducts costs; tech panel queues research and unlocks items.
- Units move, attack, and follow commands; raiders spawn and target player assets.
- Any victory category reaching its threshold triggers the victory screen.
