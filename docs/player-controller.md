## **Player Controller Setup (Mandatory)**

For both the Interaction and Inventory systems to function correctly, your game must utilize a Player Controller that inherits from the core plugin class: ***InventoryPlayerController***.

This component is crucial as it handles all necessary input binding and widget management for the plugin.

**Player Controller Integration Options**

You have two primary ways to set this up:

1. **Use the Example:** Utilize the pre-configured example Player Controller included in the plugin content folder: ***BP_InventoryPlayerController***.
2. **Create New:** Create a new Blueprint Player Controller that inherits directly from the base ***InventoryPlayerController*** class.

**The Role of InventoryPlayerController**

The ***InventoryPlayerController*** is **MANDATORY** because it performs two vital functions:

1. **Input Binding:** It is responsible for **binding all input contexts and actions** (e.g., interacting, opening inventory, rotating items) that the plugin uses. Without this component, player input will not register with the inventory system.
2. **Widget Instantiation:** It handles the **instantiation and management of all inventory-related Widgets** (e.g., the Carousel UI, the Prompt Widget, the Investigation Screen).

**Default Settings and Customization**

The ***BP_InventoryPlayerController*** and ***InventoryPlayerController*** based class comes with default values already set for all properties.

![alt text](assets/prt_13.png)

**Input Mapping & Actions**

The **Inventory Input Controller** section links the plugin's functionality to the engine's Input Mapping Contexts (IMC) and Input Actions (IA).

- **Default Assets:** The fields (e.g., IMC_Interaction, IA_OpenInventory) reference the Input Assets found in the plugin's dedicated Input folder.
- **Customization:** You can overwrite these default references with your project's custom Input Mapping Contexts and Input Actions if you prefer to use your own input scheme. **It is highly important that all fields are correctly set** regardless of whether you use the defaults or custom assets.

**Inventory Widget Controller**

This section manages the UI elements and behaviors:

- **Widget Classes:** References the Blueprint Widget classes for the core UI elements (e.g., ***W_InventoryCarouselWidget***, ***W_InventoryInvestigateWidget***). These example widgets are located in the plugin's UI folder.
- **Customization:** The plugin's UI assets are fully customizable. You can modify the provided examples or link your own custom UI classes here.
- **Use Pause Game:** A simple boolean flag that determines if the game world should pause when the inventory screen is opened.