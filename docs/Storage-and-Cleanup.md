# Storage and Cleanup

IslandPortal keeps track of every portal and its associated blocks to ensure no stray blocks or data are left behind when players manage their islands.

---

## 💾 Stored Data

All portal data is safely stored under the server's `playerdata` folder.

Each **Managed Portal** stores the following metadata:

- **Portal ID**
- **Portal Type**
- **World & Base Block Location**
- **Facing Direction**
- **Owner UUID**
- **Island ID** (links the portal to the skyblock island)
- **Default Portal Flag** (is this the first spawn portal?)
- **Access Policies** (who is allowed to use/modify it)
- **Island Members**
- **Portal Frame Blocks** (the physical frame)
- **Trigger Blocks** (the interactable middle blocks)
- **Support Blocks** (the platform or schematic pasted around it)

---

## 🧹 Auto-Cleanup

When an island is deleted, reset, or removed by your Skyblock plugin, IslandPortal listens to the event and acts automatically.

It finds any matching managed portals linked to that island and **safely removes**:
1. The portal frame.
2. The trigger blocks.
3. All tracked support blocks (from generated islands or schematic pastes).

This guarantees a clean world without floating leftover portal platforms!

---

## ⏱️ Autosave

To prevent data loss and ensure maximum performance:

- Autosave is controlled by `runtime.autosave-interval-minutes` in your `config.yml`.
- The plugin uses an atomic dirty flag.
- **File I/O runs entirely asynchronously** so it will never lag your main server thread or region threads.
