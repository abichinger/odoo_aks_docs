---
hide:
  - navigation
---

# Troubleshooting

## The screen does not update in real time

The display uses a WebSocket connection. If it is lost, a warning appears at the top
of the screen.

- Ensure your reverse proxy passes WebSocket upgrade headers.
- Run Odoo with `--proxy-mode` when it runs behind a proxy.

### WebSocket and proxy setup

#### Multi-threaded (`--workers 0`)

The multi-threaded server is the default server, also for Docker containers. It is
selected by leaving out the `--workers` option or setting it to `0`.

If Odoo runs behind a proxy in multi-threaded mode, set `--proxy-mode` and enable
[WebSocket proxying](https://nginx.org/en/docs/http/websocket.html).

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

#### Multi-processing (`--workers <NUM_WORKERS>`)

In multi-processing, a dedicated LiveChat worker starts automatically and listens on
the `--gevent-port`. Deploy a proxy in front of Odoo and redirect incoming requests
whose path starts with `/websocket/` to the LiveChat worker. Start Odoo in
`--proxy-mode` so it uses the real client headers (hostname, scheme, and IP) instead
of the proxy ones.

See the
[Multi-processing configuration sample](https://www.odoo.com/documentation/19.0/administration/on_premise/deploy.html#id8).

## Printing issues

- Confirm printers are configured in POS (ePOS or Kitchen Printers).
- For local browser printing, test printing from the device directly.

## Products do not appear, or filtering is too strict

- Products must be available in POS and saleable.
- The Kitchen Screen applies category filters from the selected Point of Sale plus
  child categories.
- Review the record's custom filter (domain) and simplify it for testing.

## Deactivate dishes does not work

- Install [**POS Stock Sync**].
- Verify the product is available in POS.

## The notification sound does not play

Browsers may block autoplay until the user interacts with the page. If autoplay is
blocked, the display shows a dialog with an **Enable** button. Click it to allow sound.
