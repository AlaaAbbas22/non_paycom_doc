## A quick guide on how to get started!

## Accessing Scripts, Approval Sheet and WS Payroll Log Form

[Approval Sheet of 2023/2024](https://docs.google.com/spreadsheets/d/1vwHoN5UWt_E6wVMi75IQpFi5OYvGdYd--cWBqI4lHpw/edit)

This spreadsheet is the starting point. This sheet is Paycom for students not on Paycom. There we collect the data for the students' hours and managers also approve/remove hours from students.

Also, the script of the Spreadsheet I am referring to is the Google Apps Script associated with the Approval Sheet. You can find it by clicking on the Extensions tab in the spread sheet and then Apps Script.

For the script of the WS Payroll Log Form, you can find it in the editing page of the form by the three dots in the top right -> Script Editor.

Also, the meaning of the function runs every week, two weeks etc... is that there is a trigger by time for these functions in the Google Apps Script editor.

## Quick journey

### Students submission

By the end of the pay period, the students are asked to submit the hours they worked during that pay period, through this [WS Payroll Log Form](https://forms.gle/jCmz9uQmdrzB79Zn8). The responses are collected in a sheet in the Approval Sheet spread sheet called `Submissions_Source`. This is not what we process. Another sheet called `Submissions` imports this data and associates a key with each entry at _Column(A) & Column(J)_. The key is as follows: "[student email address] - [PP code]", e.g. "alaa@uni.minerva.edu - PP1" for the submission of Alaa in pay period 1.

Before the submission day (Thursday), students are sent an automatic reminder to submit their hours. You can find the function in the script of the spreadsheet as a function called `contractorsSubmissionReminder` which runs every two weeks to remind them.

### Managers approval

This data is imported (using the key defined above) into the most important sheet which is the first sheet in the spreadsheet, typically called by the name of the pay period it refers to, e.g. PP1 for submissions of PP1. After the submission day (Friday end of Pay period), the google form is automatically locked using the `restrict` function in the script of the form.

The managers get an automated email on Sunday to go ahead and approve/remove students' hours. This is done in the same sheet which is the first sheet in the spreadsheet. The function for sending the managers reminders is `managerApprovalReminder` in the spreadsheet script.

### Shifting sheets

Managers receive the link to the spreadsheet and go and change the approval column of their interns to YES or NO. Then, on Tuesday/Wednesday, the sheet of the previous pay period is being locked, sent to the end of the sheet and another sheet is created for the current pay period. Let's say managers approved PP1, PP1's sheet go to the end and a new sheet is created for PP2. This process is done via the function `copySheet` in the script of the approval sheet.

### Students come back

On the next Saturday which is mid of the pay period, the form for logging hours is unlocked, and the students are once again able to submit hours but for this pay period. On Thursday, 1 day before end of PP, they receive the reminder and the cycle goes on.

## Things to update on arrival

1. The sheet `Config` in the Approval is very important. Please make sure it is always up to date. Look up the Position Tracker of the year or the Master DB for this one.
2. Make sure the sudents names in the PP sheet in the very beginning of the spreadsheet is correct because it is not updated automatically (yet).
3. 

## Important spreadsheets and their content and why they are important:

1. The Approval Sheet
2. The Position tracker
3. BDC payment summary
4. Bank Information sheet
5. W8/9
