# Troubleshooting

## Portal Island Does Not Spawn

Check:

- `debug: true` in `config.yml`.
- WorldEdit or FAWE is installed if using `mode: SCHEMATIC`.
- The configured schematic file exists under the plugin data folder.
- The candidate area has enough air clearance.
- `creation-delay-ticks`, `creation-retry-attempts`, and `creation-retry-delay-ticks` are high enough for the island plugin's schematic paste.

## Portal Does Not Teleport

Check:

- `action.mode` is `TELEPORT`.
- `action.target.world` is loaded.
- The player passes the configured permission and access policy.

## Vanilla Nether Travel Happens

Increase `runtime.vanilla-portal-cooldown-ticks` and confirm the frame blocks belong to a managed portal in `playerdata`.

## Folia Region Warnings

Use the latest build and keep portal island schematics compact enough to fit inside one chunk with clearance.
