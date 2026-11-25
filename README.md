# WHITE NOISE — Field Build 0.5.0

A compact first-person winter psychological thriller set in northern Maine, December 14, 2004. The build is designed as a small, dense place to inhabit: a timber ranger cabin, a short black-spruce trail, a sea lookout, and a cramped storage cellar beneath the cabin.

## Run locally

1. Extract the ZIP.
2. Open a terminal in the extracted project folder.
3. Run `python -m http.server 8000` (or double-click `START_GAME.bat` on Windows).
4. Open `http://localhost:8000` in a modern browser.

Do not use `file://` for launch. The app uses ES modules and fetches Three.js from a pinned CDN URL.

## Publish with GitHub Pages

GitHub Pages does not unpack ZIP archives. Extract the ZIP and upload the **contents of this folder** to the repository root. `index.html` must sit directly beside `src/` and `assets/`.

In GitHub open **Settings → Pages → Deploy from a branch → main → /(root) → Save**.

## Controls

### Keyboard and mouse

- `W A S D` — move.
- Mouse — look around; click the game to capture the pointer.
- `E` — interact / inspect.
- `F` — toggle the field lantern after collecting it.
- `Shift` — move faster.
- `Esc` — pause and release the pointer.
- The Controls menu allows movement, interaction, lantern and run keys to be rebound. If two actions are assigned to the same key, they swap.

### Touchscreen

- Play in landscape orientation.
- Left virtual stick — move.
- Drag the right side of the screen — look.
- `USE` — interact.
- `LAMP` — toggle the lantern after collecting it.
- `RUN` — move faster while held.

## Main route

1. Inspect and tune the shortwave receiver to **103.2 MHz**; press LISTEN.
2. Open the front door and go outside to the splitting block beside the porch.
3. Interact with the block three times to prepare the firewood. The brief stylized tool animation, wood chips and sound provide feedback.
4. Return inside, take the split logs from the stack and add them to the iron stove.
5. Follow the snow path toward the sea lookout. A deer may be seen among the trees; interact with it or observe it from a distance.
6. Look out over the water. When the light changes, return to the cabin.
7. Open the floor hatch and descend to the compact storage cellar. Find and collect the cassette marked **WHITE NOISE**.
8. Climb back up, tune the receiver to 103.2 MHz again and switch on the porch light.
9. Wait near the warmth of the cabin. The distant figure is an ambiguous, non-graphic story encounter.
10. Return to the radio and listen to the final recording.

## Interactive elements

Radio and frequency dial, front door, firewood splitting block, firewood stack, iron stove, mug, folded note, photograph, coastal map, field lantern, porch light switch, cellar hatch, cassette recorder, cassette, cellar ladder, deer and sea lookout. The old ranger equipment rack is atmospheric set dressing rather than a combat system.

## Files

- `index.html` — menu, HUD, settings, controls, radio interface and boot loader.
- `src/game.js` — Three.js scene, environment, interaction system, movement, sound and story state.
- `src/style.css` — menu, HUD, settings, touch controls and responsive layout.
- `assets/white_noise_ambient.mp3` — original ambient loop included locally.
- `START_GAME.bat` — Windows local HTTP server launcher.
- `BUILD_REPORT.md` — checks performed and limitations.

## Technical notes

- Three.js is pinned to **0.160.0** (jsDelivr with unpkg fallback).
- Procedural geometry and canvas textures are used; no external model or texture files are needed.
- Renderer pixel ratio is capped. Dynamic shadow maps are enabled only in High quality on non-touch devices.
- Story flags, settings, rebinding and player position are saved through `localStorage` when available.
- The game needs an internet connection at launch to fetch Three.js. The ambient track and game source are local.
- The night encounter is psychological and non-graphic. Ranger equipment is included as environmental props; no realistic weapon-use or injury simulation is implemented.
