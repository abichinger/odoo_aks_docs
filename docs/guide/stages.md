# Stages and Alerts

A **stage** is a column on the Kitchen Display. Each stage is linked to an
[Item State](item-states-routes.md) and defines how items in that state look and behave.

## Default stages

A new display starts with three stages:

| Sequence | Name | Item State | Color |
| --- | --- | --- | --- |
| 0 | Cooking | Cooking | `rgb(82 82 82)` |
| 1 | Ready | Ready | `rgb(2 132 199)` |
| 2 | Done | Done | `rgb(22 163 74)` |

You can rename, reorder, add, or remove stages. Each display has its own stages.

## Stage fields

Open a stage from the **Stages** tab of the display, or click the gear icon next to it.

| Field | Description |
| --- | --- |
| **Sequence** | The order of the stage on the screen. |
| **Name** | The title shown on the stage. |
| **Item State** | The item state this stage displays. |
| **Color** | The color of the stage header and cards. |
| **Orange Alert** | After this many minutes, the order turns orange. `0` disables the alert. |
| **Red Alert** | After this many minutes, the order turns red. `0` disables the alert. |
| **Notification Sound** | The sound played when an order enters this stage. |
| **Show Move Buttons** | Show the buttons that move items to the next or previous stage. |

### Notification sounds

Choose one of the following:

- **None**
- **Alert**
- **Champagne Cork**
- **Dingaling**
- **Drip Echo**
- **Rooster**

> Browsers may block sound until the user interacts with the page. If autoplay is
> blocked, the display shows a dialog with an **Enable** button.

## Rules and constraints

- A stage name must be unique within a display.
- An item state can be used by only one stage per display.
- Items whose state has no stage are not shown on the display. The default
  **Done → Hide** route uses this to remove finished items from the screen.

![Stage configuration](../assets/screenshots/stage-form.png)
*Screenshot placeholder: Stage form with color, alerts, and notification sound.*
