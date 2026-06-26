# SIGNAL

**A minimalist network-coverage strategy game** (formerly "WATERSHED" — same
engine, clearer theme). One verb, one elegant mathematical engine, escalating
pressure — built deliberately so there is no single "solved" strategy.

Crowds of **devices** (warm dots) connect to the **nearest tower** you place.
Signal weakens with distance, so a device far from its tower **clogs** it —
its capacity is a service budget spent against *distance*. Park a tower on its
crowd and it serves cleanly; let the crowd drift away and load climbs until
the tower **congests** and drops connections, costing **uptime**. You have
**fewer towers than crowds**, so you're always triaging — keep the city
connected as demand keeps rising.

## Why it's built this way (the research)

After several prototypes that collapsed into a single dominant strategy, the
design was grounded in published work on game *depth*:

- **Depth ≠ complexity.** Adding rules/systems doesn't add depth (Lantz,
  Isaksen, Jaffe, Nealen & Togelius, *Depth in Strategic Games*, AAAI 2017).
- **Depth = a long "strategy ladder"** — a novice heuristic should be
  beatable by a slightly cleverer one, indefinitely. A game dies when "one
  weird trick" exploits a regularity to play near-perfectly (the
  tower-defense maze-and-chokepoint trap).
- **Tight coupling** — one state variable doing several jobs — buys depth
  without adding rules (Nealen, Saltsman & Boxerman, *Towards Minimalist
  Game Design*, FDG 2011).

WATERSHED applies this directly: the core is a **facility-location / nearest-
point partition** (k-means cost). It's genuinely hard to optimise, *globally
coupled* (move one well and every boundary shifts), and the demand **drifts**
so no static layout stays optimal — there is no dominant trick, only
ever-better reading of the board. One coupled variable (a well's **charge** =
capacity, reset when you move it) supplies the *adapt-vs-commit* trade-off.

Verified by simulation: a static "never move" player survives ~half as long
as one that follows the drift — so placement, not a hidden meter, is the game.

## How to play

- **Drag wells** around the field to re-divide it. Every move re-slices the
  whole map to whatever's nearest.
- **Moving unsettles a well** (capacity drops, then recharges over a few
  turns) — so move only where it counts.
- Each turn, demand **grows and new springs bloom**; next turn's growth is
  shown as faint **ghosts** before you commit. Plan for what's coming.
- Keep wells from flooding. Demand never stops rising — last as long as you
  can. (`Enter` / `Space` advances a turn.)

## Run / deploy

Single static file. Open `index.html`, or `python -m http.server 8000`.
GitHub Pages: push, then Settings → Pages → `main` / root (`.nojekyll`
included). Tunables live in the `CFG` object at the top of the `<script>`.

## Status

v0.1 prototype. The core mechanic is verified sound (placement-driven,
clear skill gap, escalating, no dominant strategy). Difficulty/feel tuning is
the open question — best judged by playing.

### Earlier prototypes in this repo

- `firewall.html` — a tower-defense × tactics game (collapsed into a single
  dominant maze-and-chokepoint strategy; the reason for the research pivot).
- `comet-court.html` — the original slingshot/gravity sumo prototype.

Both kept for reference; full history is in git.
