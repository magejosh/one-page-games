# Product Requirements Document (PRD) — Wilds of Aether

## 1. Overview
- **Elevator pitch**: A one-file, offline-playable Zelda-like open world with JRPG tactical battles. Explore a procedural archipelago, gather and craft, delve into dungeons, and fight on a turn-based grid.
- **Primary goal**: Deliver a polished, self-contained prototype showcasing open-world exploration + light survival + tactical battles within a single HTML file.
- **Secondary goals**: Clean UX (help/overlay, tabs), seedable worlds, save/load persistence, and an extensible content pipeline.

## 2. Audience and Platforms
- **Audience**: RPG and tactics fans; devs/designers reviewing lightweight prototypes; jam participants.
- **Platforms**: Modern desktop browsers (Chrome/Edge/Firefox). Keyboard-first; optional controller/touch later.
- **Performance target**: 60 FPS typical desktop; graceful degradation on low-power laptops.

## 3. Design Pillars
- **Explore and learn**: Learn-by-doing skills; discovery-driven exploration.
- **Tactics with clarity**: Turn-based grid combat with readable states and simple AI.
- **Self-contained**: No build tools or external deps; open and play.

## 4. Core Gameplay Loop
Explore → Gather resources → Craft improvements → Engage enemies (battle) → Level up (player + skills) → Rest/save → Push further from spawn to deeper dungeons and higher-tier loot.

## 5. MVP Scope
- **World/Traversal**
  - 128×128 seeded overworld; biomes: water, sand, grass, forest, mountains.
  - Minimap and map toggle, camera follows player, time-of-day clock.
- **Survival/Progression**
  - Hunger, thirst, stamina; campfire restores and reduces vitals.
  - Player levels via global XP; `needXP(lv) = 20 + 5*lv^2`; increases HP Max and Stamina Max.
  - Skills: Survival, Woodcutting, Mining, Foraging, Cooking, Crafting, Melee, Archery, Magic.
- **Crafting/Inventory**
  - Recipes: Stick, Campfire, Healing Draught; gated items (Wooden Sword, Short Bow, Leather Armor) via Crafting levels.
  - Inventory list, item use/craft/equip/drop; equipment slots (weapon, armor).
- **Dungeons**
  - Seeded drunkard-walk generation; stairs up/down, chest tiles; depth scales enemies/loot.
  - Enter via purple obelisks (Enter key).
- **Combat (Tactics)**
  - 12×12 grid; walls/floors; player + 2–3 enemies.
  - Stats: ATK, DEF, RNG, SPD. Move/Attack/Ability/Item/Wait/Flee actions.
  - Ability: Spark (Magic Lv2), range-3 nuke costing a turn.
  - Simple AI: brawler/skirmisher; approach and attack if in range.
- **Persistence & UX**
  - Save/Load via LocalStorage (player, world, skills, inv, equip, time, in-dungeon state when applicable).
  - Start/help overlay with controls and seed input; tabs for Journal/Inventory/Skills/Crafting; optional Pause menu.

## 6. Out of Scope (for MVP)
- Quests/story, NPCs, towns, complex economy.
- Advanced spell systems, ammo management, large itemization trees.
- Audio, controller/touch support, localization (planned later).

## 7. Content
- **Enemies**: Slime, Goblin, Wolf, Shade, Bandit (tiered by depth/distance); random stats within tier ranges.
- **Loot**: Tiered weapons/armor with prefixes/suffixes; consumables (berries, healing draughts); materials (wood/stone/herb/ore/berries).
- **Biomes**: As above; consider later adding snow/desert variations and unique resources/events.

## 8. UX Requirements
- Always-visible HUD for HP/Stamina/XP/Clock/Vitals.
- Minimap; world-map toggle feedback (toast).
- Contextual toast/log feedback for actions (gather, craft, equip, loot, level).
- Tabs for Journal, Inventory, Skills, Crafting; keyboard shortcuts I/C/K.
- Battle HUD with action buttons and hotkeys (1–6, Space for wait in some builds).
- Start/help overlay: controls, seed input, start/continue; optional Pause menu (Esc).

## 9. Technical Approach
- Single HTML file per release; vanilla JS + Canvas 2D + CSS.
- Deterministic RNG (XorShift + FNV hash seed); value noise for terrain; drunkard-walk for dungeons.
- LocalStorage for persistence; safe JSON (convert typed arrays to arrays and back).
- No external build/runtime dependencies; works offline.

## 10. Telemetry/Debug (optional)
- None collected. Use on-screen log/toasts for insight. Dev can inspect LocalStorage key `wilds_save`.

## 11. Accessibility & Options
- High-contrast UI theme; readable fonts.
- Future: scalable tile size, configurable keybinds, colorblind-friendly resource tints, motion reduction.

## 12. Risks
- Content depth: procedural sameness; mitigate with more recipes/events.
- Difficulty spikes: tuning enemy tiers/loot drop rates.
- Save compatibility between iterations; version stamp recommended.

## 13. Milestones
- **v0.1 (Exploration + Survival)**: Seeded overworld, basic resources, gather/craft (Stick/Campfire/Draught), HUD, minimap, save/load.
- **v0.2 (Combat + Dungeons)**: Turn-based grid battles, basic enemies/AI, dungeon entrances + generator, loot drops.
- **v0.3 (Skills + Abilities)**: Learn-by-doing skills, recipe gates, Spark ability (Magic Lv2), tiered gear.
- **v0.4 (Polish/UX)**: Start/help overlay with seed input, battle hotkeys, pause menu, improved feedback & toasts, map toggle; stability and save enhancements.

## 14. Acceptance Criteria (MVP)
- Start a new seeded world, roam without errors at 60 FPS typical.
- Forage/chop/mine; craft at least three baseline recipes; place and use campfire; vitals update correctly.
- Encounter overworld roamers and battle on a grid; defeat enemies and receive XP/loot.
- Enter a dungeon, possibly trigger battle; chest/ladder tiles appear; depth impacts enemy tier.
- Save and reload state without corruption; inventory/equipment/skills/position restored.
- All listed hotkeys function; help overlay accurately reflects controls.
