# OnixOS — Roadmap

OnixOS is a minimal operating system built from the ground up for x86_64.

## Project principles
- Write and understand our own boot path; do not use GRUB, Limine, or another bootloader as the final bootloader.
- Build a small freestanding kernel in C, with Assembly where processor setup requires it.
- Test safely in QEMU before considering real hardware.
- Keep each milestone small, documented, and reproducible.

## Milestones
1. **Development environment:** compiler/toolchain, assembler, linker, Makefile, and QEMU.
2. **Boot design:** choose and document the initial firmware target (UEFI or legacy BIOS).
3. **Bootloader:** load the kernel and transfer control to its entry point.
4. **Kernel entry:** establish a known CPU state and produce the first diagnostic output.
5. **CPU foundations:** GDT, IDT, exceptions, and interrupt handling.
6. **Memory management:** physical memory map, page frames, and virtual memory.
7. **Drivers and devices:** timer, keyboard, and storage foundations.
8. **Processes and filesystem:** introduce multitasking and persistent data.

## Current status
- [x] Repository created.
- [ ] Development environment verified.
- [ ] Firmware target selected.
- [ ] First bootable image.
- [ ] Kernel entry confirmed in QEMU.

No milestone is considered complete until it has been built and tested.
