---
layout: page
title: "Q181088: Windows 95 DFS Client Switches Drive Mappings to DFS Shares"
permalink: /kb/181/Q181088/
---

## Q181088: Windows 95 DFS Client Switches Drive Mappings to DFS Shares

{% raw %}

	Article: Q181088
	Product(s): Microsoft Windows 95.x Retail Product
	Version(s): WINDOWS:95; winnt:4.0
	Operating System(s): 
	Keyword(s): kbenv kbnetwork osr2 win95kbfixlist
	Last Modified: 10-AUG-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Windows 95 
	- Microsoft Windows 95 OEM Service Release, version 2.0 
	- Microsoft Windows NT Server version 4.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you map drive letters to multiple Distributed File System (DFS) network
	shares from a Windows 95 DFS client, and then change to different drives and
	folders within those shares from a command prompt, the drive letter mappings may
	be switched.
	
	For example, if drive X is mapped to Share1, and drive Y is mapped to Share2, the
	drive letters may be switched so that drive X is mapped to Share2, and drive Y
	is mapped to Share1.
	
	CAUSE
	=====
	
	This problem may occur if either of the following conditions exist:
	
	- There are multiple DFS shares on different servers.
	
	- There are multiple DFS root volumes that contain mappings to same-named DFS
	  leaf objects on different servers.
	
	RESOLUTION
	==========
	
	To resolve this problem, upgrade the Windows 95 DFS client from the following
	Microsoft Web site:
	
	  http://microsoft.com/ntserver/nts/downloads/winfeatures/NTSDistrFile/default.asp
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Microsoft Windows 95 and
	Microsoft Windows 95 OEM Service Releases 2 (OSR2).
	
	MORE INFORMATION
	================
	
	If drive letters are mapped to DFS shares on two different servers and you
	change to a folder on the first drive letter and then change drives to the
	second drive letter, the second drive letter may be mapped to the share that the
	first drive letter was mapped to.
	
	If drive letters are mapped to DFS root shares on two different servers, and each
	share contains a DFS volume mapping that points to same-named DFS leaf shares on
	two other servers, the DFS volume object on one DFS root share may display the
	contents of the DFS leaf share mapped to the other DFS volume object when you
	change to a different folder.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbenv kbnetwork osr2 win95 kbfixlist
	Technology        : kbWinNTsearch kbWinNT400search kbWinNTSsearch kbWinNTS400search kbWinNTS400 kbWin95search kbOPKSearch kbZNotKeyword3
	Version           : WINDOWS:95; winnt:4.0
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
