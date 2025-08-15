## Aether Empires (aka "Aether Raiders")

Neon‑tinged, one‑page 4X set among hyperlanes. Grow colonies, research techs, enact policies, and win by science (Ascension Gate) or domination. The folder name is `aether_raiders`, while the in‑game title is "Aether Empires" — both refer to the same project.

### Play the builds
- `aether_raiders.html`: Real‑time 4X mini with simple UI and a hero ability (Chrono Surge). Science victory implemented; conquest is emergent.
- `aether_raiders02.html`: Adds zoom/pan camera, optional Turn Mode toggle, a colony management panel, and local policy overrides.
- `aether_raiders03.html`: Pure turn‑based flow with a start/setup screen (AI count, map size, turn length, species selection), colony Focus, and species perks.

### Core features (across iterations)
- **4X on a canvas**: Procedural galaxy with ~36–68 stars, hyperlane routes, range‑limited movement.
- **Colonies**: Pop/Prod/Research stats; per‑colony stockpiles; ship build queue; Ascension Gate project.
- **Ships**: Scout, Colony, Frigate. Travel between stars; simple all‑vs‑all skirmishes at destinations.
- **Tech**: Warp Drives, Coherent Lasers, Phase Shields, Assembly Drones, Bioforming, Ascension Theory (unlocks Gate).
- **Policies**: Government, Economy, Values categories; apply global bonuses. Local overrides (02/03) for small per‑colony boosts.
- **Species (03)**: Humans, Optic Seraph, Glacial Myriad, Nomad Synths; each with distinct perks.
- **Victory**: Science victory implemented via completing the Ascension Gate; domination via conquest is supported by combat/ownership flipping, but not yet formalized with an explicit check.

### Controls
- `aether_raiders.html` (RTS):
  - Space = pause • R = research • P = policies • H = help
  - Click a star to select; pick a ship from the bottom bar, then click a destination in range

- `aether_raiders02.html` (RTS + optional turns):
  - Wheel = zoom • Right‑drag = pan • T = toggle turn mode • E = end turn • 0 = reset camera
  - Same selection and ship‑move flow as above, plus "Manage" to open the colony panel

- `aether_raiders03.html` (Turn‑based):
  - Wheel = zoom • Right‑drag = pan • E = end turn • R/P = research/policies • 0 = reset camera
  - Start screen lets you choose AI count, map size, turn length, and species

### How to run
Open any of the HTML files in a modern desktop browser (Chrome/Edge/Firefox). No build step or assets required.

### Notable iteration changes
- 01 → 02: Camera/zoom, optional Turn Mode, colony management, local policy overrides, enhanced research/policy UIs.
- 02 → 03: Full turn‑based flow with pre‑game setup, species perks, and colony focus (Balanced/Production/Research/Growth).

### Tech notes
- Single‑file HTML + inline JS using Canvas 2D; no external deps.
- DPI‑aware rendering (caps DPR at 2 for perf).


