# USBDM Flashing instructions:

JAG 04/22/2012 1700 EST (GMT-0500)

## Initial programming of USBDM bootloader into BDM Flash.

 * The JS16 has a built-in USB bootloader. This is used with the provided JS16 Bootloader to initially program the JS16.
 * If the JS16 MCU is completely unprogrammed you can simply plug it in, otherwise tie the BLMS pin low before doing so.
 * Download the BOOTLOADER GUI from Freescale, you will need this to load the initial USB driver for the Freescale JS16 MCU and to program the USBDM firmware (note this is Windows 32-bit only, sorry).  Link: http://www.freescale.com/webapp/sps/site/prod_summary.jsp?code=DEMO9S08JS16&fpsp=1&tab=Design_Tools_Tab#
 * The same driver is used by the JS16 Bootloader as used by the USBDM software. The instructions in USB Driver Installation may be followed with the obvious substitution of JS16 Bootloader for USBDM where necessary. Link to USBDM Driver: http://usbdm.sourceforge.net/USBDM_V4.9/USBDM_JS16/html/driver_page.html
 * Start the JS16 Bootloader.
   * # Select the appropriate firmware to load to the device.
   * Press Program to program the device. There is no progress dialogue but after a short wait a confirmation should appear.
 * 
 * 
 * For a Debian Linux based PC, use the following command to install the pre-requisite packages: 
   * apt-get install tcl8.5 libwxgtk2.8-0 libwxgtk2.8-dbg libstdc++5 libxerces-c3.1

