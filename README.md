# Flipper — Cardputer ADV (Public) · Web Flasher

Flash the **public** Flipper port for the **M5Stack Cardputer ADV** straight from your browser — no drivers, no Python, no command line.

👉 **[Open the flasher](https://stonervpn-design.github.io/cardputer-adv-flipper-webflasher/)** in desktop **Chrome** or **Edge**, plug in via USB‑C data cable, click **Connect & Install**.

## What this is

- **Public build:** the in-tree ProtoPirate car‑key SubGHz decoders and the **CAN Commander** (OBD/CAN) app are removed. The **Defender** RF attack detector and everything else stay; the community standalone **ProtoPirate** app is included.
- **App image, ESP32‑S3**, merged at offset `0x0`.

## ⚠️ You need a microSD card

Unlike the M5Stick build, the Cardputer keeps its databases on a **real microSD card**, not internal flash. **[Download `sd_content.zip`](./sd_content.zip)** and extract it to the **root of a FAT32 microSD** so the card root has `/subghz`, `/nfc`, `/infrared`, and `/Manifest`. Without it, SubGHz KeeLoq decoding, NFC dictionaries, and IR universal remotes won't work. (The loose files are also in [`sd_content/`](./sd_content).)

The `sd_content/` set is **public databases only** (`keeloq_mfcodes_user`, `dangerous_settings`, NFC dicts, IR databases). Proprietary encrypted keystores (`keeloq_mfcodes`, `alutech_at_4n`, `nice_flor_s`) are intentionally excluded.

## Requirements

- M5Stack Cardputer ADV + microSD (FAT32)
- USB‑C **data** cable (not charge‑only)
- Desktop **Chrome** or **Edge** (Web Serial). Firefox, Safari, and phones can't flash — use the manual `esptool` method in `HOW-TO-SETUP-AND-FLASH.txt`.

## Updating

Replace `Flipper-cardputer_adv-public-merged.bin` (keep the filename) and bump `version` in `manifest.json`; GitHub Pages redeploys on push.

See **HOW-TO-SETUP-AND-FLASH.txt** for full step‑by‑step, hosting, and troubleshooting.
