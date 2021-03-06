---
layout: page
title: "Q124566: Recovering from &quot;SYSTEM Hive Corruption&quot; on Dual-Boot Computers"
permalink: /kb/124/Q124566/
---

## Q124566: Recovering from &quot;SYSTEM Hive Corruption&quot; on Dual-Boot Computers

{% raw %}

	Article: Q124566
	Product(s): Microsoft Windows NT
	Version(s): 
	Operating System(s): 
	Keyword(s): 
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 3.1 
	- Microsoft Windows NT Workstation version 3.1 
	- Microsoft Windows NT Advanced Server, version 3.1 
	- Microsoft Windows NT Workstation version 3.5 
	- Microsoft Windows NT Server version 3.5 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	On a dual-boot computer, configured to boot both Windows NT 3.1 and Windows NT
	3.5, if you attempt to start the Windows NT 3.5 system after changing the
	configuration of the Windows NT 3.1 system, Windows NT 3.5 may fail to boot with
	the following message displayed on a black screen:
	
	  OS Loader V3.1
	  ....
	  Windows NT could not start because the following file is missing or corrupt:
	  \WINNT\SYSTEM32\CONFIG\SYSTEM
	
	  You can attempt to repair this file by starting Windows NT Setup using the
	  original floppy disk or CD-ROM.
	  Select 'r' at the first screen to start repair.
	  Boot failed
	
	This message implies that there is a problem with the Windows NT 3.5 SYSTEM
	Registry hive. This might not be the case. It may be possible to fix this
	problem without performing an emergency repair on the Windows NT 3.5 Registry.
	An emergency repair of the Windows NT 3.5 System Files may rectify the problem.
	
	MORE INFORMATION
	================
	
	This message usually appears after modifying the Windows NT 3.1 side of the
	dual-boot system by doing one of the following:
	
	- Performing an Emergency Repair on the Windows NT 3.1 system
	
	- Applying a Service Pack to the Windows NT 3.1 system
	
	- Installing a new copy of Windows NT 3.1 on the computer.
	
	All of the above actions cause the Windows NT 3.5 versions of C:\NTLDR and
	C:\NTDETECT.COM to be replaced with older Windows NT 3.1 versions.
	
	The internal format of the registry was changed between Windows NT 3.1 and
	Windows NT 3.5. This prevents the Windows NT 3.1 NTLDR from booting the Windows
	NT 3.5 system, because it cannot locate startup information in the Windows NT
	3.5 SYSTEM hive.
	
	Performing an Emergency Repair of the Windows NT 3.5 System Files may rectify the
	problem, as this procedure will reinstall the Windows NT 3.5 versions of NTLDR
	and NTDETECT.COM. This may be a more convenient recovery option than an
	Emergency Repair of the Registry, if, in fact, the downgrading of these files is
	the cause of the boot failure.
	
	Additional query words: prodnt 3.10 3.50
	
	======================================================================
	Keywords          :  
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNT350search kbWinNTW350 kbWinNTW350search kbWinNTW310 kbWinNTSsearch kbWinNTS350 kbWinNTS310 kbWinNTAdvSerSearch kbWinNTAdvServ310 kbWinNTS350search kbWinNTS310search kbWinNT310Search kbWinNTW310Search
	
	=============================================================================
	

{% endraw %}
