# Preparation Rules

A **Preparation Rule** requires that several stages approve an item before it moves to
the next state. Use it when a dish must be confirmed by more than one station, for
example a grill and a plating station.

Open **Point of Sale → KDS → Preparation Rules**.

| Field | Description |
| --- | --- |
| **Name** | A name for the rule. |
| **Active** | Enable or disable the rule. |
| **Sequence** | The order in which rules are evaluated. |
| **Item State** | The state of the order change line when the rule applies. |
| **Required Stages** | The stages that must approve. At least **two** stages are required. |
| **Product Filter** | Restricts the rule to certain products (same options as item routes). |

## How approval works

1. A stage moves an item forward.
2. If the product matches a preparation rule, the stage records an approval.
3. The item advances only after **all** required stages have approved.
4. Approvals are cleared once the item moves.

> Preparation rules only apply to **forward standard transitions**. Moving an item
> backward or canceling an order is never blocked by a preparation rule.

![Preparation Rule form](../assets/screenshots/prep-rule-form.png)
*Screenshot placeholder: Preparation Rule with required stages and product filter.*
