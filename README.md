# Charged particles in electric and magnetic fields

A small simulation of how charged particles move in magnetic fields, using the
**Boris pusher**, the standard integrator in plasma physics codes.

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Ruazokyrtap/boris-particle-sim/HEAD?urlpath=voila%2Frender%2Fsliders.ipynb)
← click to open the interactive version in your browser (nothing to install; first load takes a minute or two)

## What it shows

**1. Gyration.** In a uniform magnetic field a particle circles the field lines with the
Larmor radius r_L = m v⊥ / (|q| B). The Boris pusher keeps the energy constant to machine precision.

**2. E×B drift.** Add an electric field and the orbit drifts sideways at v = E × B / B².
Ions and electrons gyrate in opposite directions but drift together at the same speed.

![E×B drift](exb_drift.png)

**3. Magnetic mirror.** In a field that is weak in the middle and strong at the ends, the magnetic
moment μ = m v⊥² / 2B is conserved, so particles slow down along B and bounce back.
Particles are trapped if sin²α > 1/R, where α is the pitch angle and R = B_max / B_min.

![Mirror trapping](mirror.png)

**4. The loss cone.** Launching 1,000 particles with random directions shows the cone of
escaping particles in velocity space. For R = 2, about 29% escape, which matches theory.

![Loss cone](loss_cone.png)

## Files

| File | What it does |
|---|---|
| `fields.ipynb` | Electric and magnetic field definitions (uniform, mirror) |
| `pusher.ipynb` | The Boris step and the integration loop |
| `sliders.ipynb` | Interactive version with sliders for E, B, mirror ratio, pitch angle and charge |
| other notebooks | The individual steps: gyration, E×B drift, mirror, loss cone |

## Run it yourself

```bash
pip install -r requirements.txt
jupyter lab
```

Units are normalized: q = m = 1, and time is measured in 1/ω_c.
