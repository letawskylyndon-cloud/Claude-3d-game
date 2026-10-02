# Dusk Pit

A 3D arena brawler that runs in the browser. You are a lone knight in a gladiator pit at dusk,
fighting waves of grunts, brutes, archers and, every fifth wave, the Gilded Brute.

Everything lives in one self-contained file, `index.html`: open it directly from disk or serve it
statically. It loads Three.js r128 from cdnjs; all models, textures and sounds are generated at runtime.

## Running on a low-end or school laptop

1. Download `index.html` **and** `three.min.js` into the same folder. The game uses the local
   `three.min.js` whenever the CDN is blocked or there is no internet.
2. Double-click `index.html` to open it in Chrome or Edge. Plug the laptop in, because battery
   saver throttles the GPU.

Graphics adapt to the machine automatically:

- **Auto-detected quality.** Integrated Intel graphics (e.g. Celeron / UHD 600) start on **Low**:
  no shadow pass (soft blob shadows instead), no torch point lights, cheaper per-vertex shading,
  fewer particles, no anti-aliasing and a capped resolution.
- **Dynamic resolution.** If the frame rate drops below 50 fps the game lowers its render
  resolution, and it raises it again when there is headroom.
- **Manual override.** The **GRAPHICS** button on the title screen cycles Auto / Low / Medium /
  High (the page reloads to apply it). Press **F** in game to show the frame rate.

## Controls

| Input | Action |
| --- | --- |
| W A S D | Move (relative to the camera) |
| Mouse | Orbit the camera (click the game to capture the pointer) |
| Left click | Light attack, press three times for a combo finisher |
| Right click | Heavy attack, a charged 200° sweep |
| Space | Dodge roll, invincible early in the roll |
| Q / E | Rotate the camera (fallback when the pointer can't be captured) |
| Esc / P | Pause |
| M | Mute |
| F | Show frame rate, quality and render resolution |

## Tuning

Every gameplay value (speeds, damage, health, attack timings, ranges, arcs, cooldowns, wave sizes,
scaling, colours) sits in the `CONFIG` object at the top of the script, grouped by system and
commented with units. Durations are in seconds. The graphics presets live in `CONFIG.graphics`.
