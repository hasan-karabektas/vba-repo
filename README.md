# vba-repo
<u><b>VB codes powering MS Office Suite tools</b></u>

This repository contains codes written for tasks automation and fastening purposes, within the context of processing daily administrative and financial workloads, as well as contributing to periodical reporting, budget follow-up and account closings.

<u><b>Masterfile</b></u>

This code, a VBA subprocedure, has been written with the purpose of gathering data, lying originally in different .xls files, within in a single centralized masterfile under the form of a single continued list. The raw data in question is the registered time (hh:mm:ss), as entered by every staff member, in weekly time registration files along with other information. Every row is a unique entry, where the staff member enters his/her ID, the code of the task s/he worked on, the description of the entry, and the time (hh:mm:ss) which was spent.
The .xls files containing the data are located inside a single folder, with one .xls file being assigned for every week of the calendar year (hence, the folder being meant to contain 52 .xls files by the end of the calendar year). 
The VBA macro code I wrote contains one Do Until, two For Next and 4 nested Do While Loops (with the first Do while loop based on the directory and the .xls files being saved therein, and the other three Do While loops being based on cells within each cell range inside the the 3 categories of sheet: project time registry, application time registry and other time registry). An integer-type variable is also added and incremented from 1 onwards, inside first Do While Loop, based the Directory.
The code works succesfully, first creating a new workbook on the Desktop, with three relevant sheets being created therein, all the while deleting the already-existing default sheets at the creation of the workbook; thereafter, the code copy-pastes the header parts from the Dir. folder, for each respective sheet in the masterfile. That way, all 3 sheets in the Masterfile (for each of the 3 categories) are ready for the data gathering. We add an extra column with reference to the week, which shall be filled in through the variable, being incremented according to the reference of the week for which data shall be transferred (1 to 52). Once the collection of data is the centralized file is complete, the macro adapts the format of the column containing the time to a proper time-number format in Ms Excel, the macro runtime is then completed and this is announced through a message box. The data centralized in the masterfile is then ready for further analysis and registration.

<b>Email_Automation</b>

Based on a For Each Next Loop integrating an inner condition, this code generates automated emails via the outlook emailing app, using a text template as message body, and customizing each email to be sent on the basis of data retrieved from an .xls file's table; with one email being sent for each row, insofar as the conditions which were set out are being met. Each email is dispatched based on variables referencing the key information (name and email address of the addressee, and other information) which are retrieved from the relevant columns of the active row. 
The code starts with the declaration of object variables to activate and refers to relevant applications and files, as well as to the table from which most of the variable data shall be retrieved. Later, the email is composed with the referencing of variables; the body of the message is in html format, so that customized, ad hoc adaptations to the format can be performed easily. The outlook signature of the user is also included in the emails which are going to be forwarded. The running of the code is completed with the dispatching of the emails for all rows.   
