# SMASHCAR

**Car-ball carnage.** Rocket-powered trucks, one giant ball, two goals — and
full-contact demolition. Smash the ball into the enemy net. Smash the enemy
while you're at it. First to **5 goals** wins. Nobody falls off, nobody's
eliminated.

Built as a single self-contained HTML file with [Three.js](https://threejs.org)
(rendering) and [Rapier](https://rapier.rs) (physics), loaded from CDNs — no
build step, no install.

## Play

- **Local / vs bots:** open the site (or `wreck.html`) and hit **PLAY** — bots fill the empty seats.
- **Online with friends:** **Host online** to get a **4-digit code**; your friend picks **Join** and types it. Pure peer-to-peer WebRTC over free cloud signaling — no server to run. Bots fill any empty seats.

### Controls
- **Drive** W/S · **Steer** A/D · **Boost** Shift · **Jump** Space (again in air = flip-dodge) · **Flip upright** R · **Mute** M
- **Phone:** hold the left pad to drive, slide to steer, pull down to reverse; right-side **BOOST / JUMP / FLIP**.

### What makes it SMASHCAR (not just car soccer)
- **Damage is real & physical** — hits crush visible dents into the bodywork, tear off bumpers and wheels, and the collision shape itself deforms. A battered truck is slower and pulls to one side (but always drivable). Everyone gets a fresh truck at each kickoff.
- **HOT BALL** — hard strikes heat the ball up; a white-hot ball *wrecks* whatever it slams into. Playing the ball is always safe — standing in front of a screamer is not. Goals cool it off.
- **Powerup pads** — grab **REPAIR** (heal), **OVERDRIVE** (raw speed), or **SHIELD** (bolts armor plates all around your truck that soak hits and shear off when cracked).
- **BATTLEFIELD PITCH** — demolitions and mega-shots blast craters into the floor, and slams dent the boundary. Late-game is played on the wreckage.
- **Demolition = power play** — grind a truck to 0% hull and it's gone for 3 seconds while you attack the open net. It always comes back.

Procedural EDM soundtrack and a reactive synthesized crowd, all generated in the browser — no audio files.

## Run locally

Any static file server, e.g.:

```
python -m http.server 8112
```

then open http://localhost:8112/ (the root redirects to the game).

## Deploy (GitHub Pages)

Static site — Pages just works. Push, then **Settings → Pages → Deploy from a
branch → `master` / root**. The site root redirects to the game. (`.nojekyll`
is included.)

## Repo notes

- `wreck.html` — **the game** (iterated through v1…v18).
- `index.html` — redirect so the site root lands on the game.
- `wreck-sumo-v7.html` — the earlier "sumo ring-out" era, before the soccer pivot.
- `the-pass.html` and the other `*.html` files — earlier unrelated game prototypes, kept for history.
