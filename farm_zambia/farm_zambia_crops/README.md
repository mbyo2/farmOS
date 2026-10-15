# Zambia crops

Provides default **plant type** taxonomy terms for crops commonly grown in
Zambia, so farmers and extension workers don't have to type them in by hand.

## What it does

On install, the module adds 16 crop terms to farmOS's built-in `plant_type`
vocabulary:

Maize, Cassava, Groundnuts, Sorghum, Finger millet, Pearl millet, Soybeans,
Sunflower, Cotton, Tobacco, Sweet potatoes, Irish potatoes, Beans, Cowpeas,
Rice, Wheat.

Each term carries a short description of the crop's role in Zambian
agriculture. Where a Bemba or Nyanja local name is well-established, it is
included in the description (e.g. maize = *chimanga*, groundnuts =
*balemba*/*njugu*, cassava = *tute*, sorghum = *amasaka*/*mapila*, sweet
potatoes = *mbatata*, cowpeas = *nyemba*, rice = *mpunga*, wheat = *tirigu*,
soybeans = *soya*). Local names were only added where the authors were
confident; crops without a confident local name ship with an English-only
description.

## Zambian context

Maize dominates Zambian smallholder farming — it is both the staple food and
the crop most government input programmes (e.g. FISP) are built around. The
other terms cover the country's main cash crops (cotton, tobacco, soybeans,
sunflower), traditional drought-tolerant cereals (sorghum, millets),
root/tuber food-security crops (cassava, sweet potatoes), and legumes used in
rotation with maize (beans, cowpeas, groundnuts, soybeans).

## Technical notes

- Taxonomy terms are content entities in Drupal, so they cannot be shipped
  as configuration. The terms are created in `hook_install()` and existing
  terms are never duplicated.
- Depends on `farm_plant_type` (upstream farmOS), which provides the
  `plant_type` vocabulary.
- Terms are left in place if the module is uninstalled, to avoid deleting
  data that farm records may reference.
