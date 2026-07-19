# Prompt

The prompt that produced this project (game + trailer), recorded verbatim.

## 1. The game — `index.html`

> Create a polished, realistic 3D third-person superhero mini-game lasting exactly 20 seconds.
>
> The player controls Spider-Man on a rainy night in Gotham City. Use cinematic, realistic graphics, detailed wet streets, gothic skyscrapers, neon signs, fog, moving traffic, police lights, reflections, wind, and dramatic storm clouds.
>
> Spider-Man begins perched on a rooftop beside Batman. Batman warns him that armed criminals are escaping through an alley below. The player must leap from the rooftop, web-swing between buildings, dodge obstacles, land in the alley, and stop three criminals before the timer reaches zero.
>
> Include smooth web-swinging physics, wall-running, jumping, web attacks, melee combat, slow-motion finishers, realistic cloth movement, impact effects, environmental destruction, and responsive controls.
>
> Use an over-the-shoulder camera that becomes cinematic during major jumps and combat finishers. Batman should glide into the final scene and help capture the last criminal.
>
> Display a countdown timer, health bar, objective marker, tutorial controls, sound effects, dramatic orchestral music, and the objective: "Stop the escape."
>
> End with Spider-Man and Batman standing on a rooftop overlooking Gotham while police arrest the criminals. Show "Mission Complete" and the final score.
>
> Target smooth 60 FPS, realistic lighting, high-quality animations, clear collision detection, and immediately playable gameplay. Keep the entire experience fast, exciting, understandable, and completable within 20 seconds.

## 2. The trailer — `web-of-gotham-trailer.mp4`

> want it as a 30 seconds video with a voice over too

### How the trailer was produced

- A scripted playthrough of the game was recorded headlessly (Chromium + Playwright),
  stepped frame-by-frame at 24 fps for smooth footage regardless of render speed.
- Voiceover: six narration lines synthesized with espeak-ng, post-processed with
  pitch-down, EQ, and reverb, and synced to the recorded phase timestamps.
- Music: the game's orchestral score recreated offline as a 30-second WAV
  (Dm drone, timpani heartbeat, rising ostinato, finale fanfare) plus rain and thunder.
- Mixed and encoded with ffmpeg (H.264/AAC, 1280x720, exactly 30.000 s), with
  sidechain ducking so the music dips under the narration.

### Voiceover script

1. "Gotham. Midnight. Three armed men make their run."
2. "Spider-Man answers. Twenty seconds on the clock."
3. "He dives through the neon canyons,"
4. "drops into the alley. Webs. Fists. Takedowns."
5. "The Dark Knight glides in to end it."
6. "Mission complete. Web of Gotham. Play it in your browser."
