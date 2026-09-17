# Sandsong — Sanctuary of the Ten Winds

A chill pseudo-3D desert music exploration game inspired by *Journey*. Explore a walled canyon shrine, find ten hidden instruments, and build a layered song that ends in a complete chord progression.

**Single file. No libraries. No external assets.** All visuals are HTML5 Canvas; all sound is synthesized in real time with the Web Audio API.

## Play

Open `index.html` in any modern browser, or run a local server:

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
| **M** | Toggle audio on/off |

## Gameplay

You are the last songkeeper of an abandoned canyon shrine. Ten instrument-spirits — a lyre, flute, drums, oud, bells, harp, shaker, horn, deep drum, and choir stone — are scattered among the ruins. Each one holds a voice of the sanctuary's song.

- **Explore** the enclosed canyon: boulders, broken pillars, and arches form alcoves where instruments hide.
- **Listen** for each instrument's distant motif (stereo-panned, distance-attenuated) and watch for golden glints and light pillars rising over dune crests.
- **Sing** near an instrument to awaken it — it flies home to the altar and joins the song permanently.
- Each collected instrument adds a new synced musical layer (72 BPM, 8-beat bar) that loops in time with all the others.
- A compass at the bottom of the screen points toward the nearest unfound instrument.
- **Collect all 10** to trigger a chord-progression finale and the victory screen.

## Visual Features

- Pseudo-3D perspective projection with yaw rotation
- Depth-sorted painter's algorithm (dunes, walls, ruins, altar, treasures — far to near)
- Parallax dune layers, ground height-fog, projected shadows
- Glowing stepped pyramid altar as a focal landmark (visible from anywhere)
- Particle systems: dust drift, sparkle trails, sing pulses, victory fireworks
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

- `index.html` — everything in one file (~1500 lines)
- HTML5 Canvas 2D
- Web Audio API
- Vanilla JavaScript (no build step, no dependencies)

## License

MIT — do whatever you want with it.
