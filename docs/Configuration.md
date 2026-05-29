# Configuration

IslandPortal is highly customizable. Upon first startup, the plugin generates four editable configuration files in the `plugins/IslandPortal/` directory.

---

## ⚙️ `config.yml`

This is the main configuration file for the plugin's runtime behavior and integrations.

```yaml
# Master switch to enable or disable the plugin
enabled: true

# Enable to output console diagnostics for placement, schematics, and cleanup
debug: false
```

### Hooks & Integrations

Enable the hooks that match your Skyblock engine. Only enable the ones you have installed!

```yaml
hooks:
  bentobox: true
  superior-skyblock: false
  skyllia: false
```

### Commands

Customize how players interact with the plugin command.

```yaml
commands:
  description: "IslandPortal main command"
  aliases: ["ip", "isportal"]
```

### Runtime Settings

These control the core loop and interaction delays.

```yaml
runtime:
  # How often to asynchronously save portal data to disk
  autosave-interval-minutes: 15
  
  # Prevents vanilla nether logic from firing (increase if players get sent to the nether)
  vanilla-portal-cooldown-ticks: 40
  
  # How long a player must wait between portal uses
  use-cooldown-millis: 2000
  
  # The lookup radius to detect portals around a player
  portal-near-scan: 2
```

### Island Creation & Placement

Control how the plugin queues its portal placement after an island is created.

```yaml
# Delay after island creation before first default portal placement attempt
creation-delay-ticks: 20

# How many times to retry if the skyblock plugin is still pasting
creation-retry-attempts: 5

# Delay between retries
creation-retry-delay-ticks: 40

# Fallback cleanup radius when an exact island ID is unavailable
island-cleanup-radius: 50
```

---

## 🚪 `portals.yml`

This file defines your custom **Portal Types**. Each portal type contains detailed configurations:

- **Item Metadata:** Name, lore, and material for the portal item.
- **Shape & Materials:** The block frame shape and materials required.
- **Placement:** Island offset and facing direction.
- **Island Mode:** Use generated blocks or a `.schem` file.
- **Defaults:** Default creation toggles and access policy defaults.
- **Actions:** Whether entering the portal executes a command or teleports the player.

---

## 🖼️ `menus.yml`

IslandPortal provides an in-game settings GUI. This file controls:

- The GUI Title and Size.
- Item layouts and slots.
- Display names, lore, and materials for the buttons.
- Click actions and sound effects.

---

## 💬 `messages.yml`

Customize all command messages and player-facing interactions. Supports modern color codes and formatting.
