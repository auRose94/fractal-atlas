# Fractal Atlas

Four classic distance-estimated fractals in one interactive raymarcher,
all in a single file: `index.html` (raw WebGL2, no dependencies, no build step).

- **Mandelbulb** — the classic `z → zⁿ + c` in spherical coordinates; power-8 is the icon.
- **Mandelbox** — box-fold → sphere-fold → scale. Scale ≈ −1.5 gives perforated
  architecture; scale 2 gives baroque machinery. Zoom inside.
- **Quaternion Julia** — `z → z² + c` with quaternions, `c` frozen (5 presets).
  Check **Morph** to watch `c` drift through 4-space.
- **Mandelbrot 4D (slice)** — the true 4-D quadratic Mandelbrot (`c` = the point),
  raymarched as a 3-D slice at height `w`. At `w = 0` you see the cardioid revolved
  into layered horns; slide `w` (or hit **Morph**) to cut through the fourth
  dimension and watch the whole body reorganize.
- **Burning Ship 4D (experimental)** — the classic 2-D Burning Ship iteration
  (`z → (|Re z| + Im z)² + c`) extended to quaternions and raymarched as a 4-D
  solid. As far as we know this one hasn't been done before. The flat 2-D ship is
  still in there: home view + **Cutaway** at depth 1.00 + face-on camera reveals
  the sheet; zoom in along its boundary to find the hull ribs.
- **Hybrid: Bulb × Box** — a mandelbulb orbit with a mandelbox fold + scale
  injected every Nth iteration. Power and box scale both live; from "bulb with
  box bark" to a spherical debris nebula with spiral-galaxy cores.
- **Hybrid: Julia × Box** and **Hybrid: Ship × Box** — the same fold injection
  applied to the quaternion Julia and Burning Ship orbits (origami terracing;
  a compass-rose medallion).
- **Tricorn 4D** — the conjugate-fold Mandelbrot variant (`z → z̄² + c`) in
  quaternions; braided-rope symmetry.
- **Rosebulb** — invented for this atlas: the bulb power wobbles with orbit
  azimuth, melting the symmetric lobes into organic caramel drapery.
- **Sequencer** — compose your own fractal: three formula slots (Bulb, Box,
  per-axis Square, Ship, Tricorn, Mirror), each with its own step count,
  applied cyclically. Detail and draw-distance controls live in the drawer.
- **Fly-through** (drawer, quat modes) — continuous travel through the fourth
  dimension with a speed slider and soft bounce; combine with auto-rotate for
  auto-pilot recordings.
- **KIFS Temple** — kaleidoscopic IFS: abs fold → orthonormal sort → twist →
  scale. Twisted Sierpinski gaskets, triangular-lace tiles, fractal temples.
- **Apollonian Foam (infinite)** — periodic tile fold + sphere inversions: an
  endless iridescent plain with golden dome-temples. The dark wells are real
  inversion centers going to infinity.

See [ROADMAP.md](ROADMAP.md) for the full queue (Kleinian next, then 5-D).

## Run it

Open `index.html` in any WebGL2-capable browser. No server needed.
The whole thing is ~33 KB of HTML (≈10 KB gzipped) — all computation happens
in each visitor's browser on their GPU, so hosting it is a static-file
workload: essentially free bandwidth, zero server compute.

## Controls

| Input | Action |
|---|---|
| Left-drag | Orbit |
| Wheel / pinch | Zoom |
| Right-drag / Shift-drag | Pan |
| **Alt + drag** (quat modes) | Tilt the 4-D slice (horizontal) / move it (vertical) |
| **Alt + wheel** (quat modes) | Slice offset in exact 0.01 steps |
| Double-click or `R` | Reset view (per-fractal home) |
| `Space` | Toggle auto-rotate |
| `H` | Hide all UI (clean screenshots) |

The **4D slice & cutaway** drawer (collapsible) holds the slice as numbers —
azimuth, elevation, tilt (full 0→π, no clamp), and w offset, all at 0.01 steps —
plus the **Cutaway** toggle: a clipping plane at a chosen fraction of the view
distance that removes the near half of the solid and shows the interior
cross-section, colored by orbit trap. Works on every fractal.

**Morph** animates each fractal's signature parameter: bulb power, box scale,
Julia's `c`, or the 4-D slice position. **Screenshot** saves a PNG.

Shared knobs: iterations, detail (marching epsilon), glow, palette, coloring
(orbit trap / escape iterations / clay), soft shadows, auto resolution
(adapts render scale toward ~60 fps).

## Implementation notes

- Per-pixel sphere tracing with an analytic distance estimator per fractal;
  screen-space (cone) epsilon so detail holds while zooming.
- Quaternion math for the Julia/Mandelbrot-4D kernels (`z → z² + c`, derivative
  via `dz = 2·z·dz`); Mandelbox folds track the derivative explicitly.
- Surface color uses an orbit trap (minimum `|z|` along the orbit); lighting is
  key light + soft shadows + AO + Fresnel, tonemapped and dithered.
- Scene scale (fog, AO radius, glow falloff) normalizes per fractal so all four
  feel consistent at their home views.
- Deep zooms can show artifacts near set boundaries — inherent to distance
  estimation, not your GPU.

Tuning playground: palettes in `palette()`, lighting in `shadePoint()`,
kernels in `bulbDE()` / `boxDE()` / `quatDE()`, marcher constants in `march()`.
