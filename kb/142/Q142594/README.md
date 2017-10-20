---
layout: page
title: "Q142594: INFO: Caveats for Using Empty Top-Level Projects in Dev. Studio"
permalink: /kb/142/Q142594/
---

## Q142594: INFO: Caveats for Using Empty Top-Level Projects in Dev. Studio

	Article: Q142594
	Product(s): Microsoft C Compiler
	Version(s): 4.0,4.1,4.2,5.0,6.0
	Operating System(s): 
	Keyword(s): kbide kbVC400 kbVC410 kbVC420 kbVC500 kbVC600 kbGrpDSTools
	Last Modified: 04-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual C++, 32-bit Editions, versions 4.0, 4.1 
	- Microsoft Visual C++, 32-bit Enterprise Edition, versions 4.2, 5.0, 6.0 
	- Microsoft Visual C++, 32-bit Professional Edition, versions 4.2, 5.0, 6.0 
	- Microsoft Visual C++, 32-bit Learning Edition, version 6.0 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article discusses the process needed to set up a project workspace such
	that it builds multiple targets that are related. You might want to do this if,
	for example, you want to set up a workspace to build several related .exe files,
	and .dll files that they can call. This scenario is described in the Visual C++
	User's Guide online documentation in the "Empty Top-Level Project with Multiple
	Subprojects" section.
	
	The section of the documentation includes a sample scenario where an empty
	top-level project has two subprojects that build .exe files, and one of the .exe
	projects has a subproject that builds a DLL. The description of this scenario
	implies that in general you can set up a top-level project that has no source
	files, and it implies that the type of the top-level project and the subprojects
	involved are unimportant; they can be any type. This is not the case. The types
	of the projects and subprojects involved are important.
	
	MORE INFORMATION
	================
	
	In certain scenarios, you get the following messages in the output window when
	you set the default project configuration to the empty top-level project in
	order to build all the subprojects:
	
	  LINK : warning LNK4001: no object files specified; libraries used
	  LINK : error LNK2001: unresolved external symbol _mainCRTStartup
	  fatal error LNK1120: 1 unresolved externals
	  Error executing link.exe.
	
	This happens if you have one or more static library or DLL projects that are
	immediate subprojects of the empty top-level project. Or, if the top-level
	project is a DLL and the subproject is a resource-only DLL, the following error
	will appear:
	
	  Fatal Error C1001 Internal Compiler Error Compiler File MSC1.CPP Line 1786
	
	Developer Studio invokes the linker to build an output file for the top-level
	project and automatically tries to link with the library files built by the
	subprojects (DLL subprojects create import libraries). This behavior occurs even
	if the top-level project is empty, meaning that it does not include source
	files.
	
	If you want to set up a project workspace where the static library or DLL
	projects are immediate subprojects of an empty top-level project, you need to
	make the top-level project type be Makefile. In addition, you need to change the
	build settings for the Makefile project so the Build command line setting is
	blank. In other words, you do not want Developer Studio to invoke any command
	for the empty top-level project. This allows you to set up the correct
	dependency relationship between the top-level project and its subprojects, and
	it prevents Developer Studio from attempting to create an output file for the
	top-level project.
	
	With Visual C++ 5.0 where the DLL projects are immediate subprojects of an empty
	top-level project, you can select the Ignore export library check box in the
	project settings for the DLL subprojects, Link tab, General category. This tells
	the build system not to automatically link the empty top-level project with the
	import library generated by the DLL subprojects. This check box is not available
	for static libraries.
	
	Additional query words: checkbox
	
	======================================================================
	Keywords          : kbide kbVC400 kbVC410 kbVC420 kbVC500 kbVC600 kbGrpDSTools 
	Technology        : kbVCsearch kbVC400 kbAudDeveloper kbVC410 kbVC420 kbVC500 kbVC600 kbVC32bitSearch kbVC500Search
	Version           : :4.0,4.1,4.2,5.0,6.0
	Issue type        : kbinfo
	
	=============================================================================
	