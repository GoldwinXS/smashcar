# THE PASS

**An AI cat-chef connection duel.** Place a dab of your sauce on any open
tile. **You** (cyan) win the instant your sauce forms one unbroken line from
the **left** edge to the **right**; the rival cat (orange) races to link
**top** to **bottom**. It can never end in a draw — once the board fills,
exactly one of you has crossed — so every tile you take also *blocks* the
rival. Attack and defence are the same move.

## Why this core (the research)

After two prototypes whose endgames collapsed to a Sprague–Grundy/Nim
**parity count** (a closed-form *shortcut* = "solved endgame", samey,
low replayability), a cited research pass pointed to the opposite kind of
math:

- **Connection games are PSPACE-complete** (Reisch 1981 for Hex; also
  Havannah, TwixT, Slither) — there is **no polynomial-time solution and no
  closed-form winning strategy**, so the whole board stays a fresh, hard
  problem every game. ([Hex is PSPACE-complete](https://academic.timwylie.com/17CSCI4341/hex_acta.pdf))
- Even though strategy-stealing *proves* a winner exists, **finding the move
  is itself PSPACE-hard** — knowing the winner exists does not trivialise play
  ([strategy-stealing is non-constructive, ITCS 2020](https://drops.dagstuhl.de/storage/00lipics/lipics-vol151-itcs2020/LIPIcs.ITCS.2020.21/LIPIcs.ITCS.2020.21.pdf)).
- The draw-free guarantee (the Hex theorem) means outcomes are always clean.

**Honesty about originality:** this is the **Hex/Y connection-game family** —
an obscure but real classic, not invented from scratch. The deepest *simple*
replayable games are a small, well-explored set; the research's clear answer
was "use a connection core," so this skins that proven core as a cat-chef
duel rather than pretending to be a novel mechanic.

## How to play

- Click any open tile to place your sauce. You connect **left↔right**.
- Leave **double-threats** (two ways to bridge a gap) — the rival can only
  block one.
- Board size selectable (6×6 → 9×9). You move first.

The AI is **flat Monte-Carlo** (random board completions always yield a unique
winner — ideal for Hex) with a small centre-opening bias. Verified: it beats
random play 8/8, ~20ms/move, and 0 draws across 200 random fills.

## Run / deploy

Single static file. `index.html`, or `python -m http.server 8000`.
GitHub Pages: push → Settings → Pages → `main` / root (`.nojekyll` included).

## Earlier prototypes in this repo (kept; full history in git)

- `simmer.html` — original "stir the pots" parity game (real depth but a
  solved-parity endgame → samey, the reason for this pivot).
- `linecook.html` — Dots & Boxes (fun + deep, but a known kids' game).
- `signal.html` — Voronoi coverage (greedy-solvable once towers ≥ crowds).
- `firewall.html` — tower-defense × tactics (maze+chokepoint dominant strategy).
- `comet-court.html` — slingshot/gravity sumo.
