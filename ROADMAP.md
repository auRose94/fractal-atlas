# Roadmap

The exploration queue for the Fractal Atlas, roughly in build order.

## 1. Hybrid kernels — shipped
- **Bulb × Box** (shipped): mandelbulb orbit with a mandelbox fold + scale
  injected every Nth iteration (`Box fold every N iters` slider). Power and box
  scale both live; the Morph toggle sweeps the scale. From "bulb with box
  bark" (scale −1.5, every 2) to a spherical debris nebula with spiral-galaxy
  cores (scale 2, every 1).
- Queued hybrids: Julia × Box, Burning Ship × fold, triple hybrids with
  per-slot iteration counts (Mandelbulb3D-style formula sequences), and
  user-editable formula slots.

## 2. True 4D fly-through
- Time as the fourth coordinate: instead of slicing the 4-D sets, fly *through*
  them — the geometry continuously re-resolves around the camera. Plan: a
  fly-through mode that maps flight time onto travel along the slice normal
  (and optionally orientation drift), with speed/direction controls and an
  auto-pilot path suitable for screen recording.

## 3. More fractal families
- **Kleinian gasket** — inversion-driven circle chains; dancing "swamp" limit sets
- **Apollonian packing** — infinite sphere-inversion cascades, foam geometry
- **KIFS kaleidoscopes** — rotating fold+scale systems; impossible temples,
  Escher geometry, one preset per "building"
- **Quaternion Tricorn** — conjugate-fold Mandelbrot variant, sharp 3-fold symmetry
- **Angle-modulated bulb ("Rosebulb")** — power varying with orbit angle;
  asymmetric organic bulbs
- **Imaginary / negative power bulbs** — exotic bulb topologies

## 4. 5D — deliberately last
The 4-D modes are slices of 4-D sets; the 5-D body is the *family of all such
slices*. Design sketch: coordinates = (3-D slice point, slice offset w,
meta-parameter), where the meta-parameter indexes the slice orientation itself
(e.g. the Julia constant's angle in 4-space, or the tilt plane of the cut).
One more knob, one more family of structures — visited after everything above
so the navigation language (orbit / slice / cutaway) is fully matured first.
