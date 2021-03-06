---
layout: page
title: "Q106167: Err Msg: Not Enough Server Storage is Available..."
permalink: /kb/106/Q106167/
---

## Q106167: Err Msg: Not Enough Server Storage is Available...

{% raw %}

	Article: Q106167
	Product(s): Microsoft Windows NT
	Version(s): winnt:3.5,3.51
	Operating System(s): 
	Keyword(s): kbnetwork
	Last Modified: 08-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows NT Server version 3.1 
	- Microsoft Windows NT Workstation version 3.1 
	- Microsoft Windows NT Advanced Server, version 3.1 
	- Microsoft Windows NT Workstation versions 3.5, 3.51 
	- Microsoft Windows NT Server versions 3.5, 3.51 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you access shares on a Windows NT server from a Windows NT client and the
	IRPstackSize parameter is set too low on the server, you may receive the
	following error message:
	
	  Not enough server storage is available to process this command.
	
	
	MORE INFORMATION
	================
	
	The registry value IRPstackSize, which may be listed at HKEY_LOCAL_MACHINE\
	SYSTEM\ CurrentControlSet\ Services\ LanmanServer\ Parameters defaults to 0x4 if
	the value is not explicitly present. Valid values range from 0x1 to 0xC (1 to
	12). Depending on the hardware configuration of a specific machine, the default
	value may not be large enough for the Srv service to properly administer shared
	directories on some of the physical drives. You may see one or both of the
	following event messages:
	
	  Event ID: 2011  Source: Srv
	  The server's configuration parameter "irpstacksize" is too small for
	  the server to use a local device.  Please increase the value of this
	  parameter.
	
	  Event ID: 0
	  Source SRV
	  Description:  Description for Event ID 0 could not be found.  It
	  contains the insertion string \device\LanManServer
	
	You may receive one of the above error message when a Windows NT client tries to
	access certain shared directories on such a server.
	
	When a Windows for Workgroups client tries to access the same shared directories,
	the following message will be generated:
	
	  Path not found.
	
	To increase the value of the parameter when it is not already present, go to the
	key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\
	LanmanServer\Parameters. The value of IRPStackSize defaults to 0x4 if it is not
	explicitly present. If the key is not present, choose Add Value in the Registry
	Editor. The Value Name should be IRPStackSize and the Data Type is REG_DWORD..
	
	If you are encountering this error message, try gradually increasing the value of
	IrpStackSize in order to find the minimal value which resolves the problem.
	Using a value that is larger than necessary can result in an unnecessary waste
	of system resources. Other factors can also lead to this error message. If
	problems persist with all legal values for IrpStackSize, restore IrpStackSize to
	its original value and another explanation for the error must be sought.
	
	WARNING: Using Registry Editor incorrectly can cause serious, system-wide
	problems that may require you to reinstall Windows NT to correct them. Microsoft
	cannot guarantee that any problems resulting from the use of Registry Editor can
	be solved. Use this tool at your own risk.
	
	
	If you receive this error message and you are running Microsoft Windows NT 4.0,
	please see the following article in the Microsoft Knowledge Base:
	
	  Q198386 Changes in IRP Stack Size in Lanman Server
	
	Additional query words: wfw wfwg IRP stack size
	
	======================================================================
	Keywords          : kbnetwork 
	Technology        : kbWinNTsearch kbWinNTWsearch kbWinNT351search kbWinNT350search kbWinNTW350 kbWinNTW350search kbWinNTW351search kbWinNTW351 kbWinNTW310 kbWinNTSsearch kbWinNTS351 kbWinNTS350 kbWinNTS310 kbWinNTAdvSerSearch kbWinNTAdvServ310 kbWinNTS351search kbWinNTS350search kbWinNTS310search kbWinNT310Search kbWinNTW310Search
	Version           : winnt:3.5,3.51
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
