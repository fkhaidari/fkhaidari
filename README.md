C++ engineer working on the RISC-V debug toolchain (OpenOCD, GDB, the Spike simulator) and on debug info for hardware designs.

I designed [uhdi](https://github.com/fkhaidari/uhdi), a debug-info format for Chisel designs, and built it into CIRCT. `firtool --emit-uhdi` emits it, and the converters in the repo turn it into hgdb, HGLDD (Tywaves) and ChiselTrace PDG.

### Upstream

**OpenOCD** ([riscv-openocd commits](https://github.com/search?q=repo%3Ariscv-collab%2Friscv-openocd+author-name%3A%22Farid+Khaydari%22&type=commits), [openocd.org Gerrit](https://review.openocd.org/q/(message:khaydari+OR+owner:%22Farid+Khaidari%22)+status:merged)): RISC-V memory access. One access path for reads and writes, an abstract-command cache, address-translation drivers, privilege and MPRV handling for program-buffer access, and hardware-translated virtual access through `aamvirtual`.

**GDB** ([patches](https://inbox.sourceware.org/gdb-patches/?q=f%3Akhaidari+s%3APATCH+-s%3ARe)): analysing a RISC-V core file without the executable (ISA features from `AT_HWCAP`, FLEN from the `NT_FPREGSET` note size) and an `arch=` option for the RISC-V disassembler.

**Spike** ([PRs](https://github.com/riscv-software-src/riscv-isa-sim/pulls?q=is%3Apr+author%3Afkhaidari)): RISC-V Debug Spec. Abstract register and memory access that keeps hart state intact, `mcontrol6` triggers, and fixes to Debug Mode entry and exit.
