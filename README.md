# Single-Family House – Gut Renovation with BIM System

A real-world example model for [IngeTrazo](https://github.com/BastelBaus/ingetrazo-docs):
a 1958 single-family house with basement, ground floor, first floor and attic,
modelled as **existing state and planned gut renovation** (walls removed / new
walls, openings, heating circuits, electrical, furniture, plot and neighbouring
buildings).

The model is an anonymised, English copy of a working project model. Personal
data (owners, address, contact details, photos, file paths) has been removed;
names and texts were translated from German.

## Contents

| Path | What |
|---|---|
| `model/sample-house_v####.igz` | IngeTrazo model – always use the highest version number |
| `model/sample-house_v####.pdf` | All sheets of that model as one vector PDF (A4), exported from IngeTrazo |

## Opening the model

Open `model/sample-house_v####.igz` in IngeTrazo (≥ 0.5.11). Useful starting points:

- **Layers** are grouped in folders *Storeys*, *Walls*, *Measurements*, *Installation*, *Zones*.
  `Walls_old` = existing walls to be removed, `Walls_new` = new walls.
- **Saved views**: `Floor_plan_ground_floor`, `Floor_plan_ground_floor_old`, `Floor_plan_first_floor`, `3D Main`, …
- **Sheets**: `Floor_plan_ground_floor`, `Floor_plan_ground_floor_old`, `Title`.
- Room labels follow the pattern `E01 … E06` (ground floor).

## How the export works

An `.igz` file is a ZIP containing `document.json` (all names and texts),
binary geometry (`geom/*.bin`) and textures. The translator

1. picks the `BIM_v####.igz` with the highest version number from the source folder,
2. translates **only text values** (group / layer / folder / material / view names,
   room labels, title-block fields) using `glossary.csv` and `rules.json`,
3. applies the private redaction rules (replace owner/address, drop embedded photos),
4. copies geometry and textures byte for byte,
5. **aborts without writing anything** if a term is missing from the glossary or if
   any forbidden content remains (personal terms, e-mail, phone numbers, network
   paths, German umlauts).

The translator and its rules are kept private and are not part of this repository.

## Versions

| Model | Source version | Date | Notes |
|---|---|---|---|
| `sample-house_v0013.igz` | v0013 | 2026-10-29 | First public version (incl. saved view "Full"), title "Single-Family House Gut Renovation with BIM System" |

## Licence

© 2026 BastelBaus. The model and documentation are licensed under
[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) –
see [LICENSE](LICENSE). You may share and adapt them, also commercially, as long as you
credit "BastelBaus – IngeTrazo sample house" and link to this repository.

Embedded textures (`textures/` inside the `.igz`) are not covered by this licence and
remain the property of their respective owners.
