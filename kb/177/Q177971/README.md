---
layout: page
title: "Q177971: WD97: Type Mismatch Error Running Converted WordBasic Macro"
permalink: /kb/177/Q177971/
---

## Q177971: WD97: Type Mismatch Error Running Converted WordBasic Macro

{% raw %}

	Article: Q177971
	Product(s): Word 97 for Windows
	Version(s): WINDOWS:97
	Operating System(s): 
	Keyword(s): kbcode kbProgramming word8 kbwordvba word97
	Last Modified: 13-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Word 97 for Windows 
	-------------------------------------------------------------------------------
	
	
	SYMPTOMS
	========
	
	When you run a macro that was converted from WordBasic to Microsoft Visual Basic
	for Applications, you receive the following error message:
	
	  Type Mismatch Error
	
	CAUSE
	=====
	
	If you converted a WordBasic macro that contains statements similar to the
	following:
	
	     x = Val(FontSize())
	
	the converted code may appear as:
	
	     x = WordBasic.Val(WordBasic.FontSize())
	
	This converted statement causes the macro to halt with the "Type Mismatch" error
	message.
	
	RESOLUTION
	==========
	
	Microsoft provides programming examples for illustration only, without warranty
	either expressed or implied, including, but not limited to, the implied
	warranties of merchantability and/or fitness for a particular purpose. This
	article assumes that you are familiar with the programming language being
	demonstrated and the tools used to create and debug procedures. Microsoft
	support professionals can help explain the functionality of a particular
	procedure, but they will not modify these examples to provide added
	functionality or construct procedures to meet your specific needs. If you have
	limited programming experience, you may want to contact a Microsoft Certified
	Partner or the Microsoft fee-based consulting line at (800) 936-5200. For more
	information about Microsoft Certified Partners, please visit the following
	Microsoft Web site:
	
	  http://www.microsoft.com/partner/referral/
	
	For more information about the support options that are available and about how
	to contact Microsoft, visit the following Microsoft Web site:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	To resolve this problem, remove "WordBasic." from the Val function as in the
	following example:
	
	     x = Val(WordBasic.FontSize())
	
	-or-
	
	Convert the statement to the Visual Basic equivalent:
	
	     x = Selection.Font.Size
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in the Microsoft products listed at
	the beginning of this article.
	
	REFERENCES
	==========
	
	For more information about getting help with Visual Basic for Applications,
	please see the following article in the Microsoft Knowledge Base:
	
	  Q163435 VBA: Programming Resources for Visual Basic for Applications
	
	Additional query words:
	
	======================================================================
	Keywords          : kbcode kbProgramming word8 kbwordvba word97 
	Technology        : kbWordSearch kbWord97 kbWord97Search kbZNotKeyword2
	Version           : WINDOWS:97
	Issue type        : kbbug
	
	=============================================================================
	

{% endraw %}
