# Commands and Permissions

IslandPortal keeps its command structure simple but powerful. 

---

## 🛡️ Administrative Permission

To access administrative commands, players or groups need the following permission node:

```text
islandportal.admin
```

---

## ⌨️ Commands

By default, the main command is `/islandportal` (aliased to `/ip` via `config.yml`).

| Command | Description |
|---------|-------------|
| `/ip help` | Shows the help menu with all available commands. |
| `/ip reload` | Reloads all configuration files seamlessly. |
| `/ip settarget <type>` | Sets the teleport target for a specific portal type to your current location. |
| `/ip give <type> <player> [amount]` | Gives the specified portal item to a player. |
| `/ip create <type>` | Force creates a managed portal of the given type at your location. |
| `/ip createisland <type>` | Force creates a full portal island of the given type at your location. |
| `/ip remove` | Removes the managed portal you are currently looking at. |

---

## 🔑 Portal Specific Permissions

Beyond administrative commands, each individual **Portal Type** can define unique permission nodes in `portals.yml`. 

You can restrict who can do what with specific portal types:

- `place`: Permission to place the portal item and generate the portal.
- `use`: Permission to trigger the portal action (teleport/command).
- `pickup`: Permission to break the portal and pick it back up.
- `configure`: Permission to open the portal's settings GUI.

!!! info "Disabling Permission Checks"
    If you leave a permission string empty (`""`) in `portals.yml`, the plugin will bypass the check and allow everyone to perform that action.
