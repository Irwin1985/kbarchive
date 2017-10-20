---
layout: page
title: "Q88769: HOWTO: Test for End of File with CFile and CStdioFile"
permalink: /kb/088/Q88769/
---

## Q88769: HOWTO: Test for End of File with CFile and CStdioFile

	Article: Q88769
	Product(s): Microsoft C Compiler
	Version(s): winnt:1.0,2.0,2.1,2.2,4.0
	Operating System(s): 
	Keyword(s): kbFileIO kbMFC kbVC100 kbVC150 kbVC200 kbVC400 kbGrpDSMFCATL
	Last Modified: 03-MAY-2001
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- The Microsoft Foundation Classes (MFC), used with:
	   - Microsoft Visual C++ for Windows, 16-bit edition, versions 1.0, 1.5, 1.51, 1.52 
	   - Microsoft Visual C++, 32-bit Editions, versions 1.0, 2.0, 2.1, 2.2, 4.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	The Microsoft Foundation Classes (MFC) provide a CFileException class. The
	CFileException class includes public data members that contain operating- system
	errors and C Run-time errors that may be generated by certain file operations.
	
	MORE INFORMATION
	================
	
	The CFile and CStdioFile classes may throw a CFileException when certain error
	conditions occur; however, these classes do not throw a CFileException when the
	end of file is reached. If an application using the CFile or CStdioFile class
	needs to check for the end-of-file condition when reading from a file, the
	return values from the Read() and ReadString() member functions should be
	checked.
	
	CFile::Read returns the actual number of bytes read. If this number is less than
	the bytes requested, then the end of file has been reached.
	
	CStdioFile::ReadString returns a NULL pointer when the end of file has been
	reached.
	
	Additional query words: EOF TRY CATCH
	
	======================================================================
	Keywords          : kbFileIO kbMFC kbVC100 kbVC150 kbVC200 kbVC400 kbGrpDSMFCATL 
	Technology        : kbAudDeveloper kbMFC
	Version           : winnt:1.0,2.0,2.1,2.2,4.0
	Issue type        : kbhowto
	
	=============================================================================
	