# Zambia conservation farming

Provides **log category** taxonomy terms for the conservation farming
practices widely promoted in Zambia, so field activities can be recorded
against a standard set of practices.

## What it does

On install, the module adds five terms to farmOS's built-in `log_category`
vocabulary:

- **Planting basins (Chololo)** — hand-dug basins concentrating water and
  inputs at the plant station.
- **Minimum tillage / Ripping** — ripping planting lines instead of full
  ploughing.
- **Crop rotation** — cereal/legume rotations for nitrogen fixation and
  pest-cycle breaks.
- **Agroforestry (Faidherbia / Moringa)** — nitrogen-fixing trees in
  cropland (*Faidherbia albida*, known locally as *musangu*, and moringa).
- **Mulching / Residue retention** — keeping crop residues as surface cover
  instead of burning.

Categorizing logs (e.g. seeding, input and observation logs) with these
terms lets projects track adoption of conservation farming across farmers
and seasons.

## Zambian context

Conservation farming has been promoted in Zambia since the 1990s, notably
by the Conservation Farming Unit (CFU), as a response to declining soil
fertility, erratic rainfall and the high cost of inputs. The core package —
minimum tillage, planting basins (*chololo*), precise input placement, crop
residue retention and rotations — is taught to hundreds of thousands of
smallholders. *Faidherbia albida* (*musangu*) is the flagship agroforestry
species: it fixes nitrogen and drops its leaves in the rainy season, so it
fertilises crops without shading them.

## Technical notes

- Taxonomy terms are content entities in Drupal, so they cannot be shipped
  as configuration. The terms are created in `hook_install()` and existing
  terms are never duplicated.
- Depends on `farm_log_category` (upstream farmOS), which provides the
  `log_category` vocabulary.
- Terms are left in place if the module is uninstalled, to avoid deleting
  data that farm records may reference.

## Future quick-log idea

These categories pair naturally with a farmOS **quick form** (a
"Conservation farming" quick log) that lets extension workers record a
practice, area covered and inputs used in a few taps. That is left as a
follow-up: it needs UX decisions beyond default terms.
