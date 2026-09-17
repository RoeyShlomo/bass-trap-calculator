# Bass Trap Calculator

Absorption modelling for bass traps, and how many a room needs.

**Live: https://roeyshlomo.github.io/bass-trap-calculator/**

Four absorber models — limp membrane, MDF plate, Helmholtz resonator and
perforated panel — over air or porous-filled cavities, plus a room calculator
that turns a target decay time into a trap count.

Everything runs in the browser. No install, no server, no data leaves the page.

## What it models

| Model | Method |
|---|---|
| Limp membrane / MLV | mass reactance over an exact cavity impedance |
| MDF plate | transformed-section laminate stiffness, Warburton frequency coefficients |
| Helmholtz resonator | end corrections per neck type; viscous, end and radiation losses |
| Perforated panel | Maa |
| Porous fill | Delany–Bazley, with Johnson–Champoux–Allard available |

Absorption is computed at **normal incidence**, which is the right choice at bass
wavelengths, so these figures are not comparable with random-incidence
reverberation-chamber data.

Results are labelled by confidence. Resonance frequencies, room modes and
geometry are analytical and hold to roughly ±5% when the material properties are
known. Absorption coefficient, Q and bandwidth depend on construction quality,
tolerances, air leaks and placement — a built trap typically lands 10–30% below
the theoretical figure. Below the Schroeder frequency, Sabine and Eyring assume a
diffuse field that does not exist, and the room calculator says so when it applies.

## This repository

Holds the built page only, so it can be served from GitHub Pages. The source, the
specification it implements and its formula audit live in a separate private
repository.

`site/index.html` is a single self-contained file with no external references. It
also works offline: download it and open it in any browser.
