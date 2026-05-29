# Troubleshooting

If things aren't working as expected, check the common issues below.

---

## ❌ Portal Island Does Not Spawn

If a new island is created but the portal island doesn't appear:

1. **Check the Debug Log:** Set `debug: true` in your `config.yml` and restart. The console will print exactly why placement fails.
2. **Missing Dependencies:** Ensure **WorldEdit** or **FastAsyncWorldEdit (FAWE)** is installed if you are using `mode: SCHEMATIC`.
3. **Missing File:** Verify the `.schem` file exists under the `plugins/IslandPortal/schematics/` folder.
4. **Not Enough Space:** The candidate area might not have enough air clearance to paste the schematic.
5. **Skyblock Paste Delay:** Your skyblock plugin might be taking too long to paste its own island. Try increasing `creation-delay-ticks`, `creation-retry-attempts`, and `creation-retry-delay-ticks` in `config.yml`.

---

## ❌ Portal Does Not Teleport

If players walk into a portal but nothing happens:

1. **Check Action Mode:** Verify `action.mode` is set to `TELEPORT` in `portals.yml`.
2. **World Not Loaded:** Ensure the `action.target.world` exists and is loaded.
3. **Permissions & Policies:** Ensure the player has the correct permission node and passes the portal's access policy settings.

---

## 🔥 Vanilla Nether Travel Happens Instead

If a custom portal sends players to the actual Nether instead of the configured target:

1. **Increase Cooldown:** Increase `runtime.vanilla-portal-cooldown-ticks` in `config.yml`.
2. **Untracked Portal:** Check if the portal is properly tracked. You can do this by looking at it and typing `/ip remove` (as admin) to see if it registers as a managed portal. If it's not managed, it will behave like a vanilla Nether portal.

---

## ⚠️ Folia Region Warnings

If you see region ownership warnings in your console on Folia:

1. **Update Plugin:** Ensure you are using the latest build of IslandPortal.
2. **Keep Schematics Compact:** Ensure your portal island schematics are compact enough to fit entirely inside one chunk (16x16 blocks) along with their required clearance.
