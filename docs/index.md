---
hide:
  - navigation
---

# POS Kitchen Display (KDS)

The **POS Kitchen Display (KDS)** module shows the orders taken at the Point of Sale
directly in the kitchen. Orders appear in real time, move through the stages you
define, and disappear once they are done.

The module is built for Odoo 19.0 and depends on `point_of_sale` and `pos_restaurant`.

[Get it on the Odoo App Store](https://apps.odoo.com/apps/modules/19.0/abichinger_kitchen_screen){ .md-button .md-button--primary target="_blank" rel="noopener" }

![Kitchen Display interface](assets/screenshots/demo-overview.png)

## What you get

<div class="grid cards" markdown>

-   :material-sync:{ .lg .middle } __Real-time orders__

    ---

    Orders taken by the waiter appear in the kitchen immediately.

-   :material-progress-check:{ .lg .middle } __Progress tracking__

    ---

    Items move through stages such as **Cooking**, **Ready**, and **Done**.

-   :material-cellphone:{ .lg .middle } __Responsive design__

    ---

    The interface adapts to tablets, phones, and desktops.

-   :material-monitor-multiple:{ .lg .middle } __Multiple displays__

    ---

    Run one display per kitchen, station, or screen.

-   :material-filter:{ .lg .middle } __Filters__

    ---

    Filter orders by product category, floor, Point of Sale, or preset.

-   :material-view-dashboard:{ .lg .middle } __Overview__

    ---

    A side panel summarizes the items that still need to be prepared.

-   :material-printer:{ .lg .middle } __Printing__

    ---

    Print order slips to ePOS, IoT, or local printers.

-   :material-alert:{ .lg .middle } __Alerts__

    ---

    Highlight orders that exceed a preparation time and play a sound.

-   :material-sitemap:{ .lg .middle } __Custom workflow__

    ---

    Define your own item states, routes, stages, and dispatch rules.

</div>

## Requirements

- Odoo Community or Enterprise, version 19.0.
- The `point_of_sale` and `pos_restaurant` modules (installed automatically).

Optional modules add extra features:

- [**POS Kitchen Display - Self Order**] —
  show orders from the self-order menu
- [**POS Order Status Screen**] —
  Order status screen
- [**POS Stock Sync**] —
  enable or disable individual dishes from the kitchen display

## Installation

1. Place the `abichinger_kitchen_screen` folder in your addons path.
   Common default addons paths (check `addons_path` in your `odoo.conf`):
   - **Windows:** `C:\Program Files\Odoo <version>\server\addons`
   - **Linux:** `/usr/lib/python3/dist-packages/odoo/addons` (package install) or `<odoo_source>/addons`
   - **macOS:** `<venv>/lib/python3.x/site-packages/odoo/addons` (pip/venv) or `<odoo_source>/addons`
2. Update the app list and install the module from **Apps**.

## Where to find the settings

After installation, open **Point of Sale ‣ KDS** to configure your displays, stages, and more.

## Next steps

- [Set up a Kitchen Display](guide/displays.md)
- [Understand Item States and Item Routes](guide/item-states-routes.md)
- [Configure the KDS](guide/configuration.md)
