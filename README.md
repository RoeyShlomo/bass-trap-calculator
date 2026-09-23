# Bass Trap Calculator

Absorption modelling for bass traps, and how many a room needs.

**Live: https://roeyshlomo.github.io/bass-trap-calculator/**

Four absorber models — limp membrane, MDF plate, Helmholtz resonator and
perforated or slatted panel — over air or porous-filled cavities, plus a room
calculator that turns a target decay time into a trap count.

Everything runs in the browser. No install, no server, no data leaves the page.

## What it models

| Model | Method |
|---|---|
| Limp membrane / MLV | mass reactance over an exact cavity impedance |
| MDF plate | transformed-section laminate stiffness, Warburton frequency coefficients |
| Helmholtz resonator | end corrections per neck type; viscous, end and radiation losses |
| Perforated panel | transfer model with an open-area-dependent end correction; Maa for microperforation |
| Slatted panel | slot end correction and mass, over the same cavity |
| Resistive layer | flow resistance at the openings or out in the cavity |
| Porous fill | Mechel–Grundmann in the bass, Delany–Bazley above it |
| Flow resistivity | measured, or Bies–Hansen from density and fibre diameter |

The trap designer computes absorption at **normal incidence**, which is the right
choice at bass wavelengths, so those figures are not comparable with
reverberation-chamber data. The room calculator converts to random incidence with
Paris' formula before it reaches Sabine, because Sabine assumes a diffuse field.

Results are labelled by confidence. Room modes and geometry are analytical and
hold to roughly ±5% when the material properties are known. A panel absorber's
resonance is reported as a ±10% band rather than a single figure, because even a
transfer-matrix prediction of a measured absorber is about that far out.
Absorption coefficient, Q and bandwidth depend on construction quality,
tolerances, air leaks, placement and on a damping figure that is assumed rather
than measured — there is no formula for the mounting losses that dominate it — so
a built trap typically lands 10–30% below the theoretical figure.

Below the Schroeder frequency the room is modal, not diffuse, so the calculator
stops presenting a Sabine trap count as an answer there: it dims the number and
shows the modes instead, with each one's present half-power width, the width the
target decay implies, and how much of that mode a trap in that position can
actually reach.

Trap placement is computed from the modal pressure over the trap's face rather
than a category, so a trap standing at a pressure node reads as doing nothing —
because it does nothing.

The room page offers the ITU-R BS.1116 target for the room's volume, at the
frequency being worked on rather than only the broadband nominal, since the
standard's tolerance widens upward through the bass. Where BS.1116 specifies
nothing — below 63 Hz, which is most of what a bass trap is for — it says so
instead of extending the curve.

Air properties are those of the stated 20 °C: ρ₀ = 1.204 kg/m³ with c₀ = 343 m/s.

## This repository

Holds the built page only, so it can be served from GitHub Pages. The source, the
specification it implements, its formula audit and the literature review behind
the models live in a separate private repository.

`site/index.html` is a single self-contained file with no external references. It
also works offline: download it and open it in any browser.
