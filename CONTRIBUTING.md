# Contributing

## Development Requirements

- Java 25.
- Paperweight userdev through Gradle.
- `./gradlew build` must pass before opening a pull request.

## Folia Rules

- Use `PlatformScheduler` for task dispatch.
- Use entity scheduler dispatch for player inventory, GUI, and state changes.
- Use region scheduler dispatch for block reads and writes.
- Use async chunk loading before region work.
- Use `teleportAsync` for teleport behavior.
- Keep player-facing text configurable in `messages.yml`, `menus.yml`, `portals.yml`, or `config.yml`.

## Pull Requests

Keep changes focused. Include config examples for new behavior and update the wiki when behavior changes.
