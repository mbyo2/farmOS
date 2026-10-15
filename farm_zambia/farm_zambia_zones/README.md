# Zambia agro-ecological zones

Provides an `agroecological_zone` taxonomy vocabulary containing Zambia's
three officially recognised agro-ecological regions.

## What it does

On install, the module:

1. Creates the **Agroecological zone** vocabulary (`config/install`).
2. Adds three terms via `hook_install()`:
   - **Region I** — low rainfall (<800 mm/year): southern valleys
     (Zambezi, Luangwa) and parts of Southern/Western Provinces.
   - **Region II** — medium rainfall (800–1000 mm/year): the central
     plateau (Central, Lusaka, Eastern, Southern plateau).
   - **Region III** — high rainfall (>1000 mm/year): the northern
     high-rainfall belt (Northern, Luapula, North-Western, Copperbelt).

Each term describes its rainfall range, geography, and suitable enterprises.

## Zambian context

Zambia's Ministry of Agriculture classifies the country into these three
regions, and the classification drives practical decisions: which crops are
viable without irrigation, where input support programmes focus, and how
extension advice is tailored. Region II is the country's agricultural
heartland (maize, soybeans, wheat); Region I favours drought-tolerant crops
and livestock; Region III favours cassava, millets and tree crops but needs
soil-acidity management.

Tagging land assets or logs with their region lets farmOS users filter and
compare records across zones — e.g. benchmarking maize yields in Region II
against Region I.

## Technical notes

- The vocabulary ships as configuration; the terms are content entities and
  are created in `hook_install()` (existing terms are never duplicated).
- Terms are left in place if the module is uninstalled, to avoid deleting
  data that farm records may reference.
