# WEB OF GOTHAM — a 20-second Spider-Man mini-game

A cinematic, third-person, 3D superhero mini-game that runs entirely in your browser.
No build step, no network needed — Three.js is vendored in `lib/`.

Rain hammers the neon district of Gotham. Spider-Man is perched on a rooftop beside
Batman, who warns that three armed criminals are escaping through the alley below.
You have **20 seconds** to leap off the roof, web-swing down the street, land in the
alley, and take all three down before they vanish. Batman glides in to help you
capture the last one.

## Play

Open `index.html` in any modern desktop browser (Chrome, Edge, Firefox, Safari)
and click **Start Mission**. A mouse is required (the game uses pointer lock).

If your browser blocks pointer lock or module scripts on `file://` URLs, serve the
folder instead:

```bash
npx serve .        # or: python3 -m http.server
```

then open the printed URL.

## Controls

| Input | Action |
| --- | --- |
| `W A S D` | Move / air control |
| Mouse | Look (over-the-shoulder camera) |
| `SPACE` | Leap off rooftop / jump / kick off a wall |
| Hold `LMB` (airborne) | Fire a web line and swing — release to fling |
| `LMB` (near an enemy) | Melee punch (lunges automatically) |
| `F` | Web attack — stuns a criminal for an easy finisher |
| `W` into a wall (airborne) | Wall-run |

**Fast route:** hold `SPACE` + `W` off the rooftop edge, then hold `LMB` to swing
down the street. Release at the bottom of the arc for a speed fling. In the alley,
tag a runner with `F`, then punch. A stunned criminal goes down in one hit.

## Features

- **20-second mission timer** with a fail state for timeouts and escapes
- **Web-swinging physics** — pendulum rope constraint with arc-bottom speed pumping,
  reel-in, and momentum-preserving release
- **Wall-running** and rooftop leaps with air control
- **Combat** — lunge punches, stunning web attacks, per-takedown slow-motion,
  and a Batman-assisted capture of the final criminal
- **Cinematics** — rooftop intro pan with Batman's briefing, cinematic side-camera
  on big falls, orbiting slow-mo finisher, and a rooftop outro overlooking the arrest
- **Living city** — rain (wind-sheared line streaks), drifting fog banks, storm
  clouds, lightning with thunder, flickering neon signs with fake wet-street
  reflections, moving traffic, street lamps, gothic tower crowns, water tanks,
  fire escapes, and an arriving GCPD cruiser with strobing lights
- **Destructible props** — trash cans and crates take impulses from combat hits
- **Procedural characters** — Spider-Man, Batman (with wind-simulated cloth cape),
  and three armed criminals, all animated in code (run cycles, swing pose, punches,
  glide, kneel, takedowns, web cocoons)
- **Synthesized audio** — rain loop, thunder, thwips, punches, whooshes, an
  urgency-scaling orchestral-style score, stingers, and a victory fanfare, all
  generated with the WebAudio API (no audio files)
- **Full HUD** — countdown, health bar, score + combo feed, criminals-left counter,
  screen-space objective marker with distance, tutorial controls, and subtitles

## Scoring

Points for swings, wall-runs, web hits, punches, and takedowns, plus end-of-mission
time and health bonuses. Faster and cleaner runs score higher.

## Tech

- [Three.js](https://threejs.org/) (r160, vendored in `lib/`) — rendering, PCF soft
  shadows, ACES tone mapping, PMREM environment for wet-surface reflections
- Custom character/physics/animation systems in a single `<script type="module">`
- No dependencies to install, nothing to build
