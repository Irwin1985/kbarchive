---
layout: page
title: "Q113812: HOWTO: Create a Menu with a Variable Pad"
permalink: /kb/113/Q113812/
---

## Q113812: HOWTO: Create a Menu with a Variable Pad

	Article: Q113812
	Product(s): Microsoft FoxPro
	Version(s): MS-DOS:2.0,2.5,2.5a,2.5b,2.6; WINDOWS:2.5,2.5a,2.5b,2.6,3.0,5.0,6.0
	Operating System(s): 
	Keyword(s): kbcode kbBuilder kbvfp300 kbvfp500 kbvfp600
	Last Modified: 09-FEB-2000
	
	-------------------------------------------------------------------------------
	The information in this article applies to:
	
	- Microsoft Visual FoxPro for Windows, versions 3.0, 5.0, 6.0 
	- Microsoft FoxPro for MS-DOS, versions 2.0, 2.5, 2.5a, 2.5b, 2.6 
	- Microsoft FoxPro for Windows, versions 2.5, 2.5a, 2.5b, 2.6 
	-------------------------------------------------------------------------------
	
	SUMMARY
	=======
	
	This article demonstrates how to make a menu choice vary with the contents of a
	database field by using the Menu Builder and very little code.
	
	MORE INFORMATION
	================
	
	Use one of the following examples, depending on your version of FoxPro.
	
	FoxPro 2.x Example
	------------------
	
	The following steps show how to create a menu that contains a pad whose name
	equals the CITY field of the current record in SALESMAN.DBF, one of the sample
	databases provided with FoxPro.
	
	1. In the Command window, issue the following commands to set the default
	  working directory to the TUTORIAL subdirectory and open the SALESMAN.DBF
	  database:
	
	        SET DEFAULT TO C:\<FoxPro directory>\TUTORIAL
	        USE SALESMAN
	
	2. In the Command window, type the following command to display the database's
	  structure:
	
	        DISPLAY STRUCTURE
	
	  Note that the database contains a character field called CITY.
	
	3. In the Command window, type the following command to create a menu design
	  called CHGPAD:
	
	        CREATE MENU CHGPAD
	
	4. In the Prompt box, type the following text:
	
	  " \<"+alltrim(city)+"" (without the quotation marks)
	
	  Notes
	  -----
	
	   - Lowercase is not required above, but it will make searching for this text
	     later in the generated code easier.
	
	   - "\<" tells FoxPro to highlight the first letter of this menu pad and
	     use it as a hot key (this will be the first letter of the city's name).
	     ALLTRIM(CITY) removes leading and trailing spaces from the contents of the
	     CITY field.
	
	   - The quotation marks are used in anticipation of the menu code that will be
	     generated by the Menu Builder (see the DEFINE PAD statement in step 8).
	
	5. Choose Options, then Pad Name, and enter CityPad for the pad name. Choose OK
	  to close the Pad Name dialog box. Choose OK again to close the Options dialog
	  box.
	
	6. To generate the menu-code file CHGPAD.MPR, choose Generate from the Program
	  menu. Choose Yes when asked if you want to save the menu design CHGPAD.MNX,
	  and then choose Generate in the subsequent dialog box.
	
	7. Press ESC to close the menu-design window.
	
	8. In the Command window, view the generated menu code by typing:
	
	        MODIFY COMMAND CHGPAD.MPR
	
	  Look for the following DEFINE PAD statement in the code:
	
	        DEFINE PAD CityPad OF _MSYSMENU PROMPT "\<"+alltrim(city)+"" ;
	        COLOR SCHEME 3
	
	  Note that the item entered in the Prompt box during menu design
	  (\<"+alltrim(city)+") was inserted in the menu code. The two quotation
	  marks you typed in were needed to close off the two quotation marks
	  automatically inserted by the Menu Builder. This results in the concatenation
	  of CITY as a field, not as the word "CITY".
	
	9. Select the above line of code, copy it to the Clipboard by pressing CTRL+C,
	  and press the ESC key to return to the Command window.
	
	10. In the Command window, type "MODIFY COMMAND CHGPAD" (without the quotation
	  marks), and then type the following program lines (you can paste the DEFINE
	  PAD line below from the Clipboard by pressing CTRL+V):
	
	         SET DEFAULT TO C:\<FoxPro directory>\TUTORIAL
	         USE SALESMAN
	         GO TOP              && Go to 1st record
	         DO CHGPAD.MPR       && Display CHGPAD menu with 1st record's city
	         WAIT WINDOW "The menu pad shows the first record's city...press ;
	            the SPACEBAR"
	
	         SKIP                && Go to 2nd record; redefine pad for its city
	         DEFINE PAD CityPad OF _MSYSMENU PROMPT "\<"+alltrim(city)+"" ;
	         COLOR SCHEME 3
	         WAIT WINDOW "The menu pad shows the next record's city...press ;
	            the SPACEBAR"
	
	        SET SYSMENU TO DEFAULT  && Restore system menu
	
	11. Press CTRL+W to exit and save this program as CHGPAD.PRG.
	
	12. In the Command window, type the following command to execute the program:
	
	         DO CHGPAD
	
	You can apply the above technique to a screen by placing the aforementioned
	DEFINE PAD statement in the screen's READ-level SHOW clause; this way, whenever
	SHOW GETS is used to refresh a screen's GET fields (for example, when displaying
	another record), the menu pad will be updated to reflect the new record's city.
	
	Visual FoxPro Example
	---------------------
	
	1. In the Command window, issue the following commands to set the default
	  working directory to the TUTORIAL subdirectory and open the EMPLOYEE.DBF
	  database:
	
	        SET DEFAULT TO C:\VFP\SAMPLES\DATA
	        USE EMPLOYEE
	
	2. In the Command window, type the following command to display the database's
	  structure:
	
	        DISPLAY STRUCTURE
	
	  Note that the database contains a character field called CITY.
	
	3. In the Command window, type the following command to create a menu design
	  called CHGPAD:
	
	        CREATE MENU CHGPAD
	
	4. In the Prompt box, type the following text:
	
	  " \<"+alltrim(city)+"" (without the quotation marks)
	
	  Notes
	  -----
	
	   - Lowercase is not required above, but it will make searching for this text
	     later in the generated code easier.
	
	   - "\<" tells FoxPro to highlight the first letter of this menu pad and
	     use it as a hot key (this will be the first letter of the city's name).
	     ALLTRIM(CITY) removes leading and trailing spaces from the contents of the
	     CITY field.
	
	   - The quotation marks are used in anticipation of the menu code that will be
	     generated by the Menu Builder (see the DEFINE PAD statement in step 8).
	
	5. Choose Options, then Pad Name, and enter CityPad for the pad name. Choose OK
	  to close the Pad Name dialog box. Choose OK again to close the Options dialog
	  box.
	
	6. To generate the menu-code file CHGPAD.MPR, choose Generate from the Menu
	  menu. Choose Yes when asked if you want to save the menu design CHGPAD.MNX,
	  and then choose Generate in the subsequent dialog box.
	
	7. Press ESC to close the menu-design window.
	
	8. In the Command window, view the generated menu code by typing:
	
	        MODIFY COMMAND CHGPAD.MPR
	
	  Look for the following DEFINE PAD statement in the code:
	
	        DEFINE PAD CityPad OF _MSYSMENU PROMPT "\<"+alltrim(city)+"" ;
	        COLOR SCHEME 3
	
	  Note that the item entered in the Prompt box during menu design
	  (\<"+alltrim(city)+") was inserted in the menu code. The two quotation
	  marks you typed in were needed to close off the two quotation marks
	  automatically inserted by the Menu Builder. This results in the concatenation
	  of CITY as a field, not as the word "CITY".
	
	9. Select the above line of code, copy it to the Clipboard by pressing CTRL+C,
	  and press the ESC key to return to the Command window.
	
	10. In the Command window, type "MODIFY COMMAND CHGPAD" (without the quotation
	  marks), and then type the following program lines (you can paste the DEFINE
	  PAD line below from the Clipboard by pressing CTRL+V):
	
	         SET DEFAULT TO C:\VFP\SAMPLES\DATA
	         USE EMPLOYEE
	         GO TOP              && Go to 1st record
	         DO CHGPAD.MPR       && Display CHGPAD menu with 1st record's city
	         WAIT WINDOW "The menu pad shows the first record's city...press ;
	            the SPACEBAR"
	
	         SKIP                && Go to 2nd record; redefine pad for its city
	         DEFINE PAD CityPad OF _MSYSMENU PROMPT "\<"+alltrim(city)+"" ;
	         COLOR SCHEME 3
	         WAIT WINDOW "The menu pad shows the next record's city...press ;
	            the SPACEBAR"
	
	        SET SYSMENU TO DEFAULT  && Restore system menu
	
	11. Press CTRL+W to exit and save this program as CHGPAD.PRG.
	
	12. In the Command window, type the following command to execute the program:
	
	         DO CHGPAD
	
	You can apply the above technique to a form by placing the aforementioned DEFINE
	PAD statement in the form's refresh property; this way, whenever you move to the
	next record in the table, the menu pad will be updated to reflect the new
	record's city.
	
	Additional query words:
	
	======================================================================
	Keywords          : kbcode kbBuilder kbvfp300 kbvfp500 kbvfp600 
	Technology        : kbVFPsearch kbAudDeveloper kbFoxproSearch kbZNotKeyword3 kbFoxPro200DOS kbFoxPro250DOS kbFoxPro250aDOS kbFoxPro250bDOS kbFoxPro260DOS kbFoxPro260 kbFoxPro250 kbFoxPro250a kbFoxPro250b kbVFP300 kbVFP500 kbVFP600
	Version           : MS-DOS:2.0,2.5,2.5a,2.5b,2.6; WINDOWS:2.5,2.5a,2.5b,2.6,3.0,5.0,6.0
	Issue type        : kbhowto
	
	=============================================================================
	