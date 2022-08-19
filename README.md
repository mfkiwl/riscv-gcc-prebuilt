# Prebuilt RISC-V GCC toolchains

[![Test Toolchains](https://github.com/stnolting/riscv-gcc-prebuilt/workflows/Test%20Toolchains/badge.svg)](https://github.com/stnolting/riscv-gcc-prebuilt/actions)
[![license](https://img.shields.io/github/license/stnolting/riscv-gcc-prebuilt)](https://github.com/stnolting/riscv-gcc-prebuilt/blob/master/LICENSE)
[![Gitter](https://img.shields.io/badge/Chat-on%20gitter-4db797.svg?longCache=true&logo=gitter&logoColor=e8ecef)](https://gitter.im/neorv32/community)

The toolchains were built according to the instructions of the
[official RISC-V GNU Compiler Toolchain repository](https://github.com/riscv-collab/riscv-gnu-toolchain)
using **Ubuntu 20.04 LTS** on a **64-bit x86 machine** (actually on Ubuntu on Windows). The compressed toolchain archives
are available as [releases](https://github.com/stnolting/riscv-gcc-prebuilt/releases) assets.

These prebuilt toolchains are used by the [NEORV32 RISC-V Processor](https://github.com/stnolting/neorv32) project.


## Available Toolchains

Toolchain prefix: `riscv32-unknown-elf` or `riscv64-unknown-elf`

| Release (tag)    | Download archive | GCC | binutils | march   | mabi | clib |
|:-----------------|:-----------------|:---:|:--------:|:-------:|:----:|:----:|
| :heavy_check_mark: [rv64imc-3.0.0](https://github.com/stnolting/riscv-gcc-prebuilt/releases/tag/rv64imc-3.0.0) | [:floppy_disk: download](https://github.com/stnolting/riscv-gcc-prebuilt/releases/download/rv64imc-3.0.0/riscv64-unknown-elf.gcc-12.1.0.tar.gz) (.tar.gz) | `12.1.0` | `2.39` | multilib: `rv32i`, `rv32ic`, `rv32im`, `rv32imc` | `ilp32`  | `newlib` |
| :x: [rv32i-2.0.0](https://github.com/stnolting/riscv-gcc-prebuilt/releases/tag/rv32i-2.0.0) | [:floppy_disk: download](https://github.com/stnolting/riscv-gcc-prebuilt/releases/download/rv32i-2.0.0/riscv32-unknown-elf.gcc-10.2.0.rv32i.ilp32.newlib.tar.gz) (.tar.gz) | `10.2.0` | `2.35` | `rv32i` | `ilp32`  | `newlib` |
| :x: [rv32e-1.0.0](https://github.com/stnolting/riscv-gcc-prebuilt/releases/tag/rv32e-1.0.0) | [:floppy_disk: download](https://github.com/stnolting/riscv-gcc-prebuilt/releases/download/rv32e-1.0.0/riscv32-unknown-elf.gcc-10.1.0.rv32e.ilp32e.newlib.tar.gz) (.tar.gz) | `10.1.0` | `2.34` | `rv32e` | `ilp32e` | `newlib` |

* :heavy_check_mark: most recent
* :x: outdated


## Download

### Via Browser

Click on the according **download** link in the table above to directly download the archive of choice
from the according [release page](https://github.com/stnolting/riscv-gcc-prebuilt/releases) via the release _assets_.

### Via Command Line

You can use `wget` to directly download a toolchain archive from the table above. Select the toolchain of
choice, right-click on the **download** link, click "copy link address" and use that as argument for `wget`. Example:

    $ wget https://github.com/stnolting/riscv-gcc-prebuilt/releases/download/rv32i-1.0.0/riscv32-unknown-elf.gcc-10.1.0.rv32i.ilp32.newlib.tar.gz

:warning: A `git clone` of the repository will **not** include the release assets so it will **not include the actual toolchain archives**!


## Installation

Create a folder where you want to install the toolchain, for example `/opt/riscv` (you will need
`sudo` rights to create this folder and copy data to it).

    $ sudo mkdir /opt/riscv

Navigate to the download folder. Decompress your toolchain (replace `TOOLCHAIN` with your toolchain archive
of choice). Again, you might have to use `sudo` if your target directory is protected.

    $ sudo tar -xzf TOOLCHAIN.tar.gz -C /opt/riscv/

Now add the toolchain's `bin` folder to your system's `PATH` environment variable (or add this line to your `.bashrc` if applicable):

    $ export PATH=$PATH:/opt/riscv/bin

Test the toolchain:

    $ riscv32-unknown-elf-gcc -v


## License

This project is released under the [GPL-2.0 license](https://github.com/stnolting/riscv-gcc-prebuilt/blob/master/LICENSE).
No copyright infringement intended.
Other implied or used projects might have different licensing - see their documentation to get more information.

#### Limitation of Liability for External Links

Our website contains links to the websites of third parties ("external links"). As the
content of these websites is not under our control, we cannot assume any liability for
such external content. In all cases, the provider of information of the linked websites
is liable for the content and accuracy of the information provided. At the point in time
when the links were placed, no infringements of the law were recognizable to us. As soon
as an infringement of the law becomes known to us, we will immediately remove the
link in question.
