## Product Requirements Document — VampSurvivorClones

### 1) Vision
Create a one‑page, instantly playable survivor/bullet‑heaven with satisfying auto‑fire, readable upgrades, and escalating pressure. Keep scope tight: a clean canvas arena, a handful of enemy types, a compact power‑up set, and a small but expressive ability draft system.

### 2) Goals & Non‑Goals
- Goals
  - Deliver a complete arcade loop in a single HTML file (no external assets).
  - Make survivability and build choices readable (HP/lives, clear buffs, concise HUD).
  - Provide meaningful build variety via a small set of passives/actives with synergies.
  - Ensure runs are short and replayable (5–15 minutes), with immediate “time‑to‑fun”.
- Non‑Goals
  - Deep meta‑progression, save/load, or roguelite unlock trees (initial scope).
  - Multiplayer or networked leaderboards.
  - Complex content pipelines (sprites, audio libraries) beyond minimal effects.

### 3) Target Audience
- Fans of Vampire Survivors/bullet‑heaven games who want a quick in‑browser run.
- Game jam and web toy enthusiasts; devs seeking compact reference implementations.

### 4) Core Gameplay Loop
1. Move to kite enemies; auto‑fire bullet streams in last move direction.
2. Defeat enemies → gain score and XP → collect periodic power‑ups.
3. Level up → draft abilities (actives/passives) at milestone levels.
4. Survive increasing waves; chase synergies; push personal best.

### 5) Feature Set (MVP → Polished)
- MVP (v01)
  - Player movement + auto‑fire streams; melee and ranged enemies.
  - Power‑ups: Fire Rate, Extra Life, Extra Stream, Temp Streams.
  - Lives and brief post‑hit invulnerability; basic difficulty scaling (speed + spawns).
  - Minimal HUD (score, time, lives, streams/buffs).
- Polished (v02)
  - Leveling/XP, milestone ability draft UI (overlay), hotkeys 1–0 with cooldowns.
  - Abilities: Piercing Shot, Ricochet, Double Tap, Exploding Monster, Freeze, Nuke, Dash, Turn Undead; Magnet, Shield, Regeneration.
  - Expanded HUD (level, XP bar) and ability list panel.
  - Tuning pass on spawn/speed scaling.
- Polished+ (v03)
  - HP/Max HP system; level‑up increases Max HP and fully heals.
  - Heal orb power‑up; Regeneration stacks and does not occupy a hotkey slot.
  - Periodic scaling focuses on spawn rate; enemy base speed increases slowly per level.
  - Refined HUD: HP bar, XP bar, timers for buffs.

### 6) Systems Detail
- Player & Combat
  - Auto‑fire bursts aim at last move direction; permanent extra streams (yellow) and temporary 4‑way streams (orange) increase coverage.
  - Bullet stats can gain pierce, ricochet, double‑tap burst, and on‑kill explosions via abilities.
  - Survivability: HP and lives; brief invulnerability after damage; optional Shield periodically blocks one hit; Dash grants brief invuln burst.
- Enemies
  - Melee (triangles) home toward player; Ranged (squares) fire short‑life bullets.
  - Spawn from screen edges; spawn interval decreases over time.
  - Scaling: periodic spawn acceleration; in v03, base speed increases slightly on level‑ups (no periodic speed spikes).
- Power‑Ups
  - Fire Rate (temporary), Extra Life, Extra Stream (permanent offset), Temp Streams (temporary +4 streams), Heal orb (restore a portion of HP).
  - Magnet (ability) increases pickup attraction when nearby.
- Abilities
  - Actives: Freeze (2s global freeze, ~15s CD), Nuke (clear screen, ~45s CD), Dash (short invuln dash, ~5s CD), Turn Undead (next bullet‑kill converts to suicide strike vs nearest).
  - Passives: Piercing Shot (+1 pierce), Ricochet (bounces once), Double Tap (second burst), Exploding Monster (on‑kill radial shots), Shield (periodic block), Magnet (pull power‑ups), Regeneration (+HP over time; stackable).
  - Hotkeys 1–0; cooldowns displayed in the ability list; Regeneration does not consume a hotkey slot (v03).
- Leveling
  - XP per kill; progressive thresholds (piecewise linear: 10×lv → 25×lv → 50×lv → …); milestone levels trigger ability draft overlay.
  - On level‑up: increase Max HP by 1 and fully heal (v03); slight enemy base‑speed increase.
- HUD & UI
  - Score, Time, Lives; HP bar; Level and XP bar; Streams count; timers for Fire Rate and Temp Streams; ability hotkey list with cooldowns.

### 7) UX & Controls
- Arrow keys or WASD to move; 1–0 to trigger actives; game auto‑fires.
- Overlays: Start screen; Level‑up ability draft.
- Clear colors and shapes: player (blue), melee (red triangles), ranged (orange squares), power‑ups by color.

### 8) Technical Requirements
- Single HTML file; no external dependencies; Canvas 2D; minimal per‑frame allocations.
- Works in latest desktop Chrome/Edge/Firefox; 60 FPS target on typical laptops.

### 9) Success Metrics
- Time‑to‑fun < 10 seconds from page load.
- Average run length 5–15 minutes; >70% of players reach at least one level‑up.
- Stable 60 FPS on mid‑range hardware at 1080p.
- Clear progression signals: players can list at least two synergistic combos after a run.

### 10) Milestones
- M0 (done): Core loop with power‑ups, melee/ranged enemies, lives (v01).
- M1 (done): Leveling + ability draft, actives/passives, HUD/overlay (v02).
- M2 (done): HP/Max HP, heal orb, regen stacks, revised scaling and HUD (v03).
- M3 (next):
  - Enemy variety pass (tank, splitter, charger); elite variants.
  - Boss/elite wave at time thresholds; light telegraphs.
  - Audio cues (web‑safe beeps) with mute toggle; screen shake options.
  - Accessibility: color‑blind friendly palette toggle; larger UI scale option.
- M4 (stretch):
  - Minimal meta‑progression (cosmetic badges, session stats, local bests).
  - Seed entry for reproducible runs; difficulty presets.

### 11) Open Questions / Risks
- Balance of ability synergies (Double Tap + Piercing + Exploding Monster) and regen stacking pacing.
- Readability under heavy ricochet/explosion scenarios; potential need for culling/rate limits.
- Spawn scaling vs player mobility—kiting edges could trivialize some waves.
- Input on mobile/touch (out of scope initially) and keyboard‑only accessibility considerations.
