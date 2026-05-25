# Storage and Cleanup

## Stored Data

Portal data is stored under `playerdata`.

Each managed portal stores:

- Portal id.
- Portal type.
- World and base block.
- Facing.
- Owner.
- Island id.
- Default portal flag.
- Access policies.
- Island members.
- Portal frame blocks.
- Trigger blocks.
- Support blocks.

## Cleanup

When an island is deleted or reset, IslandPortal removes matching managed portals. Support blocks from generated islands or schematic islands are tracked and removed with the portal.

## Autosave

Autosave is controlled by `runtime.autosave-interval-minutes`. The dirty flag is atomic and file I/O runs asynchronously.
