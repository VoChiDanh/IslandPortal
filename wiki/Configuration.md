# Configuration

IslandPortal writes four editable files on first startup.

## `config.yml`

- `enabled`: master switch.
- `debug`: console diagnostics for placement and cleanup.
- `hooks.bentobox`: enables BentoBox island events.
- `hooks.superior-skyblock`: enables SuperiorSkyblock2 island events.
- `hooks.skyllia`: enables Skyllia island events.
- `commands.description`: command description registered with Paper commands.
- `commands.aliases`: aliases such as `ip`.
- `runtime.autosave-interval-minutes`: async autosave interval.
- `runtime.vanilla-portal-cooldown-ticks`: cooldown applied to suppress vanilla Nether behavior.
- `runtime.use-cooldown-millis`: per-player portal action cooldown.
- `runtime.portal-near-scan`: lookup radius for shifted portal event positions.
- `creation-delay-ticks`: first delay after island creation before default portal placement.
- `creation-retry-attempts`: retry count if placement is not ready yet.
- `creation-retry-delay-ticks`: delay between retries.
- `island-cleanup-radius`: fallback cleanup radius when an exact island id is unavailable.

## `portals.yml`

Each portal type has:

- Item metadata.
- Portal frame shape and materials.
- Island offset and facing.
- Optional generated or schematic portal island.
- Default creation toggle.
- Consume and break return behavior.
- Access policy defaults.
- Permission nodes.
- Teleport or command action.

## `menus.yml`

Controls the settings GUI title, size, item layout, display names, lore, and click actions.

## `messages.yml`

Controls command messages and player-facing interaction messages.
