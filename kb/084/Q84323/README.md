---
layout: page
title: "Q84323: PRB: Unexpected &quot;This Program Requires Microsoft Windows&quot; Msg"
permalink: /kb/084/Q84323/
---

## Q84323: PRB: Unexpected &quot;This Program Requires Microsoft Windows&quot; Msg

	Article: Q84323
	Product(s): Microsoft Programming Utilities
	Version(s): MS-DOS:5.0x,5.1x,5.2,5.3x,5.5; OS/2:5.0x,5.1,5.11,5.13,5.15
	Operating System(s): 
	Keyword(s): kb16bitonly
	Last Modified: 30-OCT-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft LINK for MS-DOS, versions 5.0x, 5.1x, 5.2, 5.3x, 5.5 
	- Microsoft LINK for OS/2, versions 5.0x, 5.1, 5.11, 5.13, 5.15 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	An attempt to run, in MS-DOS, an application generated by Microsoft FORTRAN
	version 5.1, fails and generates the following message:
	
	  This program requires Microsoft Windows
	
	If the application is run in Windows, the system may open an MS-DOS session,
	display the message above and close the MS-DOS session, returning to Windows
	without running the application.
	
	CAUSE
	=====
	
	Most likely, one of the following errors occurred linking the application:
	
	  L2025: Multiply Defined Symbol
	
	  L2029: Unresolved External
	
	When one of these errors occurs, Microsoft LINK sets an error bit in the
	executable file header. The error bit warns the application loader that the file
	contains an error. In Windows, this bit causes the loader to start an MS-DOS
	session for the application. If the application is designed for Windows, the
	MS-DOS correctly displays the error message above.
	
	If an L2025 or L2029 error occurs creating an application for the MS-DOS
	operating system, the loader does not reject the application. However, in the
	MS-DOS operating system, running an application that has unresolved externals
	may generate incorrect results or cause the system to hang. In the OS/2
	operating system, the application generates a general protection (GP) fault if
	it attempts to access a restricted memory location.
	
	RESOLUTION
	==========
	
	The best method to address this situation involves resolving the LINK error at
	its source. If this is not possible or undesirable, use the EXEHDR utility to
	manually reset the error bit. The syntax to call the EXEHDR utility is as
	follows:
	
	  EXEHDR /r <filename>
	
	STATUS
	======
	
	Versions 3.0 and 3.1 of the Windows loader each interpret the error bit as
	described above.
	
	MORE INFORMATION
	================
	
	The following FORTRAN code reproduces the problem:
	
	Sample Code
	-----------
	
	This is the source code for the SAMPLE.FOR file:
	
	      
	    PROGRAM Sample_Test
	        PRINT *, 'FORTRAN Test'
	        GOTO 20
	        CALL MySub (123)          ! MySub is unresolved at link time
	   20   CONTINUE
	        END
	
	Project Makefile
	----------------
	
	ALL : Sample.EXE
	
	  Sample.EXE : Sample.OBJ
	     Link Sample.OBJ,, nul, /NOD LLIBFEW.LIB, FL.DEF
	
	  Sample.OBJ : Sample.FOR
	     FL /c /MW Sample.FOR
	
	Additional query words: 5.01.20 5.01.21 5.02 5.03 5.05 5.10 5.11 5.13 5.15 5.20 5.30 5.31.009 5.50
	
	======================================================================
	Keywords          : kb16bitonly 
	Technology        : kbAudDeveloper kbZNotKeyword3 kbLINKSearch kbLINK50xDOSSearch kbLINK510xDOSSearch kbLINK530xDOSSearch kbLINK50xOS2Search kbLINK520DOS kbLINK550DOS kbLINK510OS2 kbLINK511OS2 kbLINK513OS2 kbLINK515OS2
	Version           : MS-DOS:5.0x,5.1x,5.2,5.3x,5.5; OS/2:5.0x,5.1,5.11,5.13,5.15
	
	=============================================================================
	