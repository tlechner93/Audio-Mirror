# Clear View — Bedside Glasses Dock & Cleaner

Project notes for the glasses cleaner nightstand idea, taken from the design brief dated November 11, 2026.

- Full brief (PDF): [Clear_View_Design_Brief.pdf](Clear_View_Design_Brief.pdf)
- Concept boards: [premium](concept-board-premium.png) · [cost-reduced Rev. 2](concept-board-rev2.png)

> The concept boards are AI-generated illustrations, not CAD models. Their labels and dimensions are only approximate.

## 1. Product concept

Clear View is a premium bedside dock for glasses that also cleans them automatically. It should look and feel like a luxury nightstand accessory first, closer to a premium watch winder than an appliance, with cleaning as a bonus. The look is minimalist, futuristic and compact.

**How it works:** place folded glasses on the top platform → roof opens → platform lowers into the sealed chamber → roof closes → lenses are misted and dried → a soft warm glow stays on while the glasses are stored → touch the front control to get them back.

## 2. Design decisions

| Area | Decision |
|---|---|
| Glasses orientation | Folded, lenses facing forward. Nose bridge sits in an adjustable cradle with soft silicone contact points that don't touch the lenses. Test with oversized sunglasses, thick temples and odd frame shapes. |
| Exterior | Tinted, hard-coated polycarbonate shell (cost-reduced). Internal chassis, molded ribs, hidden fasteners, matte-black details. The earlier premium version used smoked glass and black anodized aluminum. |
| Roof | Two panels slide apart into hidden side tracks. They overlap at the center seam with a gasket to keep mist in. Molded polycarbonate panels with built-in guide tracks. |
| Elevator | Guided platform that stays level, holds the frame still, and has replaceable silicone inserts. |
| Cleaning | Sealed fine-mist chamber, fixed nozzles aimed at both lens surfaces, replaceable fluid cartridge, separate waste tray. **No microfiber pads touching the lenses.** |
| Drying | Centrifugal blower, filtered intake, internal air channels, moisture baffle, hidden rear exhaust. Cleaning and drying airflow are controlled separately. |
| Controls | Weight sensor to detect glasses, capacitive touch to retrieve, position sensing, ambient LEDs, safety interlocks. No touchscreen. |

## 3. Cost target: $50 in parts at 10,000 units

Chosen configuration: one shared motor for roof and elevator, tinted polycarbonate exterior, replaceable fluid cartridge. This is an aggressive target, not a supplier quote.

| Part group | Target |
|---|---:|
| Molded tinted polycarbonate shell | $8.00 |
| Roof panels, tracks, sliders | $4.00 |
| Elevator platform, guides, inserts | $2.50 |
| Shared geared DC motor | $4.50 |
| Cam drum, gears, belts, linkages | $2.50 |
| Mist pump and nozzles | $4.00 |
| Fluid cartridge and waste tray | $2.00 |
| Centrifugal blower | $3.00 |
| Air filter, ducts, baffle | $1.50 |
| Control board and drivers | $4.00 |
| Sensors and switches | $2.00 |
| LEDs and lighting driver | $0.75 |
| Seals, gaskets, silicone parts | $1.50 |
| Wiring, connectors, hardware | $2.75 |
| **Subtotal** | **$43.00** |
| External power adapter | $4.50 |
| Contingency allowance | $2.50 |
| **Target total** | **$50.00** |

Not included: assembly labor, tooling, packaging, freight, duties, development and testing. Every line still needs supplier quotes and design validation.

## 4. Shared-motor mechanism

One geared DC motor turns a cam drum with two cam tracks: one moves the roof, the other moves the elevator. Dwell sections let one movement stop while the other starts. Position switches confirm each stop so the controller can halt the motor.

| State | Roof | Elevator |
|---|---|---|
| A | Closed | Raised (ready) |
| B | Open | Raised |
| C | Open | Lowered |
| D | Closed | Lowered (cleaning / storage) |

- **Loading:** A → B → C → D
- **Retrieval:** D → C → B, wait at B while the glasses are lifted off, then return to A.

A reversible cam isn't enough by itself. It has to hold position B while you take the glasses, so the indexed stops and the controller matter. The roof must never close while the elevator is in an unsafe position. Needs mechanical stops, torque limiting or current-based obstruction detection, and independent position checks.

## 5. Pneumatic lift alternative

Because the load is light, a small pneumatic lift was suggested instead of a lead-screw elevator. Options:

- **Silicone bellows:** quiet, but still needs a pressure source, controlled release, guides and a way to hold position.
- **Miniature pneumatic cylinder**
- **Spring-assisted platform:** probably the cheapest.

The drying blower probably can't power the lift because centrifugal blowers produce low static pressure. A small diaphragm pump or mechanical air pump would work better, but adds cost and complexity. **Next step:** compare these against the shared-motor cam lift on cost, quietness, control, leakage and reliability.

## 6. Risks to validate

- **Cleaning efficacy:** has to actually remove oily fingerprints, not just wet and dry the lenses.
- **Coating compatibility:** anti-reflective, hydrophobic, blue-light, polycarbonate and plastic lenses.
- **Streaking and residue:** droplet size, solution quality, airflow and drying.
- **Folded-frame geometry:** temples mustn't block the nozzles or airflow from reaching the lenses.
- **Moisture:** no mist escaping, no condensation near electronics, no pooling around the elevator.
- **Mechanical reliability:** roof alignment, cam wear, lift repeatability, noise, jams, obstruction protection.
- **Maintenance:** cartridge, waste tray, filter and cradle must be easy to reach, clean and replace.

## 7. Prototype order

1. Roof tracks, elevator guides, cam drum and shared motor.
2. A separate mist chamber with fixed nozzles and waste collection.
3. Blower, filter, air channels, moisture baffle and exhaust.
4. Controller, position switches, weight sensing, touch control and safety interlocks.
5. Final exterior shell, once the internals and service access are proven.

## 8. Where things stand

- **Selected (Rev. 2):** shared motor for roof and elevator, polycarbonate exterior, replaceable fluid cartridge, $50 parts target at 10k units.
- **Open question:** air suspension / pneumatic lift vs. the cam lift.
- **Next deliverable:** a dimensioned mechanical layout and mechanism study showing roof tracks, cam drum, elevator guides, drive coupling, chamber, cartridge, waste tray, blower, airflow path and service access. No real 3D CAD model (STEP/STL) exists yet.
