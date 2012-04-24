# USBDM Flashing instructions

JAG 04/22/2012 1700 EST (GMT-0500)

## Initial programming of USBDM bootloader into BDM Flash.

 * Download the BOOTLOADER GUI from Freescale, you will need this to load the initial USB driver for the Freescale JS16 MCU and to program the USBDM firmware (note this is Windows 32-bit only, sorry).  Link: http://www.freescale.com/webapp/sps/site/prod_summary.jsp?code=DEMO9S08JS16&fpsp=1&tab=Design_Tools_Tab#
 * The JS16 has a built-in USB bootloader. This is used with the provided JS16 Bootloader GUI to initially program the JS16.
 * If the JS16 MCU is completely unprogrammed you can simply plug it in, otherwise tie the BLMS pin low before doing so.
 * The same driver is used by the JS16 Bootloader as used by the USBDM software. The instructions in USB Driver Installation may be followed with the obvious substitution of JS16 Bootloader for USBDM where necessary. Link to USBDM Driver: http://usbdm.sourceforge.net/USBDM_V4.9/USBDM_JS16/html/driver_page.html
 * Start the JS16 Bootloader.
   * # Select the appropriate USBDM firmware to load to the device.
   * Press Program to program the device. There is no progress dialogue but after a short wait a confirmation should appear.
   * Note that this programming is only needed once. You may notice that the programmer gives a error message similar to:
       Doing CRC ...
       CRC Checksum Error
       Error while doing CRC.
    This indicates that the Flash image does not have a valid CRC. USBDM does not use the CRC feature available in the JS16 and hence this error message is to be expected and may be ignored.
 * For a Debian Linux based PC, use the following command to install the pre-requisite packages: 
   * apt-get install tcl8.5 libwxgtk2.8-0 libwxgtk2.8-dbg libstdc++5 libxerces-c3.1
 * At this time you will need to download and install CodeWarrior for MCUs (Linux version) to be able to use the standalone programming utilities as they rely on some libraries from CodeWarrior.  Several people are looking into this to see how to trim down the 2.7GB installation of CW.  Here is a link to download the "Special Edition: CodeWarrior for Microcontrollers 10.2 (Eclipse, Linux hosted) http://www.freescale.com/webapp/sps/site/overview.jsp?code=CW_SPECIALEDITIONS or try this one: http://cache.freescale.com/lgfiles/devsuites/MCU/CW_MCU_v10.2_SE.tar
 * Extract the USBDM archive
   * cd into the /files directory
   * Next you will need to do chmod +x Install_USBDM
   * Now you can run ./Install_USBDM to update your CodeWarrior install so that you can use the USBDM with it.
 * If you don't wish to use CodeWarrior, then you can cd into the Utilities directory and then you will need to chmod +x /*FlashProgrammer/* so that you can run the programming utility.





