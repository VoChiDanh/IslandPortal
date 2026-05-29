---
hide:
  - navigation
---
# Welcome to IslandPortal

**IslandPortal** is a high-performance, Folia-aware Paper plugin designed to seamlessly manage skyblock portal islands. 

Whether you are running a classic Skyblock server on Paper or a massively scaled world on Folia, IslandPortal handles default portal placement, block tracking, custom schematics, access control, and cleanups without breaking a sweat.

---

## 🚀 Key Features

- **Folia & Paper Ready:** Built from the ground up for modern server architectures. Fully utilizes Folia's region scheduler and async teleportation.
- **Multiple Skyblock Integrations:** Works seamlessly with **BentoBox**, **SuperiorSkyblock2**, and **Skyllia**.
- **Managed Portals:** Every portal is tracked. We save the ownership, access policies, portal blocks, and trigger blocks.
- **Schematic Island Generation:** Don't just place a portal frame—paste an entire custom schematic around it!
- **Auto-Cleanup:** When an island is deleted or reset, IslandPortal automatically removes the associated portals and support blocks.
- **Custom Actions:** Route players to commands, worlds, or specific servers when they enter a portal.

---

## 🛠️ Runtime Model

How does it work behind the scenes?

IslandPortal creates **Managed Portals**. A Managed Portal contains:

- Ownership data (who created it)
- Access policies (who can use it)
- Portal frame blocks (the physical frame)
- Trigger blocks (the interactive area)
- Optional support blocks (the surrounding island)

**Default Island Portals** are placed intelligently. They are queued immediately after an island creation event. If your skyblock plugin takes time to paste its own massive schematic, IslandPortal will retry placement until the area is ready.
