---
layout: page
title: "Q128584: PC WSPlus: Restoring Schedule+ .CAL File Information"
permalink: /kb/128/Q128584/
---

## Q128584: PC WSPlus: Restoring Schedule+ .CAL File Information

{% raw %}

	Article: Q128584
	Product(s): Microsoft Schedule+ for Windows
	Version(s): WINDOWS:1.0
	Operating System(s): 
	Keyword(s): 
	Last Modified: 12-SEP-1999
	
	1.00
	WINDOWS
	kbtool kbusage kberrmsg kbtshoot
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Schedule+ for Windows, version 1.0 
	-------------------------------------------------------------------------------
	
	SYMPTOMS
	========
	
	When you attempt to restore a Schedule+ calendar (.CAL) file by copying it over
	an existing Schedule+ calendar file with the same name, the following error will
	occur:
	
	  The local copy of your schedule file could not be accessed in the location
	  specified in your schdplus.ini file.
	
	You may then be prompted with a Find Local File dialog box to locate the correct
	calendar file. If the backup calendar file is selected, the following error will
	occur:
	
	  This is not a valid local schedule file. Is it okay to delete it?
	
	If OK is chosen, the calendar file is deleted, and a new empty calendar file with
	the same name is created.
	
	CAUSE
	=====
	
	If Schedule+ is started with a calendar (.CAL) file that was copied over an
	existing calendar file with the same name in an attempt to restore the contents,
	Schedule+ will force you to either delete the calendar file or exit Schedule+.
	
	RESOLUTION
	==========
	
	NOTE: There is an option for Schedule+ to import a .CAL file, but this is for
	importing files created by the calendar program included in Microsoft Windows
	3.0, 3.1, and 3.11.
	
	Two procedures for importing Schedule+ calendar files are below:
	
	Procedure 1
	-----------
	
	This first procedure should be followed if no corruption exists in the CAL
	directory of the workgroup postoffice, or in any .CAL file in the CAL
	subdirectory of the workgroup postoffice.
	
	To properly restore a calendar file that was not exported to a Schedule (.SCH)
	file, follow these steps on the workstation:
	
	1. Exit and sign out of Mail and Schedule+.
	
	2. Exit Windows for Workgroups.
	
	3. Rename the valid Schedule+ .CAL file; for example:
	
	  ren <username>.cal backup.cal
	
	4. Rename the .CAL file with the information you wish to restore; for example,
	  to the current .CAL file name:
	
	  ren <oldusername>.cal <username>.cal
	
	5. If the workgroup postoffice is accessed through the Windows network, Start
	  Windows for Workgroups without loading the network by typing:
	
	  win /n
	
	  If the workgroup postoffice is accessed through other third party networks, do
	  not perform a network login; then start Windows for Workgroups.
	
	6. Start Schedule+. You should receive the following error message:
	
	  Mail could not connect to your Mail server. The Mail server path in your
	  MSMAIL.INI file is missing or invalid.
	
	  Click OK.
	
	7. You then receive the message:
	
	  Would you like to work offline?
	
	  Click OK.
	
	8. In the Mail Sign In dialog box, sign in with your current password.
	
	9. You will receive the message:
	
	  Your passwords don't match. Type your schedule file password.
	
	  Enter the password for the .CAL file with the information you wish to add to
	  the current .CAL file, and click OK.
	
	  You should now see the contents of the .CAL file you wish to add to the
	  current .CAL file.
	
	10. From the File menu, choose Export Appointments...
	
	11. In the Export Appointments dialog box, select Schedule+ for the file format.
	  Select All for the Schedule Range. Select the Include Daily Notes option.
	  Click OK.
	
	12. You will be prompted with the Export Appointments dialog box. The export
	  Schedule file name and location may be changed here, but it will default to
	  <username>.SCH in the Windows directory. Click OK.
	
	  The export file will be created.
	
	13. Exit and sign out of Schedule+.
	
	14. Exit Windows for Workgroups.
	
	15. Rename the .CAL file with the information that was exported back to its
	  original name; for example:
	
	  ren <username>.cal <oldusername>.cal
	
	16. Rename the current installation's .CAL file, back to its original name; for
	  example,
	
	  ren backup.cal <username>.cal
	
	17. If the workgroup postoffice is accessed through the Windows network, Start
	  Windows for Workgroups normally, loading the network drivers.
	
	  If the workgroup postoffice is accessed through other third party networks,
	  perform a network login; then start Windows for Workgroups.
	
	18. Start Schedule+.
	
	19. Login at the Mail Sign In. Schedule+ should now appear with the current .CAL
	  file information displayed.
	
	20. From the File menu, choose Import Appointments...
	
	21. In the file name field, specify <username>.SCH, which is the file you
	  exported in step 12.
	
	22. The Import Format dialog should appear. In the Import File From list box,
	  select Schedule+ as the import format. Select Add All Appointments. Select
	  Ask About Conflicting Appointments. Click OK.
	
	  The information will be imported into the current .CAL file.
	
	23. If there are existing appointments, you will receive the message:
	
	  This appointment will conflict with an existing appointment in your schedule.
	  Do you want to add it anyway? <Day of week>, <Month> <Day>,
	  <Year>, Time>AM/PM - <Time>AM/PM
	  <Appointment Description>
	
	  Click Yes to add the appointment. Click No to discard the appointment and not
	  add it.
	
	Procedure 2
	-----------
	
	The second procedure should be followed if all of the following conditions
	exist:
	
	1. It has been determined that corruption exists in the CAL directory of the
	  workgroup postoffice, or in any .CAL file in the CAL subdirectory of the
	  workgroup postoffice.
	
	2. You have a calendar file that was not exported to a .SCH file, and want to
	  import it.
	
	3. You have already exported and backed up any current information from your
	  Schedule file, and reinitialized Mail and Schedule+ by renaming your .INI
	  files.
	
	To properly restore a calendar file that was not exported to a Schedule (.SCH)
	file, and the above three conditions exist, follow these steps:
	
	1. Exit Mail and Schedule+ on ALL machines.
	
	2. Using a MS-DOS prompt or File Manager, connect to the your WGPO directory.
	
	3. In the CAL subdirectory, delete the entire contents of the CAL subdirectory.
	  Do NOT delete the subdirectory itself.
	
	  NOTE: Be absolutely certain the SCHEDULE.KEY file is deleted from the CAL
	  subdirectory. By default, the file is marked with a hidden attribute.
	
	4. Disconnect from the WGPO.
	
	5. Copy your backup .CAL file over the new .CAL file (which was recently created
	  during Mail and Schedule+ re-initialization) already in the WINDOWS
	  directory.
	
	6. Start Windows for Workgroups.
	
	7. Start Schedule+.
	
	8. When you are prompted with the Confirm Password dialog box, enter the
	  password for the offline Schedule+ file.
	
	  After the correct password has been entered, you will be prompted for the
	  current Mail/Schedule+ password.
	
	  When the correct Mail/Schedule+ password has been entered, Schedule+ will
	  start, using the backup Calendar file as your primary calendar file.
	
	9. Import the backed up Mail and Schedule+ information.
	
	MORE INFORMATION
	================
	
	To correctly and fully backup a Schedule+ calendar file:
	
	1. Log into Schedule+.
	
	2. From the File menu, choose Export Appointments...
	
	3. In the Export Appointments dialog: select Schedule+ for the file format.
	  Select All for the Schedule Range. Select the Include Daily Notes option.
	  Click OK.
	
	4. You will be prompted with the Export Appointments dialog. The export Schedule
	  file name and location may be changed here, but it will default to
	  <username>.SCH in the Windows directory. Click OK.
	
	  The export file will be created. Schedule+ may be safely reinitialized.
	
	Additional query words: schedule plus 1.00 sched+ wfw wfwg schedplus
	
	======================================================================
	Keywords          :  
	Technology        : kbScheduleSearch kbSchedule100
	Version           : WINDOWS:1.0
	
	=============================================================================
	

{% endraw %}
