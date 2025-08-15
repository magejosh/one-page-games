## Starfall Raiders

Arcade, one‑page Space‑Invaders‑like. Marching enemy waves descend in formations, firing back as they bounce and drop. Clear waves to advance levels; every 5th level you draft one of three stackable upgrades to shape your build. Tight canvas visuals, crisp input, touch controls on mobile widths.

### Play it
- Open `Starfall_Raiders/starfallRaiders.html` in a modern desktop browser (Chrome/Edge/Firefox). No build step or assets required.

### Core features
- **Wave formations**: Classic horizontal march with edge‑bounce drop. Rows/columns scale with level; three enemy types: fast, normal, tank.
- **Enemy fire**: Enemies shoot randomly; fire rate increases with level. Bullets collide with player ship.
- **Player ship**: Smooth lateral movement, centered multi‑gun spread, and visible DPS approximation in the HUD.
- **Progression**: Levels advance when all enemies are destroyed. An upgrade draft appears every 5 levels; most upgrades stack.
- **Upgrades (current pool)**:
  - Twin Cannons (+1 gun)
  - Overclocked Trigger (‑15% fire cooldown)
  - Vector Thrusters (+20% move speed)
  - Armor‑Piercing Rounds (+1 bullet damage)
  - Wide Spread (+6° spread)
  - Phase Slugs (bullets pierce +1 enemy)
  - Kinetic Shielding (brief invulnerability on hit; stacks to 3)
  - Accelerators (+90 bullet speed)
  - Salvage Magnet (larger pickup radius)
  - Autonomous Drone (side drone fires every 0.4s)
- **Pickups & scoring**: Destroyed enemies sometimes drop scrap that drifts and can be magnetized to the ship; scrap adds score. Row‑clear bonus adds points as you breach formation rows.
- **HUD & overlays**: Top bar shows Level, Lives, Score, Guns, DPS, and Upgrades taken. Start overlay, Level‑Up selection overlay, and Game Over with final stats.
- **Touch support**: On narrow screens, on‑screen left/right/fire buttons appear.

### Controls
- **Move**: A / D or Arrow Keys
- **Fire**: Space or Enter
- **Pause**: P or Escape

### Objective
- **Survive and score**: Clear as many levels as possible while avoiding enemy fire. Build a synergistic kit via upgrades and push for a high score.

### Systems snapshot (current tuning)
- Enemies spawn in a grid that scales by level (columns clamp to 6–18; rows clamp to 3–10).
- Enemy speed and firing probability increase with level. Enemies drop a short distance each time the formation bounces at screen edges.
- Player has brief invulnerability after taking damage; lives act as continues.
- Every 5 levels, present three unique upgrade choices; choice immediately applies and the next wave begins.

### File guide
- `starfallRaiders.html` — Latest and only build for this project: includes overlays, HUD, wave scaling, upgrade draft, touch controls, starfield rendering.

### Tech
- Single HTML file; vanilla JS + Canvas 2D + CSS; DPR‑aware rendering for crisp visuals. Works offline.

### Roadmap ideas
- **Content**: Boss encounters every 10 levels, unique enemy patterns and projectiles, additional pickups (shields, temporary beam, score multipliers).
- **Systems**: Reroll/currency between drafts, limited consumables, temporary overheat mechanic, difficulty presets.
- **UX/Polish**: SFX/music with mute toggle, options menu (volume, UI scale), controller support, accessibility (reduced motion, color‑blind friendly accents).

### License / attribution
Prototype for learning/portfolio. If you fork or reuse, please keep attribution in the file header where applicable.


