---
layout: page
title: "Q195610: WD97: After Update Excel Object Not a Paste Special Option"
permalink: /kb/195/Q195610/
---

## Q195610: WD97: After Update Excel Object Not a Paste Special Option

{% raw %}

	Article: Q195610
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbdta word97
	Last Modified: 14-NOV-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	- Microsoft Excel 97 for Windows 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	When you run Microsoft Excel as an OLE server application, in some cases, you
	will be unable to paste an Excel object into Word using the Paste or Paste
	Special commands on the Edit menu. If you click Paste Special, the Source field
	in the Paste Special dialog box will specify that the source is unknown.
	
	CAUSE
	=====
	
	This behavior occurs because the Excel object is no longer in the Clipboard.
	
	When you run Excel as an OLE server application with Word, after you update the
	embedded Excel object and return to Word, the Excel object disappears from the
	Clipboard.
	
	WORKAROUND
	==========
	
	To use the Paste Special command to embed an Excel object in your Word document
	as many times as you want, follow these steps:
	
	1. Start Excel independent of Word (do not run it as a server application).
	
	2. Copy the Excel selection you want to appear in your Word document (do not
	  quit Excel).
	
	3. Start Word.
	
	4. On the Edit menu, click Paste Special.
	
	Note that the Excel object remains an available option in the Paste Special
	dialog box until you quit Excel or replace the contents of the Clipboard with
	something else.
	
	MORE INFORMATION
	================
	
	If you embed an Excel worksheet object in Word by choosing Object from the
	Insert menu and selecting one of the Excel object options (or if you edit an
	already embedded Excel object), you activate an Excel server session. To quit
	the Excel server session and return to the Word document, click Update on the
	File menu and then click Exit. When you quit Excel, the Excel object in the
	Clipboard is deleted from the Clipboard. Because the Clipboard no longer
	contains the Excel object, the Excel Object options are not available in Paste
	Special.
	
	Additional query words: object linking and embedding
	
	======================================================================
	Keywords          : kbdta word97 
	Technology        : kbWordSearch kbExcelSearch kbWord97 kbWord97Search kbZNotKeyword2 kbExcel97Search kbZNotKeyword3
	Version           : WINDOWS:97
	Issue type        : kbprb
	
	=============================================================================
	

{% endraw %}
