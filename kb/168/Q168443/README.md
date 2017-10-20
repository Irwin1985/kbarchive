---
layout: page
title: "Q168443: XADM: Exchange Server Download Logging Feature"
permalink: /kb/168/Q168443/
---

## Q168443: XADM: Exchange Server Download Logging Feature

	Article: Q168443
	Product(s): Microsoft Exchange
	Version(s): WINNT:4.00
	Operating System(s): 
	Keyword(s): kbusage
	Last Modified: 28-APR-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, versions 4.0, 5.0, 5.5 
	-------------------------------------------------------------------------------
	
	IMPORTANT: This article contains information about editing the registry.
	Before you edit the registry, make sure you understand how to restore it
	if a problem occurs. For information on how to do this, view the "Restoring
	the Registry" online Help topic in Regedit.exe or the "Restoring a Registry
	Key" online Help topic in Regedt32.exe.
	
	SUMMARY
	=======
	
	The Microsoft Exchange Server download logging feature writes events to the
	Windows NT Event Log when users download attachments, messages, and folders from
	public or private folders. You can use this information for billing or tracking
	download costs.
	
	MORE INFORMATION
	================
	
	A download event is logged when the user moves or copies an item from the
	private or public information store to a different store, such as a Personal
	Folder file. The item can be a message, attachment, or folder, depending on the
	configuration selected as described in the following section.
	
	For example, if Log Downloads is set to 1 in the ParametersPublic registry key,
	every time a user moves or copies a message with an attachment to the user's
	Personal Folder file, an event is logged.
	
	The following information is logged:
	
	- User name
	
	- Mailbox name
	
	- Size of item downloaded
	
	- Document type
	
	- Document identifier
	
	The following example is an event generated by the download feature.
	
	  Event ID: 7102
	  Type: Information
	  Source: MSExchangeIS Private
	  Category: Download
	  Description:
	
	  User WinNT_Domain\User (mailbox
	  /o=Org /ou=Site /cn=Recipients /cn=Mailbox) downloaded 
	  2127271 bytes from attachment 
	  c7e20a0c4-9762-11d1-a487-00c04fc29f3e-b8a1
	
	You establish download logging by editing the registry of a Microsoft Exchange
	Server with RegEdit, a Windows NT administrative tool. The values you add apply
	to all public and private folders on the server.
	
	WARNING: Using Registry Editor incorrectly can cause serious problems that may
	require you to reinstall Windows. Microsoft cannot guarantee that problems
	resulting from the incorrect use of Registry Editor can be solved. Use Registry
	Editor at your own risk.
	
	For information about how to edit the registry, view the "Changing Keys And
	Values" online Help topic in Registry Editor (Regedit.exe) or the "Add and
	Delete Information in the Registry" and "Edit Registry Data" online Help topics
	in Regedt32.exe. Note that you should back up the registry before you edit it.
	
	To start download logging:
	
	1. Start Registry Editor (Regedt32.exe or Regedit.exe as appropriate for your
	  version of Windows NT).
	
	2. Go to the following key in the registry:
	
	     HKEY_LOCAL_ MACHINE\SYSTEM\CurrentControlSet\Services\MSExchangeIS
	
	3. Select ParametersPublic to log downloads from public folders. Select
	  ParametersPrivate to log downloads from private mailboxes.
	
	4. On the Edit menu, click Add Value and use the following entry:
	
	     Value Name: Log Downloads
	     Data Type: REG_DWORD
	
	5. In the D_WORD Editor dialog box, type a decimal or binary value from the
	  following table.
	
	   To log downloads from      Enter a registry value of  Decimal  Binary
	
	   Attachments only           1                          001
	   Messages only              2                          010
	   Attachments and messages   3                          011
	   Folders only               4                          100
	   Attachments and folders    5                          101
	   Messages and folders       6                          110
	   All                        7                          111
	
	Use the Windows NT Event Viewer to review events recorded by the download logging
	feature. To view logged downloads:
	
	1. In the Windows NT Administrative Tools program group, choose Event Viewer.
	
	2. On the View menu, click Filter Events.
	
	3. In the Source box, select MSExchangeISPub or MSExchangeISPriv.
	
	4. In the Category box, select Download.
	
	5. Double-click an event to see its detail.
	======================================================================
	Keywords          : kbusage 
	Technology        : kbExchangeSearch kbExchange500 kbExchange550 kbExchange400 kbZNotKeyword2
	Version           : WINNT:4.00
	Issue type        : kbinfo
	
	=============================================================================
	