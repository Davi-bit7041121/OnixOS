# OnixOS UEFI boot design

## Initial target
- Firmware: UEFI
- Architecture: x86_64
- Executable format: PE32+ (EFI application)
- Initial implementation language: C
- Assembly: reserved for later low-level routines when needed

## Boot flow
1. UEFI firmware loads `bootx64.efi` from the EFI System Partition.
2. The OnixOS EFI application receives an `EFI_HANDLE` and the `EFI_SYSTEM_TABLE`.
3. The application uses UEFI Boot Services to inspect the environment and load the kernel.
4. Before leaving boot services, the loader obtains the UEFI memory map.
5. The loader calls `ExitBootServices` and transfers control to the kernel entry point using a documented calling convention.

## Important constraints
- UEFI x86_64 applications use the Microsoft x64 calling convention.
- The x86_64 UEFI environment is already in 64-bit mode.
- The loader must not assume a fixed memory map.
- The kernel handoff contract, memory layout, and ELF/PE loading strategy must be specified before implementing the final handoff.
- All early tests should run in an emulator such as QEMU.

## First implementation milestone
Build a minimal EFI application that prints a message using the UEFI console protocol. This validates the compiler, linker, EFI entry point, and QEMU firmware setup before kernel loading is added.
