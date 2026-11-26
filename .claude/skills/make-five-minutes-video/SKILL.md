---
name: make-five-minutes-video
description: Use when making a new story video in the style of "The Five Extra Minutes" - 2D art with a depth camera that looks 3D, and several expressive character voices.
---

# Make a video like "The Five Extra Minutes"

This project is the finished example. Copy it for a new story: `python studio.py new <slug>` creates `runs/<slug>/`.
Run `python setup.py` once first, then use the `.venv` Python. `new` copies the example's files, so replace them.

Use `fable-script`, `fable-animation`, `fable-sound` and `reference-study` for craft.
Where they differ from this file (single narrator, flat stage, original example), follow this file.

## Look
- Flat 2D canvas art projected through a camera (`art/drawing.js`): `pr`, `board`, `quad`, `box`, `shadow`.
- World units: z=500 is 1:1 on screen, larger z is farther away, floor is y=190.
- Layer foreground, characters and background. Use `soft()` for depth blur, light shafts and floating motes.
- Move the camera (`cam.x`, `cam.y`, `cam.z`) so the layers shift against each other.
- Characters are in `art/actors.js`; sets and shots are in `art/scenes.js`.

## Voices
`CAST` in `studio/voice.py` maps each character to a Kokoro voice or blend (full model).
Each line in `episode/script.json` has `parts` with `who`, `text`, `speed`, `pitch`, `gain` and `pause`.
Change pace and pauses with the emotion. Keep each character's voice the same throughout.

## Steps
1. Write the story. Edit `episode/script.json` and `episode/film.json`.
2. `python studio.py voice`. If a take's word groups do not match, add a `labels` list, or captions are only estimated.
3. Draw one entry in `art/scenes.js` for each script id. Time actions to spoken words.
4. Update `episode/sound.json`: `quiet_from`, `quiet_until` and cues `[scene id, spoken word, sound, gain, position]`.
5. `python studio.py mix`, then check single frames: `python studio/render.py --poster 12.5` (writes `output/frame.jpg`).
6. `python studio.py render`, then `python studio.py verify`. Verify also writes the subtitle file.
7. Look at frames from the finished video. Ask the user to listen to the voices.
