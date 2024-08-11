# Introduction

Here will be the details of the code being used. It will be very detailed. Knowledge about JavaScript will be valuable though not necessary. This page has the code for the automation of the `Approval Sheet`. The explanations are related to Handling Students submissions, managers approval, and maintaing the sheet of pay periods. For the scripts related to the google form, go [here](/non_paycom_doc/form_scripts)

# Accessing It

- ***You can find the code in the scripts of the form.***

![alt text](image-14.png)

- ***This is what you would see:***

![alt text](image-13.png)


# Code
## Email Reminders
- ***Definition of variables: defining the doc ids that have the format for the reminders to be sent to the students and managers. You might not need to update these ids but make sure to update the links in the documents.***
- [Manager reminder doc](https://docs.google.com/document/d/1So9TL5JizGiL-8zzU8Pe5gdbjslG1gZh4MenBzwJVm4/edit)
- [Student reminder doc](https://docs.google.com/document/d/1wXBCgmtA15TbfYAOtPEzg7kMDATl0y_2LNowIlq1IEM/edit)
- `listOfCCedAdmins` is a list of emails that will be cced in the reminder emails. 
![alt text](image.png)

- ***`onlyUnique`: This is a helper function for filtering unique values. We use it to prevent sending multiple reminders to the same manager who has multiple interns in the sheet.***
![alt text](image-1.png)

- ***`getGoogleDocumentAsHTML`: This is a helper function for getting the reminder content from the docs referenced above.***
![alt text](image-2.png)

- ***`sendBulkEmails`: A helper function for sending emails to multiple students or managers.***
![alt text](image-3.png)

- ***`managerApprovalReminder`: A helper function for sending emails to multiple students or managers.***
![alt text](image-4.png)


- ***`contractorsSubmissionReminder`: A helper function for sending emails to multiple students or managers.***
![alt text](image-6.png)

## Sheet
- ***Defining variables: The most important thing is to keep the position tracker url up to date.***
![alt text](image-7.png)

- ***`absoluteEditors`: These are the editors who will have edit access to previous pay periods' sheets. Changes are reflected in the future and are not retrospective.***
![alt text](image-8.png)

- ***`getSheetName`: Used to get the name of the sheet of the current pay period (the one just ending).***
![alt text](image-9.png)


- ***`getHardCopy`: Copying the actual values as a hard copy instead of copying sheets with formulas.***
![alt text](image-10.png)

- ***`putHardCopy`: Saving the copied sheet into a new sheet.***
![alt text](image-11.png)

- ***`sortByManagerName`: Sorting the sheet of the pay period by the managers names.***
![alt text](image-12.png)



# Triggers

These triggers define the schedule on which the functions run. Navigate to the triggers section on the left and add triggers using the blue button on the bottom right.