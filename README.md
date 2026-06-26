# LINE COOK

**An AI cat-chef duel where the greedy move is a trap.** You and a rival AI
cat draw counters on a shared kitchen grid; close all four walls of a station
to claim its dish — **and cook again**. Most dishes wins. The Capybara of
Indifference judges, unmoved.

## The formula (and why this one works)

Built to a specific recipe, and tuned to fix the flaw that solved every
earlier prototype here (a greedy heuristic always wins a coverage game):

- **Math concept as the core:** **combinatorial game theory** — the
  chain-and-parity mathematics of *Dots & Boxes* (Berlekamp's theory). The
  obvious greedy play ("take every free dish") is *provably* a trap, and the
  game is **adversarial**, so no fixed routine can solve it. Verified: a
  greedy bot loses **15/15** to the AI, by huge margins (e.g. 1–24); two equal
  AIs split ~6–4.
- **Genre mashup:** competitive **cooking-show** × **abstract territory duel**.
- **Theme — 2026's biggest internet obsessions:** AI + cats + cooking (the
  viral "AI cooking-cat" trend), with the Capybara of Indifference as judge.

## How to play

- Click an empty edge between two dots to draw a **counter**.
- Drawing a station's **4th** wall claims its dish (your colour) and gives you
  **another move** — claims can chain.
- Drawing a station's **3rd** wall hands your rival a free dish. When you have
  no safe move, give away the **smallest** run. The expert move is the
  **double-cross**: sacrifice two dishes to force your rival to open the next
  big chain. Master that and you beat the AI.
- Grid size is selectable (4×4 quick → 6×6 long).

## Run / deploy

Single static file. Open `index.html` or `python -m http.server 8000`.
GitHub Pages: push → Settings → Pages → `main` / root (`.nojekyll` included).
Board/AI tunables live near the top of the `<script>`.

## Status

v0.1 prototype, fully playable vs the AI. The AI plays "safe moves, then
minimise the sacrifice"; it does **not** yet do the expert double-cross —
which is deliberately the player's path to mastery. A stronger
(double-crossing) AI and difficulty levels are the obvious next step.

### Earlier prototypes in this repo (kept for reference; full history in git)

- `signal.html` — network-coverage / Voronoi strategy (solvable once towers ≥ crowds).
- `firewall.html` — tower-defense × tactics (collapsed to a maze+chokepoint trick).
- `comet-court.html` — slingshot/gravity sumo.
