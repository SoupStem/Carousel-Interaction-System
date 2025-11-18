## **Core System Components**

To ensure the full functionality of the plugin, the system relies on two essential components that must be attached to your primary Character or Pawn. The presence of both components is mandatory for the correct functioning of both interaction and inventory management features.

## 1. **Interaction Manager Component**

- Function: Responsible for the centralized management of all in-game interactions.
- Key Responsibilities: Manages the raycasting or collision detection system for interactions, handles player input for interacting with objects, and oversees other important functionalities related to world interaction.

## 2. **Inventory Manager Component**

- Function: Responsible for the complete management of the inventory system.
- Key Responsibilities: Manages the core inventory data structure (adding, removing, moving items), tracks equipped items, and provides the communication interface for the Inventory Carousel itself.

***Essential Requirement***

- Attachment: Both the **Interaction Manager Component** and the **Inventory Manager Component** must be added to the player's main Actor (either a **Character** or **Pawn**) for any plugin functionality to be properly initialized and operate.

## 3. **Component Integration Option**

**Integration Method: Creating New Components**

To integrate the system, you must create new Components that inherit directly from the core base classes provided by the plugin.

![alt text](assets/prt_3.png)
![alt text](assets/prt_5.png)

- **Action:** Create two new components (e.g., new Blueprints) that inherit from the respective base classes:

    - **InteractionManagerComponent**
    - **InventoryManagerComponent**

**Essential Requirement**
- **Attachment:** It is mandatory that both the ***Interaction Manager Component*** and the ***Inventory Manager Component*** are attached to your main Character or Pawn for the plugin to function correctly.