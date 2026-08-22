# Changelog

## 1.0.3 — 2026-08-13

- Replaced the generated helper Macro's leather bag icon with the bundled `choom-trade.webp` handshake artwork.
- Automatically migrates the legacy leather bag icon on an existing Choom Trade world Macro while preserving custom Macro icons.
- Kept all eight inventory category buttons, including **Chrome**, on one line at the standard dialog width.

## 1.0.2 — 2026-08-02

- Replaced the light-grey exchange body with a unified near-black background and subtle cyan grid accents.
- Added Armor and Clothing inventory categories.
- Allowed armor and clothing in the **Owned** or **Carried** state to be transferred.
- Protected armor and clothing in the **Equipped** state in both the player UI and GM-side validation.

## 1.0.1 — 2026-08-02

- Improved sender and recipient selector contrast and standardized their typography.
- Reworked category, Send, and Close buttons into a consistent yellow/cyan industrial style.
- Increased the readability of search placeholder and protected-item guidance text.
- Preserved the v1.0.0 transfer rules and transaction behavior unchanged.

## 1.0.0 — 2026-08-02

- Added direct player-to-player inventory transfers through an active-GM broker.
- Added character-sheet **Trade** button, world Macro, search, category filters, and stack quantities.
- Added exact installed/uninstalled cyberware detection using the Actor installation tree.
- Protected armor, clothing, lifestyles, installed chrome, and intrinsic attack entries.
- Added complete transfer of weapon attachment bundles, rollback protection, and public chat receipts.
