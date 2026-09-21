# Sandsong — Sanctuary of the Ten Winds

A chill pseudo-3D desert music exploration game inspired by *Journey*. Explore a walled canyon shrine, find ten hidden instruments, and build a layered song that ends in a complete chord progression. Pick your language on the title screen — **English or 中文** — and the whole game follows.

**Single file. No libraries. No external assets.** All visuals are HTML5 Canvas; all sound is synthesized in real time with the Web Audio API.

## Play

**Play in your browser:** [annabelleonardi.github.io/desert-instrument-collection](https://annabelleonardi.github.io/desert-instrument-collection/)

Or run locally:

```bash
python3 -m http.server 8734
# then visit http://127.0.0.1:8734
```

Click anywhere (or press Space) to begin.

## Controls

| Input | Action |
|-------|--------|
| **W / A / S / D** or **Arrow keys** | Move |
| **Q / E** or **drag mouse** | Look around |
| **Space** | Sing (awakens nearby instruments, echoes hidden ones) |
| **C** | Toggle the stone compass (sound-first guidance by default) |
| **Escape** | Step away from an instrument's trial |
| **M** | Toggle audio on/off |

## Gameplay

You are the last songkeeper of an abandoned canyon shrine. Ten instrument-spirits — a lyre, flute, drums, oud, bells, harp, shaker, horn, deep drum, and choir stone — are scattered among the ruins. Each one holds a voice of the sanctuary's song.

- **Explore** the enclosed canyon: boulders, broken pillars, and arches form alcoves where instruments hide. A short action-gated tutorial and a golden guide marker lead you to the first voice.
- **Listen** for each instrument's distant motif (stereo-panned, distance-attenuated, in its own timbre) and watch for golden glints and light pillars rising over dune crests. If you search a long time without singing, the game gently reminds you that Space makes nearby voices answer.
- **Sing** near an instrument to begin its trial: an echo-match (tap Space as each note crosses the staff line) for most, or a steady-breath hold for the flute and horn. Win and it flies home to the altar and joins the song permanently.
- Each collected instrument adds a new synced musical layer (72 BPM, 8-beat bar) that loops in time with all the others — and physically restores part of the shrine (banners, chimes, a bridge of light…).
- The canyon unfolds in three acts: after the fifth voice some go dormant and only song reveals them; after the eighth, the deep sanctuary wakes.
- A compass points toward the nearest unfound instrument early on, then sleeps so the songs can lead; press **C** anytime to recall it. Inscribed lore stones tell the sanctuary's story as you pass.
- Sing along the dune crests to ride a sand-slide. A faint ghost companion may retrace a past wanderer's steps.
- **Collect all 10** to trigger a chord-progression finale — sung in the order you gathered them — and a victory card that names the song your journey created.

## Visual Features

- Pseudo-3D perspective projection with yaw rotation
- Depth-sorted painter's algorithm (dunes, walls, ruins, altar, treasures — far to near)
- Parallax dune layers, ground height-fog, projected shadows
- Glowing stepped pyramid altar as a focal landmark (visible from anywhere)
- Particle systems: dust drift, sparkle trails, sing pulses drawn as real music notes (quavers and beamed pairs), victory fireworks
- Film grain + vignette post-processing
- Warm tint that intensifies as the sanctuary awakens

## Audio Features

- Fully synthesized — no audio files, no samples
- Generated convolution reverb (impulse response)
- Ambient drone + wind bed with LFO modulation
- 10 distinct instrument voices (plucked strings, flute with vibrato, drums, inharmonic bells, shaker, sawtooth horn, choir pad)
- Equal-power stereo panning based on camera-relative angle
- Distance attenuation + air muffling (lowpass) + behind-camera falloff
- Sonar system: singing makes hidden instruments echo back from their world position
- Layered song loops locked to a shared bar clock
- Victory chord burst: Dm → B♭ → F → C → Dm(add9)

## Tech

- `index.html` — everything in one file (~2900 lines)
- HTML5 Canvas 2D
- Web Audio API
- Vanilla JavaScript (no build step, no dependencies)
- Bilingual UI (English / 中文) with the choice persisted between sessions

## License

MIT — do whatever you want with it.
