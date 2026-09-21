---
title: Troubleshooting
nav_order: 4
---

## Screen does not update in real time

- Ensure reverse proxy passes WebSocket upgrade headers (see [WebSocket/Proxy Setup]({{ site.baseurl }}{% link setup.md %}#websocketproxy-setup))
- Run Odoo with `--proxy-mode` when behind a proxy

## Printing issues

- Confirm printers are configured in POS (ePos or Kitchen Printers)
- For local browser printing, test printing from the device directly

## Products not appearing / filtering too strict

- Products must be available in POS and saleable
- Kitchen Screen applies category filters from the selected PoS plus child categories
- Review the record’s Custom filter (domain) and simplify for testing

## Deactivate dishes not working

- Install [`abichinger_pos_stock`](https://apps.odoo.com/apps/modules/18.0/abichinger_pos_stock)
- Verify the product is available in POS


