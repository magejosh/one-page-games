# Product Requirements Document (PRD) — Starfall Raiders

## 1. Overview
- **Elevator pitch**: A one‑file, instantly playable, modernized Space‑Invaders‑like. Defeat cascading enemy formations, dodge incoming fire, and draft stackable upgrades every 5 levels to build powerful synergies.
- **Primary goal**: Deliver a polished, self‑contained arcade prototype with readable combat, satisfying upgrade choices, and escalating challenge.
- **Secondary goals**: Smooth input and feedback, touch support, and a stylish, readable HUD—all in a single HTML file with no external dependencies.

## 2. Audience and Platforms
- **Audience**: Fans of classic arcade shooters, game‑jam players, and devs/designers seeking reference for minimal canvas shooters.
- **Platforms**: Modern desktop browsers (Chrome/Edge/Firefox). Touch controls for mobile widths; desktop‑first tuning.
- **Performance target**: 60 FPS on typical desktop hardware; graceful degradation on integrated graphics.

## 3. Design Pillars
- **Instant clarity**: Enemies and bullets are readable; controls are obvious; time‑to‑fun < 5 seconds.
- **Crunchy upgrades**: Small set of meaningful, stackable upgrades that change firing patterns and movement feel.
- **Arcade focus**: Short sessions, high scores, and “one more wave” pacing.
- **Self‑contained**: Single HTML file; no build pipeline.

## 4. Core Gameplay Loop
Play wave → Clear formation → Level increases → Every 5th level: choose 1 of 3 upgrades → Next wave spawns → Repeat while dodging shots and collecting pickups for score.

## 5. MVP Scope (current build)
- **Player**
  - Lateral movement; multi‑gun spread centered on the ship.
  - Shooting with cooldown; DPS approximation shown in HUD.
  - Lives with brief post‑hit invulnerability; optional shielding stacks from upgrades.
- **Enemies**
  - Formation march with horizontal bounce and vertical drop.
  - Types: fast, normal, tank (HP/speed variations), random firing toward player.
  - Level‑scaled formation size, speed, and firing probability.
- **Combat**
  - Player/enemy bullets with axis‑aligned collision.
  - Particles and small explosions for feedback.
- **Progression & Scoring**
  - Levels advance after clearing all enemies; row‑breach bonus adds score.
  - Pickups (scrap) randomly drop; magnet upgrade increases attract radius.
  - Upgrade draft appears every 5 levels; three unique options per draft.
- **UX & Presentation**
  - Start overlay (controls + Start), Level‑Up overlay (upgrade cards), Game Over overlay (final stats).
  - HUD: Level, Lives, Score, Guns, DPS, Upgrades taken. Toast messages for events (row breached, scrap gained, upgrade acquired).
  - Touch buttons (left/fire/right) on small screens.

## 6. Out of Scope (for MVP)
- Boss fights and unique patterns per boss.
- Complex enemy formations (swoops, sine waves, homing projectiles).
- Meta‑progression, currency runs, unlock trees.
- Audio, localization, keybinding UI (can be roadmap).

## 7. Content Details
- **Enemy Types**
  - Fast: moves slightly faster; low HP.
  - Normal: baseline stats.
  - Tank: higher HP; slower.
- **Upgrades (initial pool)**
  - Twin Cannons (+1 gun)
  - Overclocked Trigger (‑15% fire cooldown, min clamp applied)
  - Vector Thrusters (+20% move speed)
  - Armor‑Piercing Rounds (+1 damage)
  - Wide Spread (+6° spread; benefits multi‑gun)
  - Phase Slugs (bullets pierce +1 enemy)
  - Kinetic Shielding (gain brief invulnerability on hit; stacks up to 3)
  - Accelerators (+90 bullet speed)
  - Salvage Magnet (+40 pickup radius per pick)
  - Autonomous Drone (side drone fires every 0.4s, 3‑shot sweep)
- **Pickups**
  - Scrap: adds score; drifts with slight physics; magnetizable toward player.

## 8. Difficulty & Tuning (as implemented)
- Formation sizing: columns = clamp(6 + ⌊level×0.6⌋, 6, 18); rows = clamp(3 + ⌊level×0.25⌋, 3, 10).
- Enemy speed: clamp(30 + level×6, 30, 210).
- Enemy fire probability per frame: clamp(0.001 + level×0.00025, 0.001, 0.006) scaled to dt.
- Edge bounce drop: formation drops by ~18 px on direction flip.
- Row‑breach bonus: adds points proportional to level when the number of alive rows decreases.
- Upgrade cadence: at levels 5, 10, 15, …

## 9. UX Requirements
- Always‑visible HUD elements for Level, Lives, Score, Guns, DPS, Upgrades.
- Overlays: Start (with controls), Level‑Up (3 selectable cards), Game Over (final stats + restart).
- Transient messages for key events (upgrade acquired, scrap collected, row breached, ship hit).
- Touch controls on narrow screens; desktop keyboard controls listed in Start overlay and top bar.

## 10. Technical Approach
- Single HTML file; vanilla JS + Canvas 2D + CSS; no dependencies.
- DPI‑aware canvas rendering (cap DPR to reasonable value); starfield parallax background.
- Deterministic‑enough game loop with requestAnimationFrame; time‑step clamped to avoid large jumps.
- Simple AABB collisions; minimal allocations inside the frame loop; periodic array compaction.
- Works offline (file can be opened directly).

## 11. Telemetry/Debug
- No data collection. Use on‑screen toasts/messages for runtime insight.

## 12. Accessibility & Options
- High‑contrast palette; clean typography.
- Roadmap: reduced‑motion toggle (dim starfield/particles), color‑blind friendly accent toggle, UI scale, key‑remap, controller support.

## 13. Risks
- Variety fatigue: formation‑only patterns may feel samey without bosses/patterns.
- Balance of upgrades: certain combinations (e.g., heavy spread + many guns) could trivialize waves.
- Mobile performance and touch precision on very small screens.

## 14. Milestones
- **v0.1 (done)**: Core loop (movement, shooting, waves, enemy fire), HUD/overlays, upgrade draft every 5 levels, pickups, touch controls, basic particles.
- **v0.2 (polish)**: Audio SFX/Music + mute toggle, options menu (volume, UI scale), difficulty presets; tuning pass on upgrade weights.
- **v0.3 (content)**: Boss every 10 levels; 2–3 new enemy patterns; additional upgrades and pickups; score multipliers; end‑screen stats.
- **v0.4 (stretch)**: Meta‑progression (currency between runs), unlockable upgrade pool, controller support, accessibility options.

## 15. Acceptance Criteria (MVP)
- Start overlay shows controls; clicking Start hides overlay and begins level 1.
- Formation spawns with level‑scaled rows/columns; enemies march, bounce, and drop.
- Enemies occasionally fire; bullets damage the player on hit; player has brief invulnerability after being hit; lives decrement and display updates.
- Clearing all enemies increments level and either spawns the next wave or presents a 3‑choice upgrade draft on levels divisible by 5.
- Upgrades apply immediately and reflect in HUD (e.g., gun count, DPS approximation).
- Pickups (scrap) sometimes drop on enemy death; collecting them increases score and displays a message.
- Game Over overlay appears when lives reach zero; Restart begins a fresh run with level 1.
- Touch buttons appear and are usable on small screens.


