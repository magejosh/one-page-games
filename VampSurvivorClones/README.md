## VampSurvivorClones

A one‑page, instantly playable bullet‑heaven/survivor‑style arcade game built in vanilla HTML5 Canvas. You pilot a dot that auto‑fires bullet streams while kiting waves of melee and ranged enemies. Survive, collect power‑ups, level up, and draft abilities to build silly synergies.

### Play
- Open `vampSclone03.html` in a modern desktop browser.
- Press Start. The game begins with an ability pick.

### Controls
- Move: Arrow Keys or WASD
- Abilities: Number keys 1–0 (actives on cooldown)
- Auto‑fires toward your last move direction

### Objective
- Survive as long as possible. Score by defeating enemies. HUD shows Score, Time, HP/Lives, Level/XP, Streams, and active buffs.

### Core Mechanics
- Auto‑fire bullet streams; add permanent extra streams (yellow) and temporary 4‑way streams (orange).
- Enemies: melee (triangles) chase; ranged (squares) shoot short‑life bullets.
- Damage & survivability: brief invulnerability after a hit; optional shield blocks; lives as continues. v03 adds HP/Max HP that scales on level‑up.
- Leveling (v02+): Gain XP from kills and draft one of three abilities at milestone levels.
- Difficulty scaling: v01/02 increase enemy speed and spawns periodically; v03 increases spawns periodically while enemy speed grows slowly per level.

### Power‑ups
- Fire Rate (green): Doubles fire rate briefly.
- Extra Life (purple): +1 life.
- Extra Stream (yellow): Adds a permanent offset stream.
- Temp Streams (orange): +4 streams briefly.
- Heal (v03): Restore a portion of HP.

### Abilities (examples)
- Passives: Piercing Shot, Ricochet, Double Tap, Exploding Monster, Shield, Magnet, Regeneration (stackable in v03; does not consume a hotkey).
- Actives: Freeze, Nuke, Dash, Turn Undead (mapped to 1–0, with cooldowns shown in the hotkey list).

### Iterations
- v01 — `vampSclone.html`: Core loop, melee/ranged enemies, auto‑fire, power‑ups, basic difficulty scaling, lives.
- v02 — `vampSclone02.html`: Leveling system, ability draft, hotkeys/cooldowns, magnet/shield/regen, XP bar and overlays.
- v03 — `vampSclone03.html`: HP/Max HP + heal orb, regen stacks (no hotkey slot), spawn‑only periodic scaling, refined HUD.

### Tech
- Single‑file HTML per iteration; Canvas 2D; no external assets; desktop Chrome/Edge/Firefox.
