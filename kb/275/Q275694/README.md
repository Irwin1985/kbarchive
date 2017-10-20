---
layout: page
title: "Q275694: Status Message 2703 Is Generated By Inventory Data Loader"
permalink: /kb/275/Q275694/
---

## Q275694: Status Message 2703 Is Generated By Inventory Data Loader

	Article: Q275694
	Product(s): Microsoft Systems Management Server
	Version(s): 2.0
	Operating System(s): 
	Keyword(s): kbsms200 kbsms200bug
	Last Modified: 23-OCT-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Systems Management Server version 2.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	When the Inventory Data Loader is unable to process a Management Information
	Format (MIF) inventory file, the following error message may be displayed:
	
	  SMS Inventory Data Loader failed to process the delta MIF file %1 and has
	  moved it to %2.
	
	  Possible cause: The file is corrupt or contains bad syntax. Solution: Review
	  the immediately preceding status messages from this component for more
	  details.
	
	  If you ignore this problem, SMS will probably fix it and complete this
	  operation later. If this error occurs repeatedly, refer to your SMS
	  documentation or the Microsoft Knowledge Base for further troubleshooting
	  information.
	
	MORE INFORMATION
	================
	
	The preceding error message may be displayed because of the following possible
	reasons:
	
	- The MIF file is incorrectly formatted.
	
	- The MIF file is a delta inventory file from a client that has not yet
	  reported a full inventory.
	
	- The MIF file is a delta inventory file that contains conflicting information
	  from the currently stored inventory data for the client.
	
	The Inventory Data Loader can automatically attempt to access the MIF inventory
	file for the next 14 days. At the end of 14 days, if the Inventory Data Loader
	is still unable to process the MIF file, it discards it as a defective MIF file.
	
	Additional query words: prodsms statid 2703
	
	======================================================================
	Keywords          : kbsms200 kbsms200bug 
	Technology        : kbSMSSearch kbSMS200
	Version           : :2.0
	Issue type        : kbinfo
	
	=============================================================================
	