# RPA_Training_Tutorials
This repository contains all the mini-projects I have developed. The primary goal of these projects was to explore and learn the full capabilities of UiPath Studio for automating repetitive processes.

# The mini-projects are:

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
