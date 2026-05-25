# Commands and Permissions

## Permission

```text
islandportal.admin
```

## Commands

```text
/islandportal help
/islandportal reload
/islandportal settarget <type>
/islandportal give <type> <player> [amount]
/islandportal create <type>
/islandportal createisland <type>
/islandportal remove
```

Aliases are configured in `config.yml`.

## Portal Permissions

Each portal type can define permission nodes for:

- `place`
- `use`
- `pickup`
- `configure`

Empty permission strings disable that specific permission check.
