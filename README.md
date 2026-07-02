# WRECKBALL

**Car-ball carnage.** Rocket-powered trucks, one giant ball, two goals — and
full-contact demolition. Smash the ball into the enemy net. Smash the enemy
while you're at it. First to **5 goals** wins. Nobody falls off, nobody's
eliminated.

Built as a single self-contained HTML file with [Three.js](https://threejs.org)
(rendering) and [Rapier](https://rapier.rs) (physics), loaded from CDNs — no
build step, no install.

## Play

- **Local / vs bots:** open `wreck.html` (or just the site root) and hit **PLAY** — bots fill the empty seats.
- **Online with friends:** **Host online** → generate an invite code → send it → paste their reply back. Pure peer-to-peer WebRTC, **no server**. Bots fill any remaining seats.

### Controls
- **Drive** W/S · **Steer** A/D · **Boost** Shift · **Jump** Space (again in air = flip-dodge) · **Flip upright** R · **Mute** M
- **Phone:** hold the left pad to drive, slide to steer, pull down to reverse; right-side **BOOST / JUMP / FLIP**.

### What makes it WRECKBALL (not just car soccer)
- **Damage is real & physical** — hits crush visible dents into the bodywork, tear off bumpers and wheels (a lost wheel makes you sag and pull), and the collision shape itself deforms. A battered truck is slower and harder to steer.
- 🔥 **HOT BALL** — hard strikes heat the ball up; a white-hot ball *wrecks* whatever it slams into. Playing the ball is always safe — standing in front of a screamer is not. Goals cool it off.
- 🛡️ **WAR RIGS** — beaten trucks patch their hull with glowing **salvage**; healthy ones *bolt it on as armor* (heavier rams, plates that shear off when cracked).
- 💥 **BATTLEFIELD PITCH** — demolitions and mega-shots blast craters into the floor. Late-game is played on the wreckage.
- **Demolition = power play** — grind a truck to 0% hull and it's gone for 3 seconds while you attack the open net. It always comes back.

## Run locally

Any static file server, e.g.:

```
python -m http.server 8112
```

then open http://localhost:8112/ (or http://localhost:8112/wreck.html).

## Deploy (GitHub Pages)

It's a static site, so Pages just works. Push the repo, then **Settings → Pages
→ Source: Deploy from a branch → `master` / root**. The site root redirects to
the game. (`.nojekyll` is included so nothing is filtered.)

## Repo notes

- `wreck.html` — **the game** (the version you play; iterated as v1…v13).
- `index.html` — redirect to `wreck.html` so the site root lands on the game.
- `wreck-sumo-v7.html` — the earlier "sumo ring-out" era of WRECK, before the soccer pivot.
- `the-pass.html` and the other `*.html` files — earlier unrelated game prototypes, kept for history.
