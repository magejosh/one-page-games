## Wilds of Aether

A single-file, browser-playable Zelda-like open world with JRPG-style tactical battles. Explore a procedurally generated archipelago, gather resources, craft gear, delve into dungeons, and fight turn-based battles on a grid.

### Play it
- Open `wilds_of_aether/wilds_of_aether.html` in a modern desktop browser (Chrome/Edge/Firefox). This is the latest iteration.
- Numbered files (`wilds_of_aether02.html`, `wilds_of_aether03.html`, `wilds_of_aether04.html`) are preserved snapshots that show the project’s evolution.

### Core features
- **Open world**: 128×128 tile map with water, sand, grass, forest, and mountains; purple obelisks mark dungeon entrances.
- **Procedural generation**: Repeatable world seeds for both overworld and dungeon maps. The latest build prompts for a seed when starting a new world.
- **Survival layer**: Time of day, hunger, thirst, stamina. Campfires restore and reduce vitals.
- **Learn-by-doing skills**: `Survival, Woodcutting, Mining, Foraging, Cooking, Crafting, Melee, Archery, Magic` level up through use.
- **Crafting**: Simple recipes that unlock with skills (e.g., Stick, Campfire, Healing Draught, Wooden Sword, Short Bow, Leather Armor).
- **JRPG tactical combat**: Contact enemies to enter a 12×12 grid battle. Player/enemy turns, movement range, ATK/DEF/RNG/SPD stats, ability hotkeys.
- **Abilities**: Early example is `Spark` (Magic Lv2), a ranged zap that grants Magic XP.
- **Loot and gear**: Randomized weapon/armor drops with tiers/prefixes; inventory and equipment management.
- **Minimap and map toggle**: Always-on minimap; world-map toggle.
- **Saving/Loading**: LocalStorage-based saves (`wilds_save`) including world, inventory, skills, and (in latest build) dungeon state.

### Controls
- **Move**: WASD / Arrow Keys
- **Gather/Interact**: F (trees, stone, herbs, ore, berries)
- **Enter dungeon / use stairs**: Enter
- **Inventory / Crafting / Skills**: I / C / K
- **World map toggle**: M
- **Zoom**: Z / X (in 02/03/04)
- **Battle hotkeys** (02/03): 1 Move, 2 Attack, 3 Ability, 4 Item, 5 or Space Wait, 6 Flee
- **Pause menu**: Esc (03)

### Gameplay loop
Explore → Forage/Chop/Mine → Craft → Battle → Level up (player + skills) → Rest → Repeat deeper from spawn to find higher-depth dungeons and better loot.

### Systems snapshot
- **World**: Seeded value-noise for terrain; dungeons carved by drunkard-walk. Distance from spawn and dungeon depth increase enemy tiers.
- **Enemies**: Overworld roamers that drift toward the player; dungeon enemies by depth. AI closes distance and attacks when in range.
- **Progression**: `needXP(lv) = 20 + 5*lv^2`. Level-ups increase HP Max and Stamina Max; skills improve effectiveness and unlock recipes/abilities.
- **Crafting (examples)**:
  - Stick: 1× Wood → 2× Sticks
  - Campfire: 3× Wood + 2× Stone → placeable/rest
  - Healing Draught: 2× Herb + 1× Berries → heal 12
  - Wooden Sword (Crafting Lv2): 2× Wood + 1× Stick
  - Short Bow (Crafting Lv3): 2× Wood + 1× Stick
  - Leather Armor (Crafting Lv3): 3× Berries + 2× Herb

### Saving/Loading
- Use in-game Save/Load buttons. Saves are version-local; mixing iterations may not be compatible.
- Key used: `localStorage['wilds_save']`.

### File guide (evolution)
- `wilds_of_aether.html` — Latest build: Quick Start overlay, refined HUD, dungeon save support, expanded feedback.
- `wilds_of_aether03.html` — Adds Pause Menu (Esc), robust battle hotkeys, battle-grid click fixes, structured timers.
- `wilds_of_aether02.html` — Start overlay with seed input, zoom (Z/X), layout/minimap improvements.
- `wilds_of_aether04.html` — Early UI with in-scene quickbar, roaming enemies, and combined tabs.

### Tech
- Single HTML file per build; vanilla JS + Canvas 2D, CSS UI. No external dependencies.
- Works offline; open the file directly.

### Roadmap ideas
- **Content**: More biomes, enemy types, dungeon setpieces, bosses, events/quests.
- **Systems**: Ranged ammo, expanded magic, armor sets, cooking/fishing, shelters/base-building.
- **UX**: Controller/touch support, options menu, keybinding, improved map/UI.
- **Polish**: Audio, effects, hit feedback, accessibility options.

### License / attribution
Prototype for learning/portfolio. If you fork or reuse, please keep attribution in the file header where applicable.
