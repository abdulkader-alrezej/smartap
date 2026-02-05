# SmartAP


---

## Firmware Downloads

OpenWrt v25.12.0-rc3

| Dongwon T&I DW02-412H (128M) | sysupgrade (SquashFS) | [⬇️ Download](https://github.com/abdulkader-alrezej/smartap/releases/download/ath79-dsa-smartapv42stable-dw02-412h-128m/openwrt-ath79-nand-DSA-SmartAPv42-dongwon_dw02-412h-128m-squashfs-sysupgrade.bin) |

| Dongwon T&I DW02-412H (128M) | Nand (SquashFS-Factory Image) | [⬇️ Download](https://github.com/abdulkader-alrezej/smartap/releases/download/ath79-dsa-smartapv42stable-dw02-412h-128m/openwrt-ath79-nand-DSA-SmartAPv42-dongwon_dw02-412h-128m-squashfs-factory.img) |


---
## Source Code Availability (GPLv2 Compliance)

This device (DW02-412H) has been converted to use the OpenWrt DSA framework.
In compliance with the GNU General Public License v2 (GPLv2), the complete corresponding source code used to build this firmware, including all modifications, is available at the following repository:

| Dongwon T&I DW02-412H (128M) ) | [ LINK ](https://github.com/abdulkader-alrezej/openwrt/tree/dsa-support-Dongwon-dw02-412h) |

---
# Complete Corresponding Source (CCS) for my OpenWrt-based firmware

This repository provides the **Complete Corresponding Source (CCS)** for the OpenWrt-based images I distribute for the following devices:

- **Dongwon T&I DW02-412H (128M)**

⚠️ Based on OpenWrt (GPLv2). Not affiliated with or endorsed by the OpenWrt project.

The goal is to comply with free/open-source licenses (especially **GPLv2**) and to enable anyone to **reproduce the same images** from source.

---

## 💬 Join our Facebook Group
Have questions or want to share your experience with others?  
👉 [Join the Facebook Page](https://www.facebook.com/groups/techtechtech1)

---

## What is included (per target)

- bsdtar
- unzip
- micropython-mbedtls
- micropython-lib

Inside each target folder you will find:

- `configs/diffconfig` — the build configuration that matches the shipped image.
- `feeds.conf` — feed definitions used to fetch packages at build time.
- `files-public/` — public overlay files (e.g., default `/etc/config/*`) required to run the GPL components.
- `patches/` — any local patches I applied to OpenWrt or packages (if any).
- `scripts/build.sh` — a simple, reproducible build script.

There may also be `OPENWRT_COMMIT` and `OPENWRT_REMOTE` indicating the exact OpenWrt tree this build was based on (when applicable).

## What is NOT included (private MicroPython UI)
My **MicroPython-based web UI** and related private code are **not** included here.  
They are separate programs (mere aggregation) and are not derived from GPL code. Therefore, they are not part of the GPLv2 CCS requirement. The distributed commercial image contains that private UI; the publicly published CCS here contains everything required to rebuild the **OpenWrt base** and GPL-covered parts.

> If you rebuild using this CCS, you will get a functional OpenWrt-based image with the open-source components. You can add your own applications locally before building if desired.

## How to rebuild (quick start)
1. Install OpenWrt build prerequisites on your Linux host (gcc, g++, make, zlib, etc.).
2. Build host: Ubuntu 22.04.4 LTS jammy x86_64
3. Clone or unpack an OpenWrt buildroot matching the intended device and enter it, e.g.:
   ```bash
   
   sudo apt upgrade
   sudo apt update
   .
   sudo apt install build-essential clang flex bison g++ gawk \
   gcc-multilib g++-multilib gettext git libncurses5-dev libssl-dev \
   python3-setuptools rsync swig unzip zlib1g-dev file wget qemu-utils
   .
   git clone https://github.com/openwrt/openwrt.git openwrt
   cd openwrt
   git pull
   git tag
   git checkout v25.12.0-rc3
   git describe --tags
   v25.12.0-rc2
   ./scripts/feeds update -a
   ./scripts/feeds install -a
   make menuconfig
   Target System	 >  Atheros ATH79
   Sub-target	 >  Generic devices with NAND flash
   Target Profile > Dongwon T&I DW02-412H (128M)
   ./scripts/feeds update -a
   ./scripts/feeds install bsdtar unzip micropython-mbedtls micropython-lib
   ./scripts/feeds update -a
   ./scripts/feeds install -a

---

<img width="1921" height="1040" alt="image" src="https://github.com/user-attachments/assets/0798c44e-8179-4ce4-afc2-18a555ee8d96" />


