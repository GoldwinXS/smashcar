# Comet Court

**Mini-golf × Sumo, played in orbit.** A quick, fun browser prototype.

Slingshot your comet, let gravity wells bend the shot, and bump every rival
out of the shrinking ring. Last comet standing wins the round.

## The mashup

The brief was a "Rocket League move" — bolt together two genres nobody usually
combines. The top 5 concepts became the game's pillars:

1. **Orbital gravity / slingshot physics** — gravity wells curve every shot.
2. **Mini-golf** — one flick per turn: aim, set power, read the curve.
3. **Sumo / king-of-the-hill** — knock rivals out of a ring that tightens each round.
4. **Roguelike-lite** — pick one stacking perk before each match.
5. **Arcade combo multiplier** — chain knockouts in a single shot for escalating score.

## Controls

- **Aim:** press and drag *back* from your (cyan, ringed) comet, then release —
  like a slingshot. Pull farther for more power.
- **Read the curve:** the dotted preview shows your path through gravity.
- **Win the round:** be the last comet inside the ring.

Works with mouse or touch.

## Run it locally

It's a single static file — just open `index.html` in a browser.

For a clean local server (avoids any future fetch/CORS quirks):

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

No build step. Push to GitHub, then in the repo:

1. **Settings → Pages**
2. **Source:** *Deploy from a branch*
3. **Branch:** `main`, folder `/ (root)` → **Save**

The site goes live at `https://<user>.github.io/<repo>/`.
The included `.nojekyll` file tells Pages to serve everything as-is.

## Status

v0.1 prototype — core loop is playable end to end. Tunables live in the `CFG`
object at the top of the `<script>` in `index.html`.

### Ideas to explore next

- Sound (launch whoosh, knockout thump, combo chime).
- More perks + an enemy/perk-draft for the AI too.
- Smarter AI that banks shots off gravity wells on purpose.
- Online or hotseat 2-player.
- Per-round hazards: moving wells, a black hole, bumpers.
