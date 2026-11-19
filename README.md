# OnixOS

A minimal operating system built from the ground up for the **x86_64** architecture.

## Goals
- Develop our own bootloader instead of relying on GRUB or Limine.
- Build a freestanding kernel in C and Assembly.
- Test each milestone in QEMU.
- Keep the system small, understandable, and documented.

## Repository layout
- `boot/` — bootloader source.
- `kernel/` — kernel source and linker script.
- `docs/` — architecture notes and development roadmap.

## Status
The repository structure and initial roadmap are in place. The firmware target (UEFI or legacy BIOS) and boot protocol still need to be selected before implementing executable boot code.

See [docs/ROADMAP.md](docs/ROADMAP.md) for the milestones.
