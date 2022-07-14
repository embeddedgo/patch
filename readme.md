This repository contains patches that can be used to add Embedded Go supported
architectures to the [reference Go compiler](https://go.dev/).

The main way to install Embedded Go is to use precompiled binary packages. See [embeddedgo.github.io/getting_started](https://embeddedgo.github.io/getting_started) for download links.

The alternate way to try Embedded Go with the last (unstable) changes is to clone the [github.com/embeddedgo/go](https://github.com/embeddedgo/go) repository.

Currently supported architectures:

| GOOS/GOARCH  | Target                                       |
| ------------ | -------------------------------------------- |
| noos/thumb   | ARMv7-M microcontrollers (nFR52, STM32, ...) |
| noos/riscv64 | RV64G SOCs (tested on Kendryte K210)         |
| linux/thumb  | Linux on ARMv7-A (Cortex-A), Thumb2 ISA      |

For `GOARCH=thumb` you can set `GOARM=7` (default, soft float) or `GOARM=7d` (requires 64-bit FPU). `GOARM=7f` (32-bit FPU) is still unsupported.

#### How to install a patch

1. Download the patch that matches your version of Go or the entire repository:

```
git clone https://github.com/embeddedgo/patch
```

2. Download Go compiler:

```
git clone https://go.googlesource.com/go goroot
```

3. Apply a patch and build the Go distribution:

```
cd goroot
git checkout go1.18.4
patch -p1 <../patch/go1.18.4
cd src
./all.bash
```

4. See more info on [embeddedgo.github.io/getting_started](https://embeddedgo.github.io/getting_started) and [golang.org/doc/install/source](https://golang.org/doc/install/source).
