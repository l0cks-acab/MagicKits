# MagicKits

**Version:** 1.2.0  
**Author:** opaque.poppy & herbs.acab

Technically not the traditional kit plugin, however is used for convenient "spawn" kits, with minimal impact on server performance.

---

## Features

- Custom starter kits defined per permission group (e.g., `starterkit.admin`, `starterkit.2`, `starterkit.1`).
- Default starter kit fallback.
- Automatically removes default rock and torch from inventories on respawn.
- Fully configurable via JSON config file.

---

## Installation

1. Download or create the `MagicKits.cs` plugin file.
2. Place `MagicKits.cs` into your Rust server's `oxide/plugins` directory.
3. Start or restart your Rust server, or use the command: oxide.reload MagicKits
4. The plugin will generate a configuration file by default at: oxide/config/MagicKits.json

---

## Configuration

Edit the configuration file to customize starter kits per permission group:

Example config section:
"StarterKits": {
    "default": {
      "stones": 100,
      "wood": 200,
      "spear": 1,
      "cloth": 50
    },
    "1": {
      "stones": 150,
      "wood": 300,
      "bow.hunting": 1,
      "cloth": 75
      },
    "2": {
      "stones": 200,
      "wood": 400,
      "spear": 2,
      "cloth": 100,
      "arrow.wooden": 50
    },
    "admin": {
      "stones": 500,
      "wood": 1000,
      "gun.pistol": 1,
      "ammo.pistol": 100,
      "cloth": 200
    }
}

- Keys are permission group names.
- Values are dictionaries of Rust item shortnames and quantities.

---

## Permissions

Use Oxide/uMod permissions to assign starter kits:

- `starterkit.admin` — grants the "admin" kit on respawn.
- `starterkit.2` — grants the "2" kit.
- `starterkit.1` — grants the "1" kit.
- Players without any of these permissions receive the `"default"` kit.

Example to grant permission via server console or RCON: oxide.grant user <player_steamid> starterkit.admin


---

## Usage

- Players receive their configured starter kits automatically upon respawning.
- The plugin removes the default rock and torch, replacing them with the configured items.

---

## Troubleshooting

- Ensure the plugin is properly installed in `oxide/plugins`.
- Confirm permission assignments with Oxide commands.
- Check server and oxide logs for warnings or errors.
- Modify the config carefully; JSON syntax errors will cause config load failure.

---

## Support

For issues or feature requests, please contact **opaque.poppy**

---

## Setup Instructions (chad edition)

1. Upload `MagicKits.cs` to your Rust server’s `oxide/plugins` folder.
2. Restart the server or run `oxide.reload MagicKits` in the console.
3. Locate the config file `oxide/config/MagicKits.json` and edit it to set starter kits for each permission group.
4. Use Oxide commands to assign permissions to players, e.g., `oxide.grant user <steamid> starterkit.admin`.
5. Players will get their assigned kits automatically when they respawn.
6. To update kits, edit the config and reload the plugin again.




