# USBDM

JAG 04/16/2012 1500 EST (GMT-0500)

### Introduction

I did not invent the USBDM nor the TBDML or OSBDM that my version of the USBDM PCB is based on, I merely arranged the components so that a home user could etch and solder the components to create a USBDM at home.

### Goals

Core specs:

 * USB Type A male connector
 * This USBDM is USB bus powered and will power the target microcontroller (if the target board draws less than 100mA to program the target MCU).
 * No other BDM is necessary to program the Freescale MCU used on the USDBM board, you can program the initial USBDM program through the USB connector.
 * Low cost: components to build this version of the USBDM PCB are approximately $15 USD.
 * Software is available for Windows and Linux host systems from http://sourceforge.net/projects/usbdm/files/

PCB size is to be as small as possible to fit into a USB Type-A female socket on a laptop.

### Features:

This version of the code & extended hardware provides the following features:

 * A single BDM interface for programming and debugging of the following targets:
   * HCS12 (including those without SYNC feature (e.g. 9S12DP256B)
   * HCS12X
   * HCS08
   * Coldfire V1 microcontrollers

 * No re-flashing of the BDM is required when changing between targets
 * Compatible IDEs
   * Codewarrior V10.1 (Eclipse version)
     * Tested on Windows-XP-32bit, Windows-7-32bit, Windows-7-64bit
     * Tested on Ubuntu-32-bit, Debian-32-bit
   * Codewarrior Legacy versions
   * Codewarrior Development Studio for HCS12(X) V5.1 & CW for Microcontrollers V6.3 (RS08 is not supported)
     * Tested on Windows-XP-32bit, Windows-Vista-32bit
   * Initial support for CodeSourcery Lite for Coldfire
     * Tested on Windows-XP-32bit

 * Trimming of target internal clock (Eclipse version or standalone programming tools only).
 * Higher USB communication speed cf. JB16 version BDMs (USB full speed cf. USB low speed)
 * Windows Vista/Windows 7 compatible
 * Linux compatible
 * Initial Firmware programming may be done without a BDM using the JS16 USB bootloader ROM.
 * The Firmware in the BDM may be automatically updated using an in-circuit-programming (ICP) feature.
 * Hardware is physically small
 * HCS12, HCS08, Coldfire V1 specific features:
   * Target reset detection & control (required for HC12 processors). This allows HC12 processors to be reset into BDM mode as required for debugging.
   * A higher BDM interface speed than the existing JB16 OSBDMs. Up to 56MHz. (BDM clock 28MHz).
   * Automatic re-connection. The software has an option to continuously update the interface speed to prevent loss of communication if the target BDM interface speed changes (as may occur with clock changes on some targets).
   * Control of BDM clock selection in HC12/HCS08/Coldfire microcontrollers. Most of these targets provide an alternative BDM clock selection. This can have advantages when connecting to high speed targets as the alternative clock may operate at a lower speed.
   * Trial-and-error determination of communication speed for earlier HC12 targets.
   *User prompting for target supply cycling with BKGD low as may be needed for HCS08 targets
 
### Status

For the most up to date status information for the project, refer to this README.md file which is maintained in sync with the schematics by a small team who verify each other's work.

### Changes

Please send any changes that you make to this USBDM back upstream to Andy Goss' copy at https://github.com/DeuceEFI/USBDM

