# Roadmap

The exploration queue for the Fractal Atlas, roughly in build order.

## 1. Hybrid kernels — shipped
- **Bulb × Box**: mandelbulb orbit with a mandelbox fold + scale injected every
  Nth iteration (`Box fold every N iters`). Power and box scale both live; the
  Morph toggle sweeps the scale. From "bulb with box bark" (scale −1.5, every 2)
  to a spherical debris nebula with spiral-galaxy cores (scale 2, every 1).
- **Julia × Box**: the quaternion Julia orbit with the same injected folds —
  origami terracing woven through the julia blob.
- **Ship × Box**: the Burning Ship orbit, refolded — renders a compass-rose
  medallion with a radial-spokes core.
- **Sequencer** (shipped): user-editable formula slots — three transform slots
  (Bulb / Box / per-axis Square / Ship / Tricorn / Mirror), each with its own
  step count, applied cyclically with derivative tracking. One remix turned
  into a glassy ice-cube with a carved lens staring out of its face.
  - **Offset modifier** (shipped): XYZ offset applied to the polynomial slots
    (`Square`/`Ship`/`Tricorn`), pre-centered at 0.875 so the quadratic maps'
    natural region sits at the origin — symmetric creatures by default,
    off-center "best of both worlds" on demand.
  - **Deep-links** (shipped): full state (formula, camera, palette, everything)
    serializes into the URL hash and restores on load — every creature has a
    shareable URL. Copy link button included.
- Queued: more slot types (inversion folds, sine bends), sequencer preset
  gallery page.

## 2. True 4D fly-through — shipped
- **Fly-through** toggle (drawer, quat modes): continuous travel along the 4-D
  slice normal with a speed slider and soft bounce at ±2.4 — the geometry
  re-resolves around the camera as you go. Combine with auto-rotate for a
  hands-free auto-pilot path, and with `H` (hide UI) for recordings.

## 3. More fractal families
- **Quaternion Tricorn** (shipped) — conjugate fold `z → z̄² + c`, braided-rope
  symmetry four dimensions deep.
- **Rosebulb** (shipped) — invented for this atlas: the bulb power wobbles with
  orbit azimuth (`p(θ) = power + amp·sin 2θ`), breaking the symmetric lobes into
  organic caramel drapery and rose-cluster knuckles.
- **KIFS Temple** (shipped) — kaleidoscopic IFS: abs fold → orthonormal sort →
  twist → scale-translate. The twist slider breaks the classic Sierpinski
  gasket into rings of triangular-lace tiles; scale slider runs from solid to
  Cantor-dust.
- **Apollonian Foam** (shipped) — periodic tile fold + sphere inversions
  (Inigo Quilez's exact DE): an infinite plain of iridescent foam with golden
  dome-temples at every tile. The Inversion k slider tunes the packing; the
  dark "wells" are real — inversion centers that go to infinity.
- **Kleinian Pearls** (shipped) — a Schottky group of three mutually tangent
  sphere inversions, orbit-folded with conformal scale accumulation. The
  limit structure accumulates *inside* the generator spheres, so enable the
  **Cutaway** to expose the interior: nested pearl rings, limit-point "pupils"
  and violet strata. Future refinement: the classical flat gasket via
  Descartes-sector DEs.

## 4. 5D — shipped (the finale)
There is no canonical "5-D Mandelbrot set": by the Hurwitz theorem, normed
division algebras only exist in dimensions 1, 2, 4 and 8, so dimension five
has no native multiplication for the quadratic map. What the atlas builds
instead is a genuine 5-D *point set*: the **julia-family body**
{(z, t) ∈ ℍ × ℝ : z belongs to the quaternion julia set whose constant
orbits a small circle as t advances}.

**Mandeljulia 5D** raymarches a 3-D slice of that body with three knobs:
- **5th dim t** — position along the julia-constant path (Morph travels it).
- **5D tilt** — couples the fifth coordinate across the view, so a single
  frame holds a *continuum* of julia sets: connected blobs on one side,
  dust on the other, whirlpools between.
- **c-path radius** — how far the constant roams.

Combine with Fly-through (the slice offset) and the slice tilt/basis for
diagonal flights through the body.
