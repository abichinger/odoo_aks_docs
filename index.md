---
title: Home
nav_order: 1
---

# POS Kitchen Screen (Odoo KDS)

The POS Kitchen Screen module enhances kitchen efficiency by providing real-time order synchronization, clear progress tracking, and a responsive interface optimized for tablets and large screens.

## Features

- **Real-time orders**: Orders are displayed instantly as they’re taken in POS.
- **Progress tracking**: Status flows through Cooking → Ready → Done.
- **Merge order changes**: Optionally merge subsequent changes into the original order view.
- **Overdue alerts**: Orders exceeding configured prep time turn orange then red.
- **Product variants**: Clear variant information on order lines.
- **Print on demand**: Print from the kitchen screen via:
  - POS ePos Printer (e.g., Epson)
  - POS Kitchen Printers
  - A local browser printer connected to the screen
- **Deactivate dishes**: Quickly mark products unavailable directly from the screen.
  - Requires module [`abichinger_pos_stock`](https://apps.odoo.com/apps/modules/18.0/abichinger_pos_stock) to enable/disable dishes.
- **Internal notes**: Show internal notes on order lines.
- **Overview panel**: Aggregated counts of all items in preparation.
- **Notification sound**: Play a sound for new orders (configurable).
- **Order sorting**: Sort by tracking number or preparation time.
- **Multiple PoS sessions**: Combine multiple PoS sessions on one display.

<!-- ## Compatibility

- **Odoo**: 17.0 (and family)
- **Dependencies**: `point_of_sale`, `pos_restaurant` -->

## Links

- **Odoo Apps**: [https://apps.odoo.com/apps/modules/18.0/abichinger_kitchen_screen](https://apps.odoo.com/apps/modules/18.0/abichinger_kitchen_screen)
- **Live Demo**: [https://odoo-demo.duckdns.org/web#action=point_of_sale.action_pos_config_kanban](https://odoo-demo.duckdns.org/web#action=point_of_sale.action_pos_config_kanban)


