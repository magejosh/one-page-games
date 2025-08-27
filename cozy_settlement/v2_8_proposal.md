# Cozy Chief v2.8 Design Proposal

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
- New default emoji: **🛖**.
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
- Chief's Longhouse is now a unique, upgradeable structure (**🛖**).
- Stone Quarry emoji replaced with **⛏️** for better compatibility.
- Tech tree expanded with new thematic branches influenced by *Realmwrights* and *Dominion*.
- Added procedural resource nodes and world seeds.

## Open Questions
- How should movement and pathfinding be visualized without heavy simulation?
- What limits should exist on avatar inventory or gather range?
- Balancing knowledge generation with Longhouse upgrades.

