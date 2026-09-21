---
title: Setup
nav_order: 3
---

## Requirements

- Odoo Community or Enterprise
- Optional: [`abichinger_pos_stock`](https://apps.odoo.com/apps/modules/18.0/abichinger_pos_stock) for enabling/disabling dishes from the screen
- Optional: [`aks_self_order`] to show orders from the self-order menu

## Installation

1. Place [`abichinger_kitchen_screen`](https://apps.odoo.com/apps/modules/18.0/abichinger_kitchen_screen) in your addons path.
   - Common default addons paths (check your `odoo.conf` → `addons_path`):
     - Windows: `C:\Program Files\Odoo <version>\server\addons`
     - Linux: `/usr/lib/python3/dist-packages/odoo/addons` (package install) or `<odoo_source>/addons`
     - macOS: `<venv>/lib/python3.x/site-packages/odoo/addons` (pip/venv) or `<odoo_source>/addons`
2. Update app list and install the module from Apps.

## Configuration

1. Open the Kitchen Screen menu and create a record:
   - **Name**: e.g., Main Kitchen
   - **Point of Sale**: Select one or more PoS configurations
   - **Current wait time** (requires [`aks_self_order`]): Minutes shown to customers (set to 0 to disable)
   - **Custom filter**: Domain to restrict orders (advanced)
   - **Orderline groups** (`orderline_group_ids`): Define stages (like Appetizer, Main, Dessert) that group order lines on the screen. Add items in the “Orderline Groups” tab:
     - **Sequence**: Determines the order of stages
     - **Name**: Stage title
     - **POS Categories**: Categories to include (subcategories are included automatically)
     - **Product Attributes**: Optional attribute values to include
2. Printers (optional):
   - Configure ePos/Kitchen printers in POS settings
   - Or use a local browser printer connected to the device running the screen
3. Launch the screen:
   - From the Kitchen Screen record (opens `/abichinger_kitchen_screen/app/?ks=<id>`)
   - Or via the button in the POS kanban view

## WebSocket/Proxy Setup

If Odoo runs behind a reverse proxy, configure WebSocket support as follows.

### Multi-threaded (`--workers 0`)

> The multi-threaded server is the default server, also for docker containers. 
> It is selected by leaving the `--workers` option out or setting it to `0` [[1]]

If you are running Odoo behind a proxy in multi-threaded mode you need to set `--proxy-mode` and enable [Websocket proxying](https://nginx.org/en/docs/http/websocket.html).

```nginx
upstream odoo {
  server 127.0.0.1:8069;
}

map $http_upgrade $connection_upgrade {
  default upgrade;
  ''      close;
}

# http -> https
server {
  listen 80;
  server_name odoo.mycompany.com;
  rewrite ^(.*) https://$host$1 permanent;
}

server {
  listen 443 ssl;
  
  # <Your server configuration>
  
  location {
    proxy_pass http://odoo;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection $connection_upgrade;
    
    # <Your location configuration>
  }
}
```

### Multi-processing (`--workers <NUM_WORKERS>`)

> In multi-processing, a dedicated LiveChat worker is automatically started and listens on the `--gevent-port`. 
You must deploy a proxy in front of Odoo and redirect incoming requests whose path starts with `/websocket/` to the LiveChat worker. 
You must also start Odoo in `--proxy-mode` so it uses the real client headers (such as hostname, scheme, and IP) instead of the proxy ones. [[1]]

[Multi-processing Configuration sample](https://www.odoo.com/documentation/17.0/administration/on_premise/deploy.html#id8)


[1]: https://www.odoo.com/documentation/17.0/administration/on_premise/deploy.html#builtin-server
[`aks_self_order`]: https://apps.odoo.com/apps/modules/18.0/aks_self_order
