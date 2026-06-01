---
hide:
  - navigation
---

# Welcome to IslandPortal

**IslandPortal** is a Folia-aware Paper plugin for skyblock portal islands, managed portal blocks, custom portal actions, configurable island NPCs, and managed minions.

It is built for servers that need predictable behavior on both Paper and Folia: region-safe scheduling, async teleportation, tracked data, island lifecycle cleanup, and simple YAML configuration.

---

## Key Features

- **Folia and Paper ready:** Uses a platform scheduler that respects Folia region ownership and Paper's normal scheduler.
- **Skyblock integrations:** Supports BentoBox, SuperiorSkyblock2, and Skyllia island create/delete/reset events.
- **Managed portals:** Tracks ownership, access policies, frame blocks, trigger blocks, support blocks, and return locations.
- **Portal islands:** Can generate simple platforms or paste WorldEdit/FAWE schematics for portal islands.
- **Custom portal actions:** Teleport players or execute configured console commands.
- **IslandNPC:** Adds configurable NPCs with safe spawn search, click actions, dialogue, commands, look-at-player behavior, movement, unlock conditions, and automatic respawn.
- **Minions:** Place managed island workers with production, storage, upgrades, fuel, GUI management, offline production, owner protection, and respawned display entities.
- **Cleanup:** Removes managed portals, NPCs, and minions when supported skyblock islands are deleted or reset.
- **Admin tools:** Includes commands for reload, portal creation, portal removal, NPC spawn/removal, and minion item/removal tools.

---

## Runtime Model

IslandPortal creates managed objects instead of leaving raw blocks/entities untracked.

A managed portal stores:

- Portal id and type.
- Owner and island id.
- Island members.
- Access policies.
- Portal blocks and trigger blocks.
- Optional support blocks.
- Optional return location.

A managed NPC stores:

- NPC id and type.
- Owner and island id.
- Island members.
- Safe spawn anchor.
- Current entity id while the entity is alive.

A managed minion stores:

- Minion id and type.
- Owner and optional island id.
- Safe spawn anchor.
- Tier.
- Fuel state.
- Stored production.
- Last production timestamp for online and offline production.
- Current display entity id while the entity is alive.

Default island portals and NPCs are queued after island creation events. Minions are usually placed manually from minion items, then tracked and cleaned up by the same managed-object lifecycle.

---

## Recommended Reading

- [Configuration](Configuration.md)
- [Commands and Permissions](Commands-and-Permissions.md)
- [Island NPCs](IslandNPC.md)
- [Minions](Minions.md)
- [Schematic Portals](Schematic-Portal-Islands.md)
- [Storage and Cleanup](Storage-and-Cleanup.md)
- [Folia Architecture](Folia-Architecture.md)
- [Troubleshooting](Troubleshooting.md)
