August, 2016, designed in Labitat in Copenhagen.

Schematic and layout for board with SDRAM and SD card reader that plugs in to the Lattice HX8K Breakout Board and remaing GPIO routed to a header.

The RAM Tested and working with a modified version of Lattice's example SDRAM controller[0], with memtest running from an STM32F4 expansion board that also plugs into the HX8K Breakout. The SD card reader has not been tested.

HOWEVER, for rev. A (see git history): Some of the pins on the HX8K expansion headers are also used for other functions. Particular, as routed D0 is also connected to the FTDI chip. Fortunately, GPIO6 is right next to it, so you can just cut off pin 12 on the header, and bridge pin 10 and 12. This has been fixed in the new version.

For FPGA code, see https://github.com/knielsen/ice40-stm32-sdram, which uses the STM32 expansion board we also made.
