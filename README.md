# SIMMER

**An original AI cat-chef duel.** Every pot on the stove has a **doneness**
number. **Stir** a pot and it — plus its four orthogonal neighbours — each
drop by one. Any pot that hits exactly **0** is **plated** in your colour.
One stir per turn; when the stove empties, the most dishes wins. The Capybara
of Indifference judges, unmoved.

This one is **not a reskin of a known game** — the stir-the-pots mechanic is
invented for this prototype (the previous build, LINE COOK, was fun but was
Dots & Boxes with a hat on).

## The design, and how it was verified

Built to the formula: a **math concept as the core**, a **fresh genre
mashup** (cooking × territory strategy), themed with the **top internet
obsessions** of 2026 (AI + cats + cooking — the viral "AI cooking-cat" trend
— plus the Capybara of Indifference).

The core is a **combinatorial game**: adversarial, perfect information, and —
crucially — **greedy is a losing strategy**. Because stirring nudges five
pots toward 0 *for whoever stirs next*, leaving a pot on "1" hands the rival a
free dish, so the game is a parity/denial battle, not a grab-fest. Verified in
simulation **before** building: removing "stir again" was the key (a go-again
rule made greedy optimal and the first player snowball). A pure-greedy player
loses ~75% to a lookahead player, and the shipped AI beat greedy **6–0** in
full games.

Honest note: SIMMER has *real* strategic depth but is not as brutally
greedy-proof as a century-refined classic — that's the genuine tradeoff of
inventing a mechanic vs. skinning a known-deep one.

## How to play

- Click any cooking pot to **stir** it (the plus-shaped pulse is previewed on
  hover; pots that would plate glow green). Then the rival cat stirs.
- Aim for **multi-plates** (stir where several pots are on 1) and avoid
  nudging pots down to 1 right in front of the rival.
- Stove size is selectable (4×4 → 6×6). You move first.

The AI is a depth-adaptive negamax (alpha-beta) on plate differential.

## Run / deploy

Single static file. `index.html`, or `python -m http.server 8000`.
GitHub Pages: push → Settings → Pages → `main` / root (`.nojekyll` included).
Tunables (sizes, AI depth) are near the top of the `<script>`.

## Earlier prototypes in this repo (kept; full history in git)

- `linecook.html` — Dots & Boxes core (fun + provably deep, but a known game).
- `signal.html` — Voronoi network-coverage (solvable once towers ≥ crowds).
- `firewall.html` — tower-defense × tactics (maze+chokepoint dominant strategy).
- `comet-court.html` — slingshot/gravity sumo.
