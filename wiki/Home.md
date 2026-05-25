# IslandPortal Wiki

IslandPortal is a Folia-aware Paper plugin for managed skyblock portal islands.

## Pages

- [Folia Architecture](Folia-Architecture)
- [Configuration](Configuration)
- [Schematic Portal Islands](Schematic-Portal-Islands)
- [Commands and Permissions](Commands-and-Permissions)
- [Storage and Cleanup](Storage-and-Cleanup)
- [Troubleshooting](Troubleshooting)

## Runtime Model

IslandPortal creates managed portals with stored ownership, access policies, portal blocks, trigger blocks, and optional support blocks. Default island portals are queued after island creation events and retried if the skyblock plugin is still pasting its island schematic.
