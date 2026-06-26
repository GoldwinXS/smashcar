# FIREWALL

**Tower-defense × tactics chess, with perfect information.** A browser
strategy prototype where every threat is telegraphed — you win or lose on
your decisions, not your reflexes.

Viruses cross a circuit grid toward your **core** on the right. Each one
shows exactly where it will move next, so every turn is a planning puzzle:
place programs, funnel the swarm into kill-zones, manage energy, and hold
the line for 8 waves.

## The mashup

A fresh two-genre combo built specifically for **strategy and planning**:

- **Tower Defense** — waves advance toward a core you must protect; you
  place defenses to stop them.
- **Grid tactics (chess-like)** — programs have distinct attack/blocking
  *patterns*, and positioning is everything.
- **Perfect-information telegraphing** (the *Into the Breach* idea) — you
  see every enemy's next move before you commit, so losses are fair and
  every turn is a solvable puzzle.

## How to play

Each turn you **plan**, then **Execute**. On execute: your programs fire
first, then every virus advances one step along its arrow.

Programs (cost in energy):

- **Wall (1)** — blocks movement (2 HP). Reroutes the swarm; chewed through if you fully seal a lane.
- **Zap (2)** — hits the 4 orthogonal neighbours for 1 each turn. Great on chokepoints.
- **Beam (3)** — fires right along its whole row for 1. Mows a lane.
- **Nova (5)** — hits all 8 surrounding tiles for 2. An expensive kill-zone.
- **Mine (2)** — detonates when a virus steps on it: 3 damage to that tile + neighbours, then gone.

You gain energy each wave and can **Recycle** programs to adapt — full
refund if placed this turn, 50% otherwise. Place and recycle freely while
planning; nothing locks until you Execute.

Controls: click a tool then click a tile (mouse or touch). Keys `1`–`5`
pick tools, `R` recycles, `Enter`/`Space` executes the turn.

## Run it locally

Single static file — open `index.html`, or serve it:

```bash
python -m http.server 8000   # then visit http://localhost:8000
```

## Deploy to GitHub Pages

No build step. Push, then **Settings → Pages → Deploy from a branch →
`main` / root**. The `.nojekyll` file keeps Pages serving everything as-is.
Lives at `https://<user>.github.io/<repo>/`.

## Status

v0.1 prototype, fully playable through 8 waves. Verified by simulation:
doing nothing loses the core; a reasonable strategy clears all waves.
Tunables (wave composition, costs, energy, core HP) live in the constants
at the top of the `<script>`.

### Ideas to explore next

- More program/virus types (splitters, shielded viruses, slow fields).
- A roguelike-lite draft: pick a new program or upgrade between waves.
- Smarter difficulty curve + an endless mode with a score leaderboard.
- Sound and juicier resolve animations.

## Also in this repo

- `comet-court.html` — the earlier prototype (slingshot/gravity sumo)
  this project started as, kept for reference. Its history is in git.
