This repository contains patches that can be used to add Embedded Go supported architectures to the [reference Go compiler](https://golang.org). The alternate way to try Embedded Go is to clone https://github.com/embeddedgo/go repository.

Currently supported architectures:

| GOOS/GOARCH | Target                                       |
| ----------- | ---------------------------------------------|
| linux/thumb | Linux on ARMv7-A (mainly for tests)          |
| noos/thumb  | ARMv7-M microcontrollers (nFR52, STM32, ...) |

#### How to install

1. Download selected patch or the whole rpository:

```
git clone https://github.com/embeddedgo/patch
```

2. Download Go compiler:

```
git clone https://go.googlesource.com/go goroot
```

3. Apply patch and build the Go distribution:

```
cd goroot
git checkout go1.14.2
patch -p1 <../patch/go1.14.2
cd src
./all.bash
```

4. See more info on https://golang.org/doc/install/source and https://embeddedgo.github.io/getting_started
