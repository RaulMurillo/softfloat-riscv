# softfloat-riscv

Berkley [SoftFloat](http://www.jhauser.us/arithmetic/SoftFloat.html) and
[TestFloat](http://www.jhauser.us/arithmetic/TestFloat.html) for emulating and
testing floating point routines.

This repository combines both and adds explicit support for RISC-V.

For SoftFloat this mean the specialization of the software floating routines to
match RISC-V specified behavior.

For TestFloat this means adding a generic `RISCV` build target.

Both softwares are modified to *emulate* RISC-V behavior, not to be run on RISC-V machines. For that, the a different compiler should be used (see the `Makefile`).

To build and run the modified libraries, execute:
```bash
cd SoftFloat-3e/build/Linux-RISCV-GCC
make all
cd ../../../TestFloat-3e/build/Linux-RISCV-GCC/
make all
./testfloat_gen -rnear_even f64_mulAdd
```
