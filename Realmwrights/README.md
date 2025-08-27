## Realmwrights

Turn-based, one-page 4X settlement builder. Choose a faction, explore a foggy map, gather resources, raise buildings and units, and compete with AI rivals across multiple victory paths.

### Play it
- Open `Realmwrights/Realmwrighs.html` in a modern desktop browser (Chrome/Edge/Firefox). No build step or assets required.

### Core features
- **Factions & perks**: Humans, Dwarves, Elves, Goblins, Orcs, Highfolk, and Scav Horde each grant unique bonuses, units, and signature buildings.
- **Procedural map**: Seeded tile map with forests, stone, food, crystal, gold, and water plus fog of war and minimap.
- **Resource economy**: Wood, Stone, Food, Crystal, Gold, Population, Culture, Science, Influence, Trade routes.
- **Buildings & units**: Town Hall, Houses, Sawmill, Quarry, Farm, Market, Temple, Barracks, Archery Range, Stable, University, Crystal Lab, Workshop, faction uniques, plus workers, militia, archers, knights, and more.
- **Technology tree**: Five tiers culminating in the Grand Theorem tech for a technological win.
- **Diplomacy & trade**: Treaties, trade routes, and AI opponents with multiple difficulty levels.
- **Victory paths**: Conquest, Technological, Cultural, Trade, and Political.

### Controls
- **Left-click**: select / move
- **Right-click**: pan map
- **Mouse wheel / - =**: zoom
- **WASD**: pan
- **E**: center on hero
- **Enter**: end turn

### Objective
- Pursue any enabled victory condition while managing resources, expanding territory, and countering rival factions.

### Systems snapshot (current tuning)
- Map size from 32×32 up to 160×160 tiles; seeded generation allows reproducible worlds.
- Workers can be assigned to resource nodes to shuttle goods back each turn; resources deposit only at the Town Hall.
- Turns advance time; every 10 turns equals 1 year. Upkeep, tech research, and AI actions process on end turn.
- AI factions expand, harvest, research, trade, and contest victory conditions.

### File guide
- `Realmwrighs.html` — Latest and only build.

### Tech
- Single HTML file using vanilla JS + Canvas + CSS; works offline once downloaded.

### Roadmap ideas
- Additional buildings, units, and tech tiers.
- Smarter AI personalities and diplomacy events.
- Audio, animations, and save/load.

### License / attribution
Prototype for learning/portfolio. If you fork or reuse, please keep attribution in the file header where applicable.

