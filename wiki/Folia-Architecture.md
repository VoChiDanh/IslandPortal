# Folia Architecture

## Scheduler Layer

All task dispatch goes through `PlatformScheduler`.

- `runGlobal` uses Folia's global region scheduler on Folia and Bukkit's scheduler on Paper.
- `runGlobalLater` and `runGlobalTimer` return a cancellable `PlatformTask`.
- `runAsync` uses Folia's async scheduler on Folia and Bukkit's async scheduler on Paper.
- `runAtLoaded` loads the target chunk asynchronously, then dispatches region-owned logic at the target location.
- `runFor` dispatches player and entity work through the entity scheduler on Folia.

## Entity Safety

Player inventory, GUI, message callbacks, and portal cooldown changes are scheduled through `runFor`. This keeps entity-owned state on the entity scheduler.

## Block Safety

Portal block placement, portal island generation, schematic paste, and cleanup are scheduled through `runAtLoaded`. Portal island placement also rejects candidates whose full clearance bounds cross chunk boundaries, so one region task owns every block it reads and writes.

## Teleport Safety

Portal teleport actions use `teleportAsync`. Failure messages are sent in the completion callback through the player scheduler.

## Storage Safety

Portal state is held in concurrent maps. Autosave uses an atomic dirty flag and runs file I/O asynchronously.
