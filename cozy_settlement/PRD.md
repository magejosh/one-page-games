## Product Requirements Document — Cozy Chief

### 1) Vision
Deliver a warm, self-contained medieval settlement toy where players guide a tiny hamlet into a thriving borough within a single HTML file. Emphasize clarity, cozy vibes, and quick sessions.

### 2) Goals & Non-Goals
- Goals
  - Provide a frictionless city-builder loop with manual gathering → automation via buildings → tech-driven expansion.
  - Represent time, seasons, and happiness in a readable way.
  - Support growth tiers with distinct milestones and a lightweight tech tree.
  - Keep everything in one offline-playable HTML file with minimal assets.
- Non-Goals
  - Deep simulation (agent pathing, complex economy).
  - Combat or external threats.
  - Multiplayer or persistent online saves.

### 3) Target Audience
- Fans of relaxed city builders who want a quick in-browser prototype.
- Game-jam participants and developers seeking a compact reference.

### 4) Core Gameplay Loop
1. Forage wood/food/stone to bootstrap resources.
2. Place buildings on the map to automate production.
3. Accumulate goods, unlock technologies, and meet tier milestones.
4. Expand with new buildings and bonuses; repeat to reach Borough IV.

### 5) Feature Set (MVP → Polished)
- MVP
  - Manual resource gathering buttons.
  - Building placement on a tile grid; basic structures (Woodcutter Hut, Farm, Cottage).
  - Time flow with days and seasons affecting farm output.
  - Population/housing, happiness meter, tier advancement.
- Polished
  - Knowledge as a research currency and a branching tech tree unlocking new structures (School, Market, Workshop, etc.).
  - Minimap, camera pan/zoom, and placement highlight.
  - Random events: Chief’s Longhouse lore grants knowledge; quarries occasionally yield iron or gold.
  - Expanded economy (clay→bricks, flax→linen, tools, culture, faith).

### 6) Systems Detail
- **Resources**: wood, stone, food, gold, clay, flax, linen, iron, tools, housing, population, faith, knowledge, culture.
- **Buildings**: produce or convert resources, grant housing or mood, or unlock events (e.g., Chief’s Longhouse, Quarry, Shrine, School).
- **Time & Seasons**: 24‑minute days; four-season cycle modifies farm yields.
- **Happiness & Population**: happiness drifts based on food/housing; higher happiness boosts growth; tiers require population + resource milestones.
- **Tech Tree**: nodes such as Masonry, Crafting, Trade Guilds provide unlocks and modifiers; requires knowledge earned over time.
- **Events**: periodic checks for knowledge from Longhouses and rare quarry finds.

### 7) UX & Controls
- Point-and-click UI with gather buttons and building cards.
- Drag map to pan; mouse wheel to zoom; minimap click-to-jump.
- `Esc` cancels placement; toasts/logs report events and errors.

### 8) Technical Requirements
- Single-file HTML with inline JS/CSS; minimal DOM + Canvas for minimap.
- Runs offline in latest desktop Chrome/Edge/Firefox.
- Target 60 FPS on typical laptops; cap zoom to maintain performance.

### 9) Success Metrics
- Time-to-first building placement under 30 seconds.
- Typical session length 10–20 minutes to reach Borough IV.
- Stable performance with <5% frame drops at default zoom.

### 10) Milestones
- M0 (done): Foraging and basic building placement (v2.1).
- M1 (done): Seasons, happiness, tiers, minimap, camera (v2.5).
- M2 (done): Tech tree and knowledge events, quarry finds (v2.7).
- M3 (next): Trade routes, save/load improvements, more buildings.
- M4 (stretch): Audio cues, accessibility options, mobile-friendly UI.

### 11) Open Questions / Risks
- Balance of resource production vs. consumption across tiers.
- UI scalability on small screens or high zoom levels.
- Long-term engagement once Borough IV is reached; need for end-state or sandbox tools.
