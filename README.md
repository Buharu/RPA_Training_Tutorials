# RPA_Training_Tutorials
This repository contains all the mini-projects I have developed. The primary goal of these projects was to explore and learn the full capabilities of UiPath Studio for automating repetitive processes.

# The mini-projects are:
## Main_Input Methods and Input activities
Create an automation to deposit a transanction in the Double UI application. In this project I will be using "Type Into", "Click", "Use Application/Browser" activities to accomplish the automation.

Activities used to create the RPA Robot:
* Use Application/Browser
* Type Into
* Click

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

