## ***A Quick Guide on How to Get Started!***
- ***Have a look at the get started of the [form scripts](/non_paycom_doc/form_scripts) and [sheet scripts](/non_paycom_doc/sheet_scripts) for a correct set up for the automation, as well.***
## **Accessing the Sheets**
*Accessing Scripts, Approval Sheet, and WS Payroll Log Form*

[Approval Sheet of 2024/2025](https://docs.google.com/spreadsheets/d/1h--NTEjqyUzLndCXJbNB5af5pqv4vK5-beLuPCsWYnE/edit?gid=566099288#gid=566099288)

- This spreadsheet is the starting point. It serves as Paycom for students not on Paycom. It collects data for the students' hours, and managers also approve or remove hours from students.
- The script of the spreadsheet is the Google Apps Script associated with the Approval Sheet. You can find it by clicking on the **Extensions** tab in the spreadsheet and then selecting **Apps Script**.
- The script for the WS Payroll Log Form is in the editing page of the form. Click the three dots in the top-right corner, then select **Script Editor**.
- When functions mention they run every week, two weeks, etc., it indicates a time-based trigger set in the Google Apps Script editor.

## **Quick Journey**
*Summary of the Process*

### Student Submissions
- By the end of the pay period, students submit the hours they worked through the [WS Payroll Log Form](https://docs.google.com/forms/d/1_FbkVJR0gg0L0E46f8f_G6xKe-pAX0lKjBb-j_yS07I/edit). The responses are collected in a sheet within the Approval Sheet spreadsheet called `Submissions_Source`. This is not what gets processed.
- Another sheet called `Submissions` imports this data and associates a key with each entry at _Column A_ and _Column J_. The key is structured as: "[student email address] - [PP code]", for example, "alaa@uni.minerva.edu - PP1".
- Before submission day (Thursday), an automatic reminder is sent to students to submit their hours. This reminder is managed by the `contractorsSubmissionReminder` function, which runs every two weeks.

### Managers' Approval
- This data is imported into the first sheet in the spreadsheet, typically named after the pay period it refers to (e.g., PP1 for submissions of PP1). After the submission day (Friday), the Google form is automatically locked using the `restrict` function.
- Managers receive an automated email on Sunday to approve or remove students' hours. This occurs in the same sheet, typically the first sheet. The function for sending manager reminders is `managerApprovalReminder`.

### Shifting Sheets
- Managers approve hours by changing the approval column for their interns to YES or NO. On Tuesday/Wednesday, the sheet for the previous pay period is locked, moved to the end, and a new sheet is created for the current pay period. This is handled by the `copySheet` function.
- For example, if managers approve PP1, that sheet is locked and sent to the end, then a new sheet is created for PP2.

### Students' Return
- On the following Saturday, the form for logging hours is unlocked, allowing students to submit hours for the new pay period. On Thursday, one day before the end of the pay period, a reminder is sent, and the cycle continues.

## **Actions**
*What to update when you arrive?*

1. **Config Sheet:** This sheet in the Approval Sheet is crucial. Ensure it is always up-to-date. Check the Position Tracker of the year or the Master DB for accuracy.
2. **PP Sheet:** Ensure the students' names in the PP sheet (at the beginning of the spreadsheet) are correct, as they are not updated automatically.
3. **YTD Analysis:** Verify that names and emails are accurate.
4. **Submissions_Source:** Ensure this sheet, where hours are submitted, is connected to the correct source. It should pull the most accurate information.
5. **Triggers:** Ensure the triggers on the Approval Sheet are correctly configured. These can be found in the scripts.
6. **Scripts:** Have a look at the get started of the [form scripts](/non_paycom_doc/form_scripts) and [sheet scripts](/non_paycom_doc/sheet_scripts) for a correct set up for the automation, as well.

## **Important Sheets**
*Important spreadsheets, their content, and why they are important:*

1. **Approval Sheet:**
    - The main sheet where students submit hours and managers approve them. Reminders are sent automatically from the scripts of this sheet.
2. **Position Tracker:**
    - Contains all the information about students' positions, personal information, and managers' information.
3. **BDC Payment Summary:**
    - Details payments made to students through [Bill.com](https://Bill.com).
4. **Bank Information Sheet:**
    - Where students submit their bank account information, which is used to set up their account on Bill.com.
5. **W8/9 Folder:**
    - A Google Drive folder in the `Wire` folder where W8/9 forms are collected. Ensure any forms submitted by students are saved in this folder.
