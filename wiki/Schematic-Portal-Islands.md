# Schematic Portal Islands

## Default Schematic

The plugin bundles:

```yaml
schematics/spawn_portal_island.schem
```

It is copied to the plugin data folder on first startup.

## Enabling Schematic Mode

```yaml
portal-island:
  enabled: true
  mode: SCHEMATIC
  schematic: "schematics/spawn_portal_island.schem"
  schematic-ignore-air: true
  portal-offset:
    x: 3
    y: 4
    z: 4
```

The schematic builds the island support structure. The managed portal frame and trigger blocks are still created by IslandPortal after the paste, which keeps default portal detection, access checks, cleanup, and persistence reliable.

## Fallback Behavior

If WorldEdit or FastAsyncWorldEdit is not installed, or the schematic cannot be loaded, IslandPortal falls back to generated platform mode.

## Folia Boundary Rule

The full schematic bounds, portal frame, and clearance area must fit inside one chunk for a placement candidate to be used. Candidates crossing chunk boundaries are skipped.
