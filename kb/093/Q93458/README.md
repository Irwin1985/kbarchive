---
layout: page
title: "Q93458: README.WRI from Windows for Workgroups Version 3.1 (Part A)"
permalink: /kb/093/Q93458/
---

## Q93458: README.WRI from Windows for Workgroups Version 3.1 (Part A)

{% raw %}

	Article: Q93458
	Product(s): Microsoft Windows 3.x Retail Product
	Version(s): WINDOWS:3.1
	Operating System(s): 
	Keyword(s): 
	Last Modified: 23-SEP-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows for Workgroups version 3.1 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The following information was taken from the Microsoft Windows for Workgroups
	version 3.1 README.WRI file. This article contains section 1.0 through 6.5.
	
	MORE INFORMATION
	================
	
	More Information About Microsoft Windows for Workgroups
	-------------------------------------------------------
	
	This document contains important information not available in the
	"Microsoft Windows for Workgroups User's Guide" or in online Help. For
	additional information about Windows for Workgroups, see "Other Online
	Documents" at the end of this document.
	
	Note: If you plan on using a terminate-and-stay-resident (TSR) program
	with Windows for Workgroups, please read the SETUP.TXT online document
	first. It contains important information about running TSR programs
	with Windows for Workgroups and the Setup program.
	
	Using Write to View This Document
	---------------------------------
	
	If you enlarge the Write window to its maximum size, this document
	will be easier to read. To do so, click the Maximize button in the
	upper-right corner of the window. Or open the Control menu in the
	upper-left corner of the Write window (press ALT+SPACEBAR), and then
	choose the Maximize command.
	
	To move through the document, press PAGE UP or PAGE DOWN. Or click the
	arrows at the top and bottom of the scroll bar along the right side of
	the Write window.
	
	To print the document, choose Print from the File menu.
	
	For Help on using Write, press F1.
	
	To read other online documents, choose Open from the File menu.
	
	Contents
	--------
	
	This document contains information about the following topics:
	
	1.0  Running Windows for Workgroups with an Operating System Other
	    Than MS-DOS
	
	2.0  Preventing Stack Overflow
	
	3.0  Using 32-Bit Disk Access
	
	4.0  Using Memory Managers and Vshare
	4.1  Solving Memory Conflicts by Using MONOUMB.386 or MONOUMB2.386
	4.2  Solving Memory Conflicts by Excluding an Address Range
	4.3  Using 386MAX
	4.4  Turning On Sharing Popup with Vshare
	
	5.0  Using Advanced Power Management (APM)
	
	6.0  Using SMARTDrive Version 4.0
	6.1  Accessing Floppy Disk Drives on Older COMPAQ DESKPROS
	6.2  Using SMARTDrive with Double Buffering
	6.3  Using SMARTDrive with Norton Utilities Version 6.0 Disk Monitor
	6.4  Using SMARTDrive with SuperStor Disk-Compression Utility
	6.5  Using SMARTDrive with Copy-Protected Games and Applications
	
	7.0  Using Multimedia Extensions with Windows for Workgroups
	7.1  Upgrading to Windows for Workgroups
	7.2  Configuring MIDI Setups
	7.3  Configuring Your Display
	7.4  Sample MIDI File
	7.5  Using HyperGuide
	7.6  Using Music Box
	7.7  Using Alarm Clock
	
	8.0  Running Specific MS-DOS-based Applications
	8.1  Creative Labs JukeBox
	8.2  Game or Timing-Sensitive Applications
	8.3  Third-Party Expanded-Memory Emulators with MS-DOS Version 5.0
	8.4  PC Tools Applications
	8.5  WordPerfect Version 5.1
	8.6  3270-Emulation Applications
	8.7  C/C++ Version 7.0
	
	9.0  Running Communications Applications
	
	10.0  Using Specific Display Adapters with Windows for Workgroups
	
	10.1  Installing Display Adapters by Following the Manufacturer's
	     Instructions
	10.2  Upgrading Display Drivers When Using Soft-Font Packages
	10.3  Using Self-Configuring Display Adapters
	10.4  LCD
	10.5  SuperVGA
	10.6  Third-Party Display Drivers: Running MS-DOS-based Applications
	10.7  VGA-Compatible
	10.8  Video Seven: Using 256-Color Support
	10.9  WinSpeed
	10.10 IBM XGA: Configuring Color and Resolution
	10.11 IBM XGA: Using EMM386
	
	11.0  Using Specific Mice with Windows for Workgroups
	11.1  Microsoft Mouse
	11.2  Genius Mouse
	11.3  Logitech Mouse
	11.4  Logitech Cordless Mouse
	11.5  Logitech or Microsoft BallPoint Mouse on a Toshiba T2200SX
	11.6  Mouse Systems Mouse on PS/2 Ports
	
	12.0  Using Additional Hardware Configurations with Windows for
	     Workgroups
	12.1  CD-ROM Drives
	12.2  EISA Systems with More Than 16 Megabytes of Extended Memory
	12.3  Epson Screen Savers
	12.4  NCR 925 with EMM386.EXE
	12.5  Non-US Keyboard Layouts: Using Application Shortcut Keys
	12.6  Plus Hardcard
	12.7  SCSI Hard Disk Using DMA
	12.8  Columbia Data Products SCSI Hard-Disk Controller
	12.9  Serial Ports on 80286-Based Computers: Improving   Performance
	12.10 Sound Blaster Audio Card
	12.11 Tandy 2500XL with MS-DOS in ROM
	12.12 Wyse Computers
	
	13.0  Using Mail
	13.1  Running Mail with Windows for Workgroups in Standard Mode
	13.2  Backing Up a Mail Message File
	13.3  Creating and Accessing Other Message Files
	13.4  Checking for New Mail
	13.5  Sending a Bitmap as an Attachment
	13.6  Compressing Shared Folders
	13.7  Connecting to a Postoffice on a NetWare Server
	13.8  Workgroup Postoffice Must Be at the Root of Share
	13.9  Workgroup Postoffice Share Names
	13.10 Multiple Mail users on One Computer
	13.11 Creating Schedule+ Resources
	
	14.0  Other Online Documents
	
	1.0  Running Windows for Workgroups with an Operating System Other
	    Than MS-DOS
	------------------------------------------------------------------
	
	Microsoft Windows for Workgroups and MS-DOS work together as an
	integrated system. They were designed together and extensively tested
	together on a wide variety of computers and hardware configurations.
	Running Windows for Workgroups on an operating system other than
	MS-DOS could cause unexpected results or poor performance.
	
	2.0  Preventing Stack Overflow
	------------------------------
	
	Stacks are temporary data structures that MS-DOS and applications use
	for processing hardware events. If, while setting up Windows for
	Workgroups, the Setup program detects hardware or software that
	require a certain stack size, Setup places the following command line
	in your CONFIG.SYS file:
	
	  stacks=9,256
	
	This should be sufficient most of the time. However, if you receive
	the "Internal Stack Overflow" message when Windows for Workgroups is
	running in 386 enhanced mode, or if your system fails for no apparent
	reason when Windows for Workgroups is running in standard mode
	(especially if you are setting up or moving the mouse), first try
	increasing the second number on the stacks= command line (for example,
	256). If that doesn't work, try increasing the first number (for
	example, 9). For more information about the stacks setting and
	modifying the CONFIG.SYS file, see your MS-DOS documentation.
	
	3.0  Using 32-Bit Disk Access
	-----------------------------
	
	By default, 32-bit disk access is turned off to prevent disk errors on
	some battery-powered portable computers. However, 32-bit disk access
	may run correctly with some battery-powered portable computers, such
	as the Zenith MasterSport SL. If you want to try using 32-bit disk
	access, select the Use 32-bit Disk Access check box in the expanded
	Virtual Memory dialog box (choose the 386 Enhanced option in Control
	Panel). For more information, see Chapter 11, "Managing Memory and
	Performance," in the "Microsoft Windows for Workgroups User's Guide."
	
	Caution: Before you use 32-bit disk access on a battery-powered
	portable computer, it is highly recommended that you back up your hard
	disk. Because 32-bit disk access has not been fully tested on all
	battery-powered systems, you may receive disk errors while using it.
	
	4.0  Using Memory Managers and Vshare
	-------------------------------------
	
	This section describes problems you may encounter while using memory
	managers and the VSHARE.386 file-sharing/file-locking program with
	Windows for Workgroups.
	
	4.1  Solving Memory Conflicts by Using MONOUMB.386 or MONOUMB2.386
	------------------------------------------------------------------
	
	If you encounter the following message when starting Windows for
	Workgroups in 386 enhanced mode, your display driver may be accessing
	the monochrome address range (B000-B7FF), which prevents the memory
	manager from using this range for upper memory blocks:
	
	"Windows cannot set up an upper memory block at segment B000. Exclude
	this address space by using the syntax of your memory manager. For
	more information, see the README.WRI file. Type WIN /S to start
	Windows for Workgroups in standard mode and choose the Read Me icon."
	
	To solve this problem, try installing MONOUMB2.386 on your system.
	MONOUMB2.386 is a device driver provided with Windows for Workgroups
	that allows certain memory managers to use the monochrome address
	range for upper memory blocks even if your display driver is accessing
	this range.
	
	To install MONOUMB2.386:
	
	1. Copy and expand the MONOUMB2.38_ file that is on your Windows for
	  Workgroups disk to your Windows SYSTEM directory by typing the
	  following at the MS-DOS prompt:
	
	     expand  a:\monoumb2.38_  c:\windows\system\monoumb2.386
	
	2. Add the following setting to the [386Enh] section in the SYSTEM.INI
	  file:
	
	     device=monoumb2.386
	
	3.  Start Windows for Workgroups.
	
	Note: MONOUMB2.386 may not work with some memory managers, such as
	EMM386.EXE. In this case, you can try using MONOUMB.386. 
	
	You can also exclude the address region B000-B7FF. This specifies that
	the memory manager should not try to use this address range for upper
	memory blocks. For information about excluding specific address
	ranges, see the following topic.
	
	4.2  Solving Memory Conflicts by Excluding an Address Range
	-----------------------------------------------------------
	
	If you encounter the following message when starting Windows for
	Workgroups in 386 enhanced mode, and the address specified is not
	B000, you must exclude the address range:
	
	  Windows cannot set up an upper memory block at segment xxxx. Exclude
	  this address space by using the syntax of your memory manager. For
	  more information, see the README.WRI file. Type WIN /S to start
	  Windows for Workgroups in standard mode and choose the Read Me icon.
	
	If the address specified is B000, you can try using MONOUMB2.386 or
	MONOUMB.386, as described in the preceding topic.
	
	The method you use to exclude an address range depends on the memory
	manager you are using. For example, if you are using EMM386.EXE, you
	need to remove the I=xxxxx option from the device=emm386.exe command
	line in your CONFIG.SYS file, where xxxxx is the address range
	starting at the address specified in the error message.
	
	If you are using QEMM, you need to include the X= option on the
	device=qemm386.sys command line in your CONFIG.SYS file. For example,
	to exclude the address range C000-C7FF, you would specify the
	following:
	
	  device=qemm386.sys  X=C000-C7FF
	
	For more information about modifying your CONFIG.SYS file, see your
	MS-DOS documentation. For more information about installing and
	configuring EMM386.EXE, see Chapter 11, "Managing Memory and
	Performance," in the "Microsoft Windows for Workgroups User's Guide."
	For information about installing and configuring other memory
	managers, see the documentation provided with your memory manager.
	
	4.3  Using 386MAX
	-----------------
	
	If you are running 386MAX with Windows for Workgroups, note the
	following:
	
	- Do not use options that limit the EMS swap region in the upper memory
	  area. If you include exclude= options on the 386max or bluemax command
	  line or in the .PRO file (usually called 386MAX.PRO), make sure that
	  the address range specified does not extend beyond A000.
	
	  For example, exclude=1800-A000 is acceptable, but exclude=1800-B800 is
	  not. If the address range specified by using the exclude= option
	  extends beyond A000, Windows for Workgroups may not run properly in
	  386 enhanced mode. If you must exclude an address range above A000,
	  use the RAM= option instead. For more information about this and other
	  options, see your 386MAX documentation.
	
	- Do not use the 386MAX parameter EXT=0. This parameter may cause
	  Windows to fail during Setup. After setting up, if Windows is running
	  in standard mode, this parameter causes your system to lock up when
	  you quit Windows.
	
	- Do not load SMARTDrive when QCache is running.
	
	  Note: The 386MAX setup program does not detect SMARTDrive version 4.0
	  and may recommend that you install QCache.
	
	- If you update an earlier version of 386MAX to version 6.0, the 386MAX
	  version 6.0 setup program may not remove the LOAD=WINDOWS.LOD line
	  from your .PRO file. You can remove this line manually. It is not
	  needed and removing it will free up a small amount of memory.
	
	- If for some reason you remove the net start command line from your
	  AUTOEXEC.BAT, Windows may lock up during startup.
	
	4.4  Turning on Sharing Popup with Vshare
	-----------------------------------------
	
	VSHARE.386 is a file-sharing and file-locking program that is used
	when running Windows for Workgroups in 386 enhanced mode. With VSHARE,
	when a file-sharing violation occurs, you see an "Access denied"
	message, instead of the "Sharing violation on drive..." message used
	in versions of Windows that do not include networking.
	
	Some MS-DOS-based applications may need the sharing-violation message.
	If you need to turn on this message, add the following line to the
	[386Enh] section of your SYSTEM.INI file:
	
	  EnableSharingPopups=TRUE
	
	For more information about modifying the SYSTEM.INI file, see the
	SYSINI.WRI online document.
	
	5.0  Using Advanced Power Management (APM)
	------------------------------------------
	
	Windows for Workgroups includes support for Advanced Power Management
	(APM). This enables Windows to extend battery life, display power-
	status information, and work together with the suspend features of
	battery-powered personal computers. To find out if your computer
	supports APM, contact your computer manufacturer.
	
	To install APM on your system:
	
	1. Quit Windows for Workgroups.
	
	2. Run Windows for Workgroups Setup and select one of the following
	  system types:
	
	     MS-DOS System with APM
	     Intel 386SL Based System with APM
	
	  Select "Intel 386SL Based System with APM" if your computer has an
	  Intel 386SL processor and supports the SL Enhanced Options for APM.
	  Otherwise, select "MS-DOS System with APM."
	
	3. Restart Windows for Workgroups.
	
	  A Power icon appears in the Control Panel window.
	
	4. Choose the Power icon to configure power-management settings.
	
	For more information about the settings, choose the Help button or
	press F1 while using the Power Management dialog box.
	
	6.0  Using SMARTDrive Version 4.0
	---------------------------------
	
	This section describes some solutions to problems that you might
	encounter when using SMARTDrive version 4.0 (provided with Windows for
	Workgroups) together with specific applications or hardware.
	
	6.1  Accessing Floppy Disk Drives on Older COMPAQ DESKPROS
	----------------------------------------------------------
	
	On some COMPAQ DESKPRO 386/16 and 386/20 computers, you might
	experience problems accessing floppy disk drives when SMARTDrive
	version 4.0 is installed. To work around the problem, you can try one
	of the following solutions:
	
	- Place the SMARTDrive buffer into low memory by adding the following
	  option to the smartdrv command line in the AUTOEXEC.BAT file:
	
	     smartdrv  /L
	
	- Disable the caching on floppy disk drives by adding the following
	  options to the smartdrv command line in the AUTOEXEC.BAT file:
	
	     smartdrv  a-  b-
	
	For more information about these options, see Chapter 11, "Managing
	Memory and Performance," in the "Microsoft Windows for Workgroups
	User's Guide."
	
	6.2  Using SMARTDrive with Double Buffering
	-------------------------------------------
	
	Most expanded-memory emulators attempt to optimize SMARTDrive by
	configuring it to load into upper memory blocks (UMBs). This will
	cause problems if you are running Windows for Workgroups in 386
	enhanced mode with double buffering. If you need to use double
	buffering with SMARTDrive, make sure that SMARTDrive is configured in
	the CONFIG.SYS file to load into low memory. The command line should
	look like this:
	
	  device=smartdrv.exe  /double_buffer
	
	This problem applies only to the smartdrv command line in the
	CONFIG.SYS file. It does not apply to the references to SMARTDrive in
	the AUTOEXEC.BAT file. For more information about using double
	buffering with SMARTDrive, see Chapter 11, "Managing Memory and
	Performance," in the "Microsoft Windows for Workgroups User's Guide."
	
	6.3  Using SMARTDrive with Norton Utilities Version 6.0 Disk Monitor
	--------------------------------------------------------------------
	
	Do not use the Disk Protect feature in Norton Utilities Version 6.0
	Disk Monitor with SMARTDrive version 4.0. If you try to write to the
	protected drive, you will encounter an error and your system will
	fail. If you want to write to and cache a protected drive, add the
	drive letter to the smartdrv command line in your AUTOEXEC.BAT file.
	For example, if drive D is a protected drive, you would add the
	following:
	
	  smartdrv  d
	
	Or you can use the Norton cache program instead when using Disk
	Monitor.
	
	6.4  Using SMARTDrive with SuperStor Disk-Compression Utility
	-------------------------------------------------------------
	
	Do not use the Create Mountable Drive, Mount, and Dismount features of
	SuperStor after SMARTDrive is loaded. You must configure your
	SuperStor partitions before loading SMARTDrive. Windows for Workgroups
	Setup places the smartdrv command line first in your AUTOEXEC.BAT
	file. If your AUTOEXEC.BAT file includes "mount" configuration
	commands, make sure that the smartdrv command line follows the
	SuperStor configuration command lines.
	
	Also, you will receive read-write errors if you use SMARTDrive to
	cache a SuperStor compressed drive. To prevent SMARTDrive from caching
	the compressed drive, you must include the drive letter- option on the
	smartdrv command line.
	
	For example, if drive C is the uncompressed drive, and drives E and F
	are the compressed SuperStor drives, you would include the following
	command line in your AUTOEXEC.BAT file:
	
	  smartdrv  e-  f-
	
	6.5  Using SMARTDrive with Copy-Protected Games and Applications
	----------------------------------------------------------------
	
	When using SMARTDrive, you may encounter problems starting a copy-
	protected application that requires you to place the master disk in
	the floppy disk drive. To solve this problem, you need to disable
	caching on the floppy disk drive by using the drive letter- option
	when you load SMARTDrive. For example, if you load SMARTDrive from
	your AUTOEXEC.BAT file and are using drive A, you need to include the
	following command line in your AUTOEXEC.BAT file:
	
	  smartdrv  a-
	
	Additional query words: 3.10 wfw wfwg
	
	======================================================================
	Keywords          :  
	Technology        : kbAudDeveloper kbWFWSearch kbWFW310
	Version           : WINDOWS:3.1
	
	=============================================================================
	

{% endraw %}
