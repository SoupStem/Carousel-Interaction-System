## **Creating Interactive Objects (Collectables/Pickups)**

The next step is to introduce interactive objects (collectables or pickups) into your game world. The plugin provides a base class and example actors to streamline this process.

**Item Creation Option**

**Create New Actor:** Create a new Blueprint Actor that inherits from the ***InventoryInteractionItem*** class.

    Efficiency Note: You do not need to create a new unique Actor class for every single item. You can simply place one Collectable Actor in the world, configure its properties, and then duplicate it for new items, changing only the necessary settings.

Core Interaction Settings

When configuring your Collectable Actor, focus on these key properties:

![alt text](assets/prt_12.png)

- **Item Tag:** **Mandatory ID:** The unique identifier (Tag) for the item. - This Tag must exactly match a **ItemTag** in your Master Inventory Data Table (DT_ItemDataSort). When set, the system automatically loads and applies the item's mesh and configuration from the **Data Asset**.

**Interaction Widget Component**

The **Interaction Widget Component** displays the prompt (e.g., "Press E to Collect").

- **Adjustment:** For items of different sizes, you may need to adjust the location of the **Interaction Widget Component** to ensure the prompt is clearly visible above the item. This is done by selecting the component and modifying its Location in the Details Panel.
- **Rotation:** The component's rotation is handled automatically by the plugin to always face the player, ensuring readability.

**Crucial Physics and Collision Configuration**

The plugin manages collision based on the item's physics state. You must correctly set the collision profiles for both states.

- **Simulate Physics:** This boolean determines whether the item is physically simulated in the world (e.g., rolling when hit).
- **Index Mapping:** The settings in ***Profile Names*** and ***Collision Enabled Modes*** are indexed based on the state of ***Simulate Physics***:
    - ***Simulate Physics*** is **TRUE:** The system uses Index

        0

    settings for both ***Profile Names*** and ***Collision Enabled Modes***.

    - ***Simulate Physics*** is **FALSE:** The system uses Index

        1

    settings for both ***Profile Names*** and ***Collision Enabled Modes***.

**Configuration Warning:** Ensure that the collision settings for both Index

    0

and Index

    1

are configured correctly to guarantee that the interaction logic can properly detect and collect the item regardless of whether it is simulating physics or not.