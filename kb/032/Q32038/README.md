---
layout: page
title: "Q32038: Redirecting the Results of Pressing the PRINT SCREEN Key"
permalink: /kb/032/Q32038/
---

## Q32038: Redirecting the Results of Pressing the PRINT SCREEN Key

	Article: Q32038
	Product(s): Microsoft Disk Operating System
	Version(s): MS-DOS:1.x,2.x,3.x,4.x,5.0,5.0a,6.0,6.2,6.21,6.22
	Operating System(s): 
	Keyword(s): 
	Last Modified: 17-DEC-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft MS-DOS operating system versions 1.x, 2.11, 3.1, 3.2, 3.21, 3.3, 3.3a, 4.0, 4.0a, 5.0, 5.0a, 6.0, 6.2, 6.21, 6.22 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	When the PRINT SCREEN key is pressed, an interrupt occurs that dumps the
	contents of the screen to the printer. This interrupt (INT 05h) is not an MS-DOS
	interrupt; it is a ROM-BIOS interrupt.
	
	The MS-DOS MODE command can redirect the MS-DOS file handle and FCB output sent
	to the LPT1: device to a serial device (that is, COM1 or COM2).
	
	However, MS-DOS has no way to redirect the output generated by pressing the PRINT
	SCREEN key, which by default goes to the device referred to as LPT1:. The only
	way to redirect the output to another serial or parallel port is to use a
	public-domain utility designed for this purpose. Public- domain utilities are
	available that redirect printer output (including output generated by pressing
	the PRINT SCREEN key) to a file and to another parallel port.
	
	Additional query words: 6.22 1.10 1.25 2.00 2.10 2.11 3.00 3.10 3.20 3.21 3.30 3.30a 4.00 5.00 5.00a 6.00 6.20
	
	======================================================================
	Keywords          :  
	Technology        : kbMSDOSSearch kbMSDOS321 kbMSDOS400 kbMSDOS1xSearch kbMSDOS320 kbMSDOS330a kbMSDOS621 kbMSDOS622 kbMSDOS620 kbMSDOS600 kbMSDOS310 kbMSDOS500 kbMSDOS330 kbMSDOS500a kbMSDOS211
	Version           : MS-DOS:1.x,2.x,3.x,4.x,5.0,5.0a,6.0,6.2,6.21,6.22
	
	=============================================================================
	