# RPA_Training_Tutorials
This repository contains all the mini-projects I have developed. The primary goal of these projects was to explore and learn the full capabilities of UiPath Studio for automating repetitive processes.

# The mini-projects are:

## Work_with_files_folders_zip
Asks the user to select a .zip file containing client information. Renames the contracts using the folder (company) name and stores the contract files in a dedicated folder.

Preconditions:
- The .zip file contains folders named after client companies.
- The company folders contain contracts.
- The contract file names contain the string "Contract". 

Step 2: Extend

Further develop the automation process built in the previous lesson. The task is to iterate through the documents extracted from the .zip file and extend the functionality to sort not only the contracts but also the invoices into their respective folders. 
- The company folders contain contracts.
- The contract file names contain the string "Contract". 

Create a specified folder for invoices.
Rename all invoice files by appending the original invoice name with the respective company name (e.g., Invoice 001 01092022 Megatronic Incorporated.pdf).
Move the renamed invoice files to the Invoices folder.

Activities used:
* Browser For Input File
* Browser for Folder
* Get File info
* Multiple Assign
* Extract/Unzip Files
* For Each File in Folder
* Log Message
* IF
* Move File

## Check_App_State_&_Verify_Execution
Use the "Pick Activity", "Pick Branch Activity" and "verify execution" features to check if the user is logged in to the ACME page. 
If the user is not logged in, log an error message. If the user is logged in, navigate to Vendor > Add New Vendor section. 
Enter the details of the new vendor and verify that the vendor is added successfully. 

Use the following details of a vendor: 

Vendor ID: 10001 

Vendor Name: Ironman Inc 

Vendor Address: 1 MG Road 

Vendor City: Bengaluru 

Vendor Country : India 

### Main_Pick_&_Pick_Branch_&_Verify_Execution
Pick a branch to execute base on a trigger:
1. Login Botton found:
#### Login_to_Acme_Website
Display a message that the robot will login on ACME Website. Insert the email address and verify with <b>"Verify Execution"</b> if is correct. Insert the password. Login in the site and verify with <b>"Verify Execution"</b> if it successed. The two error that will appear if it is the case, catch them and save them in an argument and sent it to Sequence <i>"Main_Pick_&_Pick_Branch_&_Verify_Execution"</i>

Set the properties of the "Use Browser/Application" as follow:
- Close - Never
- Input Mode - Simulate
- Open - If not open

Activities used:
* Log Message
* Use Browser/Application
* Assign
* Try Catch
* Type Into (Verify Execution)
* Get Password
* Type Into
* Click (Verify Execution)


2. Navigate to add Vendor
### Navigate_to_add_Vendor
Display a meesage in console that the robot will navigate to the "Add Vendor" page.

Set the properties of the "Use Browser/Application" as follow:
- Close - Never
- Input Mode - Simulate
- Open - If not open

Activities used:
* Log Message
* Hover
* Click


3. Insert the Vendor
### Insert_new_Vendor
Use the <b>APP/WEB Recorder</b> to insert the vendor. When click on the "Save Vendor" verify with <b>"Verify Execution</b> if vendor was successfully add. Display a message box that tell the user the "Vendor added successfully"

Set the properties of the "Use Browser/Application" as follow:
- Close - Never
- Input Mode - Chromium API
- Open - If not open

Activities used:
* Use Browser/Application
* Type into
* Click (Verify Execution)
* Message Box

## Main_Parallel_Activity
To calculate the tax based on the amount entered by the user. Parallel property condition is set: userInput < 3000. if the user enters a value less then 3000, then the tax amount to be paid is 0. if the user enters a value greater then or equal to 3000, then 8% tax is calculated.

Activites used:
* Sequence
* Input Dialog
* Assign
* Log Message
* Message Box
* If

Methods:
* ToString
* vbCrLf

## FixMyWorkflow_StartingProject
Reads employee data from an Excel file, opens a browser window, navigates to the RPA Challenge Website, clicks on the "Start" button and enters the employee data into the RPA Challenge forms. 

This project learned me how to use the debug tool and how to fix a project when it has issues. 

Issues found and solutions applied:
1. Compilation Error: 
    Anchor 1 is not valid because no targeting methods are enabled.
<b>Solution</b>
Change the propery of "Target" from "TargetAnchorable" to null

2. Failed to find the excel sheet
<b>Solution</b>
Replace the old path with the correct path

3. Sheet name incorect writo
<b>Solution</b>
Identify the correct name of the sheet and replace from "Sheet12" to "Sheet1"

4. Click "Start" Button activity error: "The Element was not found"
<b>Solution</b>
I indicate correct the button on the Browser. Also because it's an activity on For Each Column I surrended with a Try-Catch to pass correctly. 

5. The "Type Into" activity write the name of the column and not the data from the current row.
<b>Solution</b>
I replace the old value with the CurrentRow value.

6. The value of attribut aaname is incorrect
<b>Solution</b>
The old value was "Submit1". The correct value is "Submit"



## Fix_a_RPA_Robot_add_new_functionalities
This Process will:
1. Search for "The Ice Age" movie in the IMBD webiste.
2. Get the IMDb RATING.
3. Displays it through the messagebox.

<b>Solving</b>

Changes I made:
1. I change the browser because the edge didn't have the extension installed.
2. Unified Application Target -> Selector:  from msedge.exe  to chrome.exe
3. I indicate "Search" UI Element 
4. I insert a "Type Into" Activity to insert the movie name
5. I indicate the "Movie Card" and "Rating" UI Element 

<b>Include the new requirements:</b>

1. Implement a user input prompt to capture the movie title from the user.
2. Use the movie title as input to search for the movie on the movie search page of the IMDB website.
3. Extract the IMDB rating of the searched movie from the website.
4. Display the retrieved IMDB rating through a message box.

<b>Implementation steps</b>:

1. Added an "Input Dialog" activity for the user to enter the movie name.
2. Added a "Get Text" activity to retrieve the correct movie name.
3. To identify the correct "Movie Card" UI Element, I modified the Fuzzy Selector to use the movie name from the variable. This addresses the issue with the Target and Anchor when the movie name changes.
4. Added a "Try-Catch" activity to handle missing ratings.

Activities used:
* Input Dialog
* Get Text
* Insert dinamically the movie name
* Try-Catch
* Assign

## Main_Extract_arrow_indicator_NSE_website
Use case 

Build the automation to accomplish the following tasks:

The process will navigate to the NSE website, extract the Sensex points, and retrieve the arrow indicator (red or green) to demonstrate the functionalities of:
- UiExplorer, 
- Property Explorer
- Get Attribute.

Once the robot has read the values and arrow indication, it'll write the details to the Excel report.

Activities used:
* Use Application/Browser
* Get Attribute
* Log Message
* Get Text
* Excel Process Scope
* Use Excel File
* Find First/Last Data Row
* If
* Write Cell

Methods used:
* Sheet
* Cell
* ToString
* Contains

## Main_Output_Methods_and_Output_Activities
In this sequence I will use previous sequence, "Input Methods and Input activities.xaml" and I will add functionallity for extraction transaction numbers from Double UI. For every transaction added in the Double UI, I will extract the "transaction no" and insert in the excel file to the corespondent row

Activities used:
* Use Application/Browser
* Read Range Workbook
* For Each Row in Data Table
* Type Into
* Click
* Get Text
* Message Box
* Assign
* Write Cell Workbook

## Extract_invoice_details_Web_Site
Develop a process using the Modern Design Experience that automates the extraction of invoice details. The process should be capable of performing the following actions: 

* Read an input Excel file with the invoice numbers. 
* Sign in to the ACME website. 
* Navigate to the invoice search page. 
* For each invoice number in the Excel file, search for the invoice number. 
* Extract the invoice details, including Vendor Tax ID, Invoice Item, Total, and Date. 
* Write the extracted invoice details to an Excel file stored in the project folder. 

Activities used:
* Invoke Workflow file
* Use Application/Browser
* Try Catch
* Get Text
* Assign
* If
* Log Message
* Click
* Type Into
* File Exits
* Read Range Workbook
* Write Range Workbook
* Add Data Column
* For Each Row in Data Table
* Else If
* Update Row Item

## Main_Extract_Author_and_Bookstores_from_statement
Parse an input string having the following format:

"You searched for author X. His books can be found at the following stores: Bookstore 1, Bookstore 2, Bookstore 3"

Print a new String containing the information about the author and the bookstoares. Format the output as follows:

"Availability for x: bookstore 1; <new line> bookstore 2; <new line> bookstoare 3;

Activities used:
* Assign
* Log Message

Methods used:
* Split
* First
* Substring
* LastIndexOf
* Length
* Trim
* ToString
* Last
* ToList
* String.Format
* String.Join
* vbCr

## Main_Extract_email_from_a_statement
Extract the email address from a statement without using Regex

Activities used:
* Assign
* If
* For Each
* Append Item to List

Methods used:
* Contains
* Split
* String.Format
* String.Join
* vbCr

## Main_Extract_email_with_RegEx
Create a workflow that extracts all the email addresses from the provided template file (in_Template_RegEx_application.txt) using regular expression.

Activities used:
* Read Text File
* Find Maching Patterns
* Log Message

Methods:
* String.Format
* String.Join

## Main_Extract_First_Last_Name_and_build_a_statement
Create a workflow using string activities that extracts the First and Last Name of an employee from a text file and uses this information to fill in the placeholder text in the string below.

"Hello Mr/Ms/Mrs <first_name> <last_name>, we would like to invite you to our product launch event next week. Please confirm by the end of current week."

Activities used:
* Read Text File
* Text to Left/Right - Custome
* Text to Left/Right - New line
* Modify Text
* Log Message

Methods:
* String.Format

## Main_Extract_Update_emails_from_files_in_folder
The user details are stored in a project folder called ‘Input_Files_Data_Manipulation’ and we’ll iterate through each of them to update the email address of all the users. 

Activities used:
* For Each File in Folder
* Read Text File
* Text to Left/Right
* Modify Text
* Change Type
* Modify Text - Combine Text
* Write Text File

Methods used:
* Path.Combine
* Path.GetFileName
* CurrentFile.FullName
* Replace

## Main_Merge_Sort_Lists

Create 2 lists: 
          First, "UKCities" with the "Build Collection Activity" and containts: "London" first element and "MACHESTER" the second.
          Second, "ESCities" by initializate as the defauld value egal to {"MADRID",  "valencia", "BARCELONA"}.

Request:
           1. Merge the 2 lists
           2. Sort them by using "Invoke Method Activity"
           3. Create a new list that contains the cities writo by TitleCase and display the new list with String.Join method in a "Log Message Activity"

Activities used:
* Build Collection
* Merge Collections
* Invoke Method - Sort
* For Each
* Assign
* Append Items to Collection
* Log Message

Methods:
* String.Join

## Main_Sort_Asc_Print_last_3_element_desc
Given a list of countries as input, please sort the list in alphabetical order, then print out the first three values in descending order in the Output Panel. 

Note: Use this value for the List initialization: {"Germany", "Spain", "Japan", "Brazil", "India", "China"}. 

Activities used:
* Invoke Method - Sort
* Invoke Method - Reverse
* Log Message

Methods used:
* String.Join
* List.GetRange

## Main_Tour_France_No_Victories_for_Dictionary_Elements
Given a dictionary containing a year and associated name as input:

Calculate the number of victories of each winner.
Print every winner's name with its corresponding number of victories in the output panel.  
Note: Initialize a dictionary of type (Int32, String) with the following value -  {{2006,"Oscar Pereiro"},{2007,"Alberto Contador"}, {2008, "Carlos Sastre"}, {2009,"Alberto Contador"}, {2010, "Andy Schleck"}, {2011, "Cadel Evans"}, {2012,"Bradley Wiggins"}, {2013,"Chris Froome"}, {2014,"Vincenzo Nibali"},{2015,"Chris Froome"},{2016,"Chris Froome"},{2017,"Chris Froome"}, {2018,"Geraint Thomas"}}

## Main_Calculate_Weekday_for_Dictionary_Element
Initialize an empty dictionary where to save the next information:
Key                   Value
Jamie Hanks     11/25/1989
Willie Gamer     01/08/1987
Patricia Shaw     04/14/2005

Requests:
     In what day of the week will be the birthdate of each person from dictionary in the current year?
     Display in console if the birthday was pass or it will be in future

Activities used:
* Assign
* For Each
* IF
* Log Message

Methods used:
* dictionaryVariable.Keys
* DateTime.Parse
* DateTime.Today.Year
* birthday.Month
* birthday.Day
* String.Format

## Main_Extract_Addresses_RegEx
Searches and matches a set of items from a string containing multiple items, them outputs the matched results

Activities used:
* Assign
* Find Matching Patterns (RegEx / Regexp)
* For Each
* Log Message

## Main_Input Methods and Input activities
Create an automation to deposit a transanction in the Double UI application. In this project I will be using "Type Into", "Click", "Use Application/Browser" activities to accomplish the automation.

Activities used to create the RPA Robot:
* Use Application/Browser
* Type Into
* Click
