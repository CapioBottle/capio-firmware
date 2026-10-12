# Capio bottle firmware releases

Firmware updates for the Capio smart pill bottle. The Capio iOS app reads
[`latest.json`](latest.json) to find the newest version and installs it on
the bottle over Bluetooth. You don't need to download anything here yourself.

## What is in each release

- **`capio_v<version>_dfu.zip`**: the signed update package. Bottles only
  accept packages signed by Capio, so a modified or damaged file is rejected
  and the bottle keeps its current firmware.
- **`capio_v<version>_lgpl_relink.zip`**: the files you need to rebuild that
  firmware with your own version of the Arduino nRF5 core, as the GNU LGPL
  v2.1 requires. It holds Capio's compiled object files, the library source
  and a rebuild script. See the README inside.

## `latest.json`

```json
{
  "schema": 1,
  "version": "2.0.7",
  "url": "https://github.com/CapioBottle/capio-firmware/releases/download/v2.0.7/capio_v2.0.7_dfu.zip",
  "sha256": "…",
  "size": 163980,
  "minBottleVersion": "2.0.0",
  "releasedAt": "2026-10-11",
  "notes": "…"
}
```

`minBottleVersion` is the oldest bottle firmware that can take this update
over the air. Bottles on firmware 1.x can't update over the air.

## Licences

The Capio firmware is proprietary. Copyright © Capio. All rights reserved.
It includes open-source components: the Arduino nRF5 core (GNU LGPL v2.1),
the Nordic Semiconductor nRF5 SDK and SoftDevice S132 (Nordic 5-Clause
License, for Nordic chips only), Arm CMSIS, micro-ecc (BSD 2-Clause) and the
Work Sans font (SIL Open Font License 1.1). The full notices are in the Capio
app under Settings → Credits.
