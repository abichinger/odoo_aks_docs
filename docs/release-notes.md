# Release Notes

## 1.3.0

- Allow to define custom stages for each kitchen screen.
- Add support for custom item states and routes.
- Add preparation rules: require approval from multiple kitchen stages before a
  matching order change line advances to the next state.

## 1.2.1

- Fix: automatically refresh the name of the customer.

## 1.2.0

- Add `presetTime` to the Order model and update related components for display and
  sorting.

## 1.1.2

- Fix duplication: add `copy=False` to the `access_token` field in the KitchenScreen
  model.

## 1.1.1

- Add deletion logic for missing orders in `updateOrders`.

## 1.1.0

- Add sequence to kitchen screens.

## 1.0.5

- Emit `AB_KITCHEN_CHANGE` event.
- Remove delivery time handling from the kitchen screen.

## 1.0.4

- Fix: update delivery location retrieval to use available preset IDs.

## 1.0.3

- `epson_printer.js` requires `init_lna.js`, add it to the manifest.

## 1.0.2

- Fix: update `tableId` assignment to support self-ordering tables.

## 1.0.1

- Fix: make the Send button always visible.

## 1.0.0

- Migrate to Odoo 19.0.
- Open the Kitchen Screen in a new tab.
- Add mode and title to `useClient`.
- Fix vulnerabilities reported by `npm audit`.
- Add custom assets bundle `aks.assets`.
