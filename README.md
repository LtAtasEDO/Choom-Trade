# Choom-Trade v1.0.3
A safe player-to-player inventory transfer UI for Cyberpunk RED.

A focused player-to-player inventory transfer module for Foundry VTT 12 and the Cyberpunk RED system.

Module creation assisted by AI.

## Compatibility

- Foundry VTT 12 (verified target: 12.343)
- Cyberpunk RED Core 0.92.1 or newer
- An active Gamemaster must be online to authorize transfers

## Installation

1. Extract the ZIP into Foundry's `Data/modules` directory.
2. Confirm the final path is `Data/modules/choom-trade/module.json`.
3. Enable **Choom Trade** in the world.
4. Reload connected clients once after enabling it.

The active GM automatically creates a player-visible **Choom Trade** script Macro. The same interface is also available from the **Trade** button in the header of an owned character sheet.

Version 1.0.3 bundles a dedicated Choom Trade handshake icon for the generated world Macro and keeps all eight inventory category buttons on one line at the standard dialog width. Armor or clothing whose CPR equipped state is **Equipped** remains protected.

Public helper:

```js
return game.choomTrade.open(typeof args === "undefined" ? null : args);
```

## Tradable inventory

- Gear
- Drugs and food
- Weapons
- Ammunition
- Armor that is **Owned** or **Carried**
- Clothing that is **Owned** or **Carried**
- Crafting components stored as Gear
- Cyberware that is not installed in the Actor's cyberware tree

## Protected inventory

- Installed cyberware, including foundational cyberware listed in `actor.system.installedItems.list`
- Cyberware options attached to another cyberware item
- Equipped armor and shields
- Equipped clothing
- Lifestyle and housing Gear named with `eb/Month`
- The system's intrinsic **Unarmed** and **Thrown Weapon** attack entries
- Skills, Roles, Programs, Cyberdecks, NET Architectures, and other non-inventory document types

Weapons with installed upgrades are moved as one complete bundle. Stackable Gear, Drugs/Food, and Ammunition can be transferred in a chosen quantity. Received equipped items are set to **Carried** so the recipient does not automatically equip or activate them.

## Transfer behavior

- Only `character` Actors owned by non-GM players are shown.
- A user can send only from a character they own.
- The active GM validates ownership, item eligibility, and quantity again at transfer time.
- The destination copy is created before the source is reduced or removed, with rollback protection on failure.
- A public chat receipt records the sender, recipient, item, and quantity.
- Transfers are direct; the recipient does not need to approve each item.

## Included files

- `scripts/choom-trade.mjs` — UI, GM socket broker, transfer transaction, and chat receipt
- `scripts/trade-rules.mjs` — testable inventory and cyberware eligibility rules
- `styles/choom-trade.css` — Cyberpunk yellow/cyan interface and chat styling
- `assets/choom-trade.webp` — bundled handshake icon for the helper Macro
- `extras/fvtt-Macro-choom-trade.json` — optional manual Macro import
