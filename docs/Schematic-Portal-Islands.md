# Schematic Portal Islands

IslandPortal lets you go beyond simple block frames. You can paste an entire custom schematic around the portal frame!

---

## 📦 Bundled Schematics

The plugin comes with two sample schematics. They are copied to the plugin data folder on first startup:

1. `schematics/spawn_portal_island.schem` - A basic default portal island.
2. `schematics/track_only_portal_island.schem` - A larger track-only sample.

For production use, place your own `.schem` files under `plugins/IslandPortal/schematics` and update your `portals.yml`.

---

## 🎨 Enabling Schematic Mode

To make a portal paste a schematic instead of generating simple blocks, update the `portal-island` section for your portal type in `portals.yml`:

```yaml
portal-island:
  enabled: true
  mode: SCHEMATIC
  schematic: "schematics/spawn_portal_island.schem"
  schematic-ignore-air: true
  vertical-align:
    enabled: true
    schematic-anchor-y: 0
    y-offset: 0
  portal-offset:
    x: 3
    y: 4
    z: 4
```

!!! note "How it Works"
    The schematic builds the island support structure. The **managed portal frame and trigger blocks** are still created by IslandPortal *after* the paste. This ensures default portal detection, access checks, cleanup, and persistence remain reliable.

---

## 🏗️ Full Custom Portal (Track Only Mode)

If your schematic *already contains* the exact portal frame and portal blocks inside it, you can enable `track-only` mode.

```yaml
portal:
  width: 2
  height: 3
  frame-material: OBSIDIAN
  portal-material: NETHER_PORTAL
  replace-only-air: false
  track-only: true

portal-island:
  schematic: "schematics/track_only_portal_island.schem"
  portal-offset:
    x: 6
    y: 5
    z: 3
  vertical-align:
    enabled: true
    schematic-anchor-y: 4
    y-offset: 0
```

In `track-only` mode, IslandPortal **does not replace schematic blocks**. It only registers the frame area and inner trigger area as a managed portal so they function properly.

!!! warning "Nether Portal Interception"
    If `portal-material` is set to `NETHER_PORTAL`, IslandPortal intercepts the vanilla Nether logic and routes the player through the configured custom action instead.

---

## 📍 Placement Search

When pasting, IslandPortal searches for a safe location starting from the configured `island-offset` plus any random distance. 

If you want the schematic to paste at an **exact custom location**, set `random-distance.min`, `random-distance.max`, and `search-radius` to `0`.

---

## 📏 Vertical Alignment

Use `vertical-align` when a custom schematic appears too high or too low compared to the main island.

- `enabled`: aligns the schematic to the island location Y.
- `schematic-anchor-y`: the relative Y level inside the schematic that should become level with the main island.
- `y-offset`: final adjustment after alignment. Use a negative value to lower the pasted portal island.

### Examples

**Example 1:** Moving the entire paste down 4 blocks.
```yaml
vertical-align:
  enabled: true
  schematic-anchor-y: 0
  y-offset: -4
```

**Example 2:** If the schematic origin is at the bottom, but the walking surface is 8 blocks above the origin.
```yaml
vertical-align:
  enabled: true
  schematic-anchor-y: 8
  y-offset: 0
```

---

## 🔄 Fallback Behavior

If WorldEdit or FastAsyncWorldEdit (FAWE) is not installed, or if the schematic cannot be loaded, IslandPortal falls back to the basic generated platform mode safely.
