# SwellOS v0.1-alpha — "Swell Inlet"

**Release date:** 2026-06-22

This is the first public alpha release of SwellOS — an independent, source-based GNU/Linux distribution built from scratch.

## What's included

All 9 milestones for v0.1 are complete:

### Core system
- **Swell kernel** — monolithic x86_64 kernel (CONFIG_MODULES=n), PREEMPT, NO_HZ_FULL, ZSTD, all common drivers built-in
- **runit** — fast service supervision init system
- **sbpm** — Rust-based binary package manager (install, remove, upgrade, freeze, search)
- **LFS baseline** — 16 core packages (linux-api-headers → glibc → binutils → gcc → CLI tools + runit + sbpm)

### Desktop
- **Infrastructure** — dbus, elogind, polkit, Wayland, Xorg, PipeWire, WirePlumber, Mesa, libinput, NetworkManager
- **Environments** — KDE Plasma 6, Hyprland, i3, WindowMaker
- **Metapackages** — kde-plasma, gnome, xfce4, hyprland, i3, windowmaker, swell-desktop, swell-dev, swell-browser, swell-gaming, swell-multimedia, swell-office

### Applications (27 packages)
- **Browsers:** Firefox 135, Chromium 133
- **Dev tools:** LLVM 19, Rust 1.83, Git, CMake, Python 3.13, Vim, Nano
- **Gaming:** Steam, Wine 10.0, DXVK 2.4.1, MangoHud 0.8.0
- **Multimedia:** FFmpeg 7.1, GIMP 2.10, OBS Studio 31, Blender 4.3, Audacity 3.7
- **Office:** LibreOffice 24.8, Thunderbird 128
- **Network:** OpenSSH 9.9, dhcpcd 10.1, wpa_supplicant 2.11, iwd 3.2

### Tooling
- **swell-build** — Rust build system: `pkg`, `world -j N`, `repo`, `list`, `info`, `clean`, `iso`
- **swell-install** — Rust TUI installer with partition management and metapackage selection
- **ISO generation** — `swell-build iso` creates bootable live ISO (GRUB+UEFI, initramfs, busybox, squashfs)

## Repository layout

All code is under the [SwellOS](https://github.com/SwellOS) GitHub organization:

| Repo | Description |
|------|-------------|
| `swellos` | Meta-repo with submodules |
| `kernel` | Kernel config, build scripts, CI |
| `sbpm` | Package manager (Rust) |
| `swell-build` | Build system + ISO generation (Rust) |
| `swell-installer` | TUI installer (Rust) |
| `packages` | 59 build scripts across 8 categories |
| `docs` | LFS-style documentation |
| `website` | swellos.github.io source |

## Quick start

```bash
# Clone meta-repo
git clone https://github.com/SwellOS/swellos.git
cd swellos && git submodule update --init --recursive

# Build sbpm
cd sbpm && cargo build --release

# Build kernel
cd ../kernel && ./scripts/build.sh

# Build all packages
cd ../swell-build && cargo build --release
./target/release/swell-build world -j $(nproc)

# Generate repo + ISO
./target/release/swell-build repo
./target/release/swell-build iso -K /path/to/bzImage -f
```

## Known limitations (alpha)

- Packages have not been integration-tested end-to-end
- Desktop environments (especially monolithic KDE Plasma) may require additional dependency packages
- The live ISO requires a pre-built busybox binary on the build host
- No binary package repository is available yet — all packages must be built from source

## Upcoming

- Binary package repository at packages.swellos.org
- Pre-built ISO downloads
- User documentation book
- Community contribution guidelines

---

[SwellOS website](https://swellos.github.io) · [GitHub organization](https://github.com/SwellOS) · [Package catalog](https://github.com/SwellOS/packages)
