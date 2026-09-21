# Set up a Kitchen Display

A **Kitchen Display** is one screen in the kitchen. Create one display per kitchen,
station, or device. You can run as many displays as you need.

## Create a display

1. Open **Point of Sale → KDS → Displays**.
2. Click **New**.
3. Fill in the fields:

| Field | Description |
| --- | --- |
| **Name** | A name for the display, for example *Main Kitchen*. |
| **Display Type** | The type of display. Currently only **Kitchen** is available. |
| **Sequence** | The order of the display in the list. |
| **Primary Color** | An optional accent color for the display. |
| **Point of Sale** | The Points of Sale whose orders appear on this display. Leave empty to include **all** Points of Sale. |
| **Current wait time** | The wait time in minutes shown to customers. Set to `0` to disable. Requires `aks_self_order`. |
| **Order Domain** | An advanced filter for orders (see [Configure the KDS](configuration.md)). |
| **Order Line Domain** | An advanced filter for order lines (see [Configure the KDS](configuration.md)). |

4. Configure the **Stages** tab (see [Stages and Alerts](stages.md)).
5. Save the record.

![Kitchen Display form](../assets/screenshots/displays-form.png)
*Screenshot placeholder: Kitchen Display form with the Stages, Filters, and Orderline Groups tabs.*

## Open a display

You can open a display in three ways:

- **From the display record:** click **Open** in the form or on the kanban card.
  This opens `/abichinger_kitchen_screen/app/?ks=<id>` in a new tab.
- **From the POS dashboard:** open a POS session, then click **Kitchen Screen** on the
  POS card. This button appears when the session is open and at least one display is
  linked to the Point of Sale.
- **From POS settings:** link displays to a Point of Sale under
  **Point of Sale → Configuration → Settings → Kitchen Screens**.

> Only internal users can open the Kitchen Display. Opening the app without a valid
> `ks` parameter redirects to the Displays list.

## Link displays to a Point of Sale

A display shows orders from the Points of Sale selected in its **Point of Sale** field.
You can set this from either side:

- On the display: **Point of Sale** field.
- On the Point of Sale: **Settings → Kitchen Screens**.

If the **Point of Sale** field is empty, the display includes orders from every
Point of Sale.

## Run several displays

Create one display per kitchen or station and assign the relevant Points of Sale.
Each display keeps its own stages, filters, and settings. Use the **Sequence** field
to control the order in the Displays list.

![Kitchen Display kanban view](../assets/screenshots/displays-kanban.png)
*Screenshot placeholder: Displays kanban view with several kitchen screens.*
