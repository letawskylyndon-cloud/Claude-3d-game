# Dusk Pit

A 3D arena brawler that runs in the browser. You are a lone knight in a gladiator pit at dusk,
fighting waves of grunts, brutes, archers and, every fifth wave, the Gilded Brute.

Everything lives in one self-contained file, `index.html`: open it directly from disk or serve it
statically. It loads Three.js r128 from cdnjs; all models, textures and sounds are generated at runtime.

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

## Tuning

Every gameplay value (speeds, damage, health, attack timings, ranges, arcs, cooldowns, wave sizes,
scaling, colours) sits in the `CONFIG` object at the top of the script, grouped by system and
commented with units. Durations are in seconds.
