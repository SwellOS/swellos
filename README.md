# SwellOS

**Your system. Your rules.**

SwellOS is an independent, ultra-lightweight Linux distribution based on LFS/BLFS. Source-based, rolling release, optimized for modern x86_64 hardware.

| Component | Choice |
|-----------|--------|
| Kernel | Swell kernel (monolithic, performance-patched, no modules) |
| Init | runit |
| Desktop | KDE Plasma on Wayland |
| Package manager | sbpm (source-based, Rust) |
| Audio | PipeWire |
| Filesystem | Ext4 |
| Installer | TUI (swell-install) |

## Quick start

```bash
git clone --recurse-submodules https://github.com/SwellOS/swellos.git
cd swellos
```

## Repositories

| Repo | Description |
|------|-------------|
| [kernel](https://github.com/SwellOS/kernel) | Swell kernel fork |
| [packages](https://github.com/SwellOS/packages) | Package build scripts |
| [sbpm](https://github.com/SwellOS/sbpm) | Package manager |
| [swell-installer](https://github.com/SwellOS/swell-installer) | TUI installer |
| [swell-build](https://github.com/SwellOS/swell-build) | Build system |
| [docs](https://github.com/SwellOS/docs) | Documentation |

## License

Kernel: GPLv2. Tooling: MIT.
