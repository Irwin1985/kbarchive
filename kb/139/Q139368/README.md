---
layout: page
title: "Q139368: PC NTMMTA: SESSION.LOG Displays Pulse as Baud Rate"
permalink: /kb/139/Q139368/
---

## Q139368: PC NTMMTA: SESSION.LOG Displays Pulse as Baud Rate

{% raw %}

	Article: Q139368
	Product(s): Microsoft Mail For PC Networks
	Version(s): 3.5
	Operating System(s): 
	Keyword(s): 
	Last Modified: 20-MAY-2002
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Mail Multitasking MTA for Windows NT, version 3.5 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	The Microsoft Windows NT Multitasking MTA (NT MMTA) may incorrectly log Pulse
	for 38,400 baud rate communications, and Touch Tone for 57,600 baud rate
	communication links.
	
	RESOLUTION
	==========
	
	A supported fix that corrects this problem is now available from Microsoft, but
	has not been fully regression tested and should be applied only to systems
	experiencing this specific problem.
	
	To resolve this problem, contact Microsoft Product Support Services to obtain the
	fix. For a complete list of Microsoft Product Support Services phone numbers and
	information on support costs, please go to the following address on the World
	Wide Web:
	
	  http://support.microsoft.com/default.aspx?scid=fh;EN-US;CNTACTMS
	
	The English version of this fix should have the following file attributes or
	later:
	
	  File Name      Version
	  ----------------------
	  External.exe   3.5.25
	
	This hotfix has been posted to the following Internet location as Exty2k.exe:
	
	  ftp://ftp.microsoft.com/bussys/mail/pcmail-public/All-Y2K/
	
	
	STATUS
	======
	
	Microsoft has confirmed this to be a problem in Microsoft Mail Multitasking MTA
	for Windows NT version 3.5.
	
	MORE INFORMATION
	================
	
	The communication rate used by the modem to establish a connection to the remote
	modem is logged based on entries in the modem script. This rate normally appears
	as a connection statement, where the baud rate appears after the word CONNECT,
	for example,
	
	  >>>CONNECT 28,800<<<
	
	NOTE: The connection rate is the more accurate rate when determining the rate of
	information exchange between the External Mail program and the Remote External
	or one of Remote Mail programs.
	
	The baud statement is used in the modem script to dictate the baud rate of the
	COM port to a specified value. The baud rate entry is recorded after the modem
	has been initialized by the External Mail program. The Baud Rate entry in the
	SESSION.LOG of the External Mail program is used to display the connection rate
	established by the External program between the serial port and the local
	modem.
	
	The baud rate entry can be located in the COMM settings section of the modem
	initialization in the SESSION.LOG.
	
	For example,
	
	  Initializing Modem:
	  Line Speed : 57600
	  OUT: [AT&F?]
	  IN: [??OK??]
	  OUT: [AT&C1&D2E0L0M1V0X3&K3W2?]
	  IN: [AT&C1&D2E0L0M1V0X3&K3W2?0?]
	  OUT: [ATS0-0S7=45S9=6S10=50S12=50?]
	  IN: [0?]
	  COMM settings:
	  Comm. Port: Com1
	  Baud Rate: Touch Tone
	  Dial Mode: Touch Tone
	  Script File: <Script Name>
	  Initialization complete. Ready.
	
	The only valid baud rates that the External Mail program can use to set the
	serial port for communications with the modem are 300, 1200, 2400, 4800, 9600,
	19200, 38400, and 57600.
	
	
	Additional query words: 3.50 windows nt baud=pulse baud=tone post35fix
	
	======================================================================
	Keywords          :  
	Technology        : kbZNotKeyword2 kbMailSearch kbZNotKeyword3 kbMailMMTA350NT
	Version           : :3.5
	Issue type        : kbbug
	Solution Type     : kbfix
	
	=============================================================================
	

{% endraw %}
