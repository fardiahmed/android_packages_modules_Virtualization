# A16_RISCV/packages/modules/Virtualization: android16-riscv

Changes made for the Android 16 (AOSP, riscv64) bring-up of the BananaPi BPI-F3 (SpacemiT K1) and the BananaPi BPI-SM10 (SpacemiT K3), on branch `android16-riscv`.

AVF for riscv64 (non-protected VMs; no riscv64 pvmfw upstream yet).

## Changes

- **Enable virtmgr and virtualizationservice for riscv64**
- **virt APEX: add a riscv64 variant**: No riscv64 pvmfw/android_bootloader_crosvm or service VM exists upstream yet, so ship only crosvm, virtmgr and virtualizationservice plus the Microdroid filesystems (non-protected VMs).
- **kdump: define the earlycon for riscv64 guests**: crosvm's riscv64 backend maps the serial port like aarch64 (mmio at 0x3f8).

## Build

```
./build.sh k1   # BPI-F3 (K1): kernel, bootloaders and Android images
./build.sh k3   # BPI-SM10 (K3), not booted yet
```

`./build.sh --help` lists the options (`--skip-kernel`, `--kernel-only`, ...).
