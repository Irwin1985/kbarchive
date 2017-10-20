---
layout: page
title: "Q192498: SMS: Repackage of Netscape Communicator 4.03 Fails to Show Icons"
permalink: /kb/192/Q192498/
---

## Q192498: SMS: Repackage of Netscape Communicator 4.03 Fails to Show Icons

	Article: Q192498
	Product(s): Microsoft Systems Management Server
	Version(s): WINDOWS:1.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 09-SEP-1999
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server Installer version 1.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When using Microsoft Systems Management Server Installer to do a repackage of
	Netscape Communicator 4.03 Pro, the installation fails in several ways depending
	on the platform. On Microsoft Windows NT systems, the icons created by the
	Systems Management Server Installer do not correspond to those created by the
	actual Netscape installation.
	
	The problem occurs when the shortcut icon number generated by the Systems
	Management Server Installer is greater than 127 in the installation expert. When
	the number exceeds 127 and you click OK in the Installation Expert, you are
	prompted to enter a number between 0 and 127, even though Installation Expert
	put the higher number in the icon number field.
	
	This occurs because the Installation Expert uses 7 bits to represent an icon
	number, when it should be a 16-bit value.
	
	On Microsoft Windows 95 computers, the failures are similar to those on Microsoft
	Windows NT. In addition, a sub-group of the Netscape Start Menu is not created
	on the Microsoft Windows 95 systems.
	
	A "Normal" Netscape installation creates a Netscape Communicator Professional
	Edition program group and also creates a subgroup called Utilities when it is
	installed on either Windows NT or Windows 95. When repackaging Netscape under
	Windows 95, the Utilities group is not created; all the items that are normally
	installed in this group are placed in the Netscape Communicator Professional
	Edition group (with incorrect icons).
	
	CAUSE
	=====
	
	The icon numbers for each installation are as follows:
	
	                           SMS Installer   Netscape (Actual)
	  Icon Name                 Icon Number       Icon Number
	  -----------------------------------------------------------
	  IBM Host On-Demand              4                5
	  Collabra                       31                4
	  Composer                      155                3
	  Messenger                     187               11
	  Navigator                     254                1
	  Netcaster                      28                6
	  User Profile Manager           27                7
	
	This problem has the potential of occurring with every icon that has a value
	greater than 127.
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Systems Management Server
	Installer builds 1.0.24 and earlier for Microsoft Windows NT and Windows 95.
	
	
	MORE INFORMATION
	================
	
	
	The third-party contact information included in this article is provided to help
	you find the technical support you need. This contact information is subject to
	change without notice. Microsoft in no way guarantees the accuracy of this
	third-party contact information.
	
	The third-party products discussed here are manufactured by vendors independent
	of Microsoft; we make no warranty, implied or otherwise, regarding these
	products' performance or reliability.
	
	Additional query words: prodsms
	
	======================================================================
	Keywords          :  
	Technology        : kbSMSSearch kbSMSI100
	Version           : WINDOWS:1.0
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	