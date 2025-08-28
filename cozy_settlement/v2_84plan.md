# Cozy Chief v2.84 Design Proposal

## Goals
- Reduce reliance on static action buttons by introducing an on-map player avatar.
- Expand exploration and resource gathering through procedurally scattered nodes.
- Rework Chief's Longhouse as a unique, upgradable building.
- Refresh the tech tree with richer medieval fantasy themes inspired by *Realmwrights* and *Dominion*.
- Replace problematic emojis for Chief's Longhouse and Stone Quarry.

## Feature Outline
### 1. Player Avatar and Exploration
- Add a movable avatar represented by the emoji **🏃** that the player can direct on the grid.
- Scatter resource nodes (trees, berry bushes, stone outcrops, clay pits) across the map at world generation.
- Resources are collected by moving the avatar onto nodes, reducing dependence on top‑bar buttons.
- Avatar movement consumes time; later techs can improve speed or carrying capacity.

### 2. Unique Chief's Longhouse
- Only one Longhouse may exist at a time.
- New default emoji: **🏰**.
- Acts as a hub for narrative events and knowledge generation.
- Tech upgrades:
  - **Council Hall** – boosts knowledge gain and unlocks policy choices.
  - **War Room** – enables scout missions for rare resources.
  - **Great Hall** – attracts visiting heroes that grant temporary buffs.

### 3. Stone Quarry Emoji Refresh
- Update building list to use **⛏️** for Stone Quarry instead of the current unsupported icon.

### 4. Expanded Tech Tree
- Branch into thematic paths:
  - **Crafts & Guilds** – unlocks Workshop, Artisan bonuses, trade goods.
  - **Mysticism** – Shrine upgrades, mana crystals, culture bonuses.
  - **Engineering** – stone roads, bridges, water mills.
  - **Exploration** – scouting parties, map reveals, avatar upgrades.
- Each branch offers 3–4 tiers with dependencies, creating a broader, more nuanced progression.

### 5. Miscellaneous Improvements
- Procedural world seed option for replayability.
- Early tutorial tasks encouraging avatar exploration.

## Changelog Highlights
- Introduced avatar‑based resource gathering and exploration.
- Chief's Longhouse is now a unique, upgradeable structure (**🏰**).
- Stone Quarry emoji replaced with **⛏️** for better compatibility.
- Tech tree expanded with new thematic branches influenced by *Realmwrights* and *Dominion*.
- Added procedural resource nodes and world seeds.

## Open Questions
- How should movement and pathfinding be visualized without heavy simulation?
- What limits should exist on avatar inventory or gather range?
- Balancing knowledge generation with Longhouse upgrades.


## v2.84 Expansion Plan

### Overview
Build on v2.83 by deepening progression and adding light fantasy conflict.

### Key Additions
- **Deeper Tech Tree**: restructure tech data to support 20+ columns and branching paths. Add early concepts for guard towers, adventurers, arcana, and civic upgrades.
- **Building Upgrades**: allow Woodcutter Huts to upgrade into Lumber Mills when "Forestry" is researched. Structure allows future upgrade chains.
- **Wandering Fauna & Monsters**: simple roaming animals on the map; some spawn as gold‑carrying monsters that threaten buildings.
- **Defenses & Adventurers**: introduce Guard Tower and Adventurers Guild buildings that train units to protect tiles or clear dungeons.
- **Terrain Types**: color‑coded tiles (grass, forest, hill, water) with placement bonuses/restrictions, procedurally generated.
- **Resource Delivery Visuals**: buildings periodically send a villager emoji along paths to the Longhouse to drop off goods.
- **Fantasy Resources & UI Layout**: add Mana and Hide resources, adjust top bar layout for future expansion.

### Non-goals for v2.84
- Full card‑battle system for dungeons (stub only).
- Complex pathfinding or combat AI beyond simple proximity checks.

### Open Questions
- How to balance wandering monsters with cozy pacing?
- Should terrain bonuses be multiplicative or unlock exclusive structures?
- How many upgrade tiers should defensive structures support?

### Farming & Hunting Expansion (v2.84+)
- Techs: Farming (Farm, Wheat Field), Hunting (Hunters Lodge), Tanning (Tanner), Butchery (Butcher), Blacksmithing (Blacksmith).
- Resources: Adds Meat (🍖). Hunters and Ranches generate meat; Butchers convert meat ➜ food.
- Adjacency: Farms get +15% per adjacent Wheat Field; Wheat Fields get +10% per adjacent Farm.
- Automation: Each Hunters Lodge trains a hunter that periodically hunts animals, returning meat/hides. If a Tanner exists, hunted yields get +25% and goods are delivered to Longhouse.
- Ranch: Steady meat and hides.
