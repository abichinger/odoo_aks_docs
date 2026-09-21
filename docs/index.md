# POS Kitchen Display (KDS)

The **POS Kitchen Display (KDS)** module shows the orders taken at the Point of Sale
directly in the kitchen. Orders appear in real time, move through the stages you
define, and disappear once they are done.

The module is built for Odoo 19.0 and depends on `point_of_sale` and `pos_restaurant`.

## What you get

| Feature | Description |
| --- | --- |
| Real-time orders | Orders taken by the waiter appear in the kitchen immediately. |
| Progress tracking | Items move through stages such as **Cooking**, **Ready**, and **Done**. |
| Responsive design | The interface adapts to tablets, phones, and desktops. |
| Multiple displays | Run one display per kitchen, station, or screen. |
| Filters | Filter orders by product category, floor, Point of Sale, or preset. |
| Overview | A side panel summarizes the items that still need to be prepared. |
| Printing | Print order slips to ePOS, IoT, or local printers. |
| Alerts | Highlight orders that exceed a preparation time and play a sound. |
| Custom workflow | Define your own item states, routes, stages, and dispatch rules. |

## Requirements

- Odoo Community or Enterprise, version 19.0.
- The `point_of_sale` and `pos_restaurant` modules (installed automatically).

Optional modules add extra features:

- [`abichinger_pos_stock`](https://apps.odoo.com/apps/modules/18.0/abichinger_pos_stock) —
  enable or disable individual dishes from the screen.
- [`aks_self_order`](https://apps.odoo.com/apps/modules/18.0/aks_self_order) —
  show orders from the self-order menu and display the current wait time.

## Installation

1. Place the `abichinger_kitchen_screen` folder in your addons path.
   Common default addons paths (check `addons_path` in your `odoo.conf`):
   - **Windows:** `C:\Program Files\Odoo <version>\server\addons`
   - **Linux:** `/usr/lib/python3/dist-packages/odoo/addons` (package install) or `<odoo_source>/addons`
   - **macOS:** `<venv>/lib/python3.x/site-packages/odoo/addons` (pip/venv) or `<odoo_source>/addons`
2. Update the app list and install the module from **Apps**.

## Where to find the settings

After installation, open **Point of Sale → KDS**. The menu contains:

| Menu item | Purpose |
| --- | --- |
| **Displays** | Create and manage Kitchen Displays. |
| **Item States** | Define the states an item can be in. |
| **Item Routes** | Define how items move between states. |
| **Preparation Rules** | Require approval from several stages before an item advances. |
| **Dispatchers** | Distribute items across several destinations (for example, two kitchens). |

## Next steps

- [Set up a Kitchen Display](guide/displays.md)
- [Understand Item States and Item Routes](guide/item-states-routes.md)
- [Configure the KDS](guide/configuration.md)
