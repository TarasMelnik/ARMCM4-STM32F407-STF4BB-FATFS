*****************************************************************************
** ChibiOS/RT port for ARM-Cortex-M4 STM32F407.                            **
*****************************************************************************

** TARGET **

The demo runs on a STM32F4-Discovery board + Embest DM-STF4BB
    www.embest-tech.com/product/extension-module/dm-stf4bb-base-board.html
    
** The Demo **

The MicroSD port on the Embest board is used for FATfs actions though SDIO.
    
The Embest BB board does not have the ability to detect when a card is inserted
    so the mount and unmount commands need to be called before doing anything.

    mount
        Mount the SD card, must be called before anything else.
        The blue LED will illuminate when a SD card is mounted.
    unmount
        Unmount the SD card 
    mkfs [partition]
        Format the [partition], starts at 0
    getlabel
        Get the label of the default partition.
    setlabel [label]
        Set the label of the default partition.
    tree
        Print the file structure
    free
        Print free space on the drive.
    mkdir [dir]
        Make a directory [dir] on the drive.
    hello
        Create hello.txt and put "Hello World" in it.
    cat [file]
        Echo  [file] to the terminal.
        
    A shell is attached to both:
        USART1: PA9(TX) & PA10(RX)
        USART2: PD5(TX) & PD6(RX)
** Build Procedure **

The demo has been tested by using the free GCC-based toolchain included with 
ChibiStudio.

Just modify the TRGT line in the makefile in order to use different GCC ports.

** Notes **

Some files used by the demo are not part of ChibiOS/RT but are copyright of
ST Microelectronics and are licensed under a different license.
Also note that not all the files present in the ST library are distributed
with ChibiOS/RT, you can find the whole library on the ST web site:

                             http://www.st.com
