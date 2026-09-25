# Corne Choc Pro BT ZMK Config — Miryoku-style

This is a firmware-only configuration for Keebart's Corne Choc Pro BT **5×3+3 (36-key)** layout, pinned to ZMK v0.3. The sixth column is optional; this repository currently builds the 5-column variant.

## Build targets

The workflow builds only the matching 5-column targets:

- `corne_choc_pro_5col_left`
- `corne_choc_pro_5col_right`

Normal firmware artifacts:

- `corne_choc_pro_bt_5col_left`
- `corne_choc_pro_bt_5col_right`

The `sharp_mip` shield is included in both normal builds, so the LCD configuration remains part of the firmware. Matching settings-reset artifacts are also built for recovery:

- `corne_choc_pro_bt_5col_left_settings_reset`
- `corne_choc_pro_bt_5col_right_settings_reset`

## Files required for this build

- `.github/workflows/build.yml` — GitHub Actions entry point
- `build.yaml` — 5-column build matrix
- `config/corne_choc_pro_5col.keymap` — 5×3+3 keymap
- `config/corne_choc_pro_5col.conf` — 5-column firmware configuration
- `config/corne_choc_pro_5col.json` — 5-column visual metadata for the ZMK Keymap Editor
- `config/west.yml` — ZMK manifest
- `zephyr/module.yml` — module declaration

The 5-column JSON file is retained for the ZMK Keymap Editor; it is not consumed by the firmware compiler. The regular 6-column keymap is optional and is not part of the current build matrix.

Do not use the generic `corne` shield, `nice_nano_v2` targets, or the regular `corne_choc_pro_left/right` artifacts for this 5-column board.
