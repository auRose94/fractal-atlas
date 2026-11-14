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
- Queued hybrids: triple hybrids with per-slot iteration counts
  (Mandelbulb3D-style formula sequences) and user-editable formula slots.

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
- Still queued: **Kleinian gasket** — Schottky-group limit sets via circle
  inversions; the one kernel that needs its own dedicated tuning session.

## 4. 5D — deliberately last
The 4-D modes are slices of 4-D sets; the 5-D body is the *family of all such
slices*. Design sketch: coordinates = (3-D slice point, slice offset w,
meta-parameter), where the meta-parameter indexes the slice orientation itself
(e.g. the Julia constant's angle in 4-space, or the tilt plane of the cut).
One more knob, one more family of structures — visited after everything above
so the navigation language (orbit / slice / cutaway / fly) is fully matured
first.
