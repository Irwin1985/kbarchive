---
layout: page
title: "Q249796: XCLN:Outlook Rule Creates Message Loop in Information Store"
permalink: /kb/249/Q249796/
---

## Q249796: XCLN:Outlook Rule Creates Message Loop in Information Store

{% raw %}

	Article: Q249796
	Product(s): Microsoft Exchange
	Version(s): WINDOWS:97; winnt:5.5; :
	Operating System(s): 
	Keyword(s): exc55
	Last Modified: 10-NOV-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Exchange Server, version 5.5 
	- Microsoft Outlook 97 
	- Microsoft Outlook 98 
	- Microsoft Outlook 2000 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	An Exchange Server computer may receive a large number of non-delivery report
	(NDR) messages (Event ID 290), and the Mtadata folder may be filled with
	messages, all from a particular user. When you check the message transfer agent
	(MTA) queues on that server, a large number of messages are bound for the local
	information store.
	
	CAUSE
	=====
	
	This issue can occur if a rule automatically forwards all messages sent to a
	particular mailbox to another mailbox or group of mailboxes. If one or more of
	the target mailboxes are deleted, an NDR is generated and returned to the
	sending mailbox, which creates a message loop local to that server.
	
	The generation of an NDR forces the message to route through the MTA, which is
	why the MTA may be filled with messages that are bound for the local information
	store from a sender on the same information store.
	
	RESOLUTION
	==========
	
	To resolve this issue, use one of the three following methods (the methods are
	listed in order according to the severity of the symptoms that you are
	experiencing, from least severe to most severe):
	
	- Log on at the client computer that the autoforwarding rule was created on.
	  Delete the rule.
	
	-or-
	
	- Log on at the client computer that the autoforwarding rule was created on and
	  install and run CleanSweep. For additional information about how to install
	  and run CleanSweep, click the article number below to view the article in the
	  Microsoft Knowledge Base:
	
	  Q174045 XCLN: Installing and Using the CleanSweep Tool
	
	  Delete all local and server-side rules.
	
	-or-
	
	- Delete the mailbox that is automatically forwarding the mail.
	
	In some cases, you may need to stop the MTA service to prevent it from causing
	the server to stop responding because of hard drive or processor overuse. After
	the rule is no longer running, you can allow the MTA to empty normally. If there
	are too many messages in the Mtadata folder, contact Microsoft Product Support
	Services (PSS) for assistance.
	
	Additional query words: OL97, OL98, OL2000
	
	======================================================================
	Keywords          : exc55 
	Technology        : kbOutlookSearch kbExchangeSearch kbExchange550 kbZNotKeyword2 kbOutlook2000Search kbOutlook97Search kbOutlook98Search kbZNotKeyword3
	Version           : WINDOWS:97; winnt:5.5; :
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
