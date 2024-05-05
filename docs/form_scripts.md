## Quick get started
- ***Update the links and sheet ids***

## Introduction

Here will be the details of the code being used. It will be very detailed. Knowledge about JavaScript will be valuable though not necessary. This page has the code for the automation of the `Payroll Log Form`. The explanations are related to handling closure/opening the google form and editing the questions. For the scripts related to the Approval Sheet, go [here](/non_paycom_doc/sheet_scripts)

## Acessing it
- ***You can find the code in the scripts of the form.***

![image.png](https://i.postimg.cc/yxsJwmVP/image.png)

- ***This is what you would see:***

![image.png](https://i.postimg.cc/8z971Qps/image.png)
## Code

- ***For the first 2 lines, this is the set up for the name of the config sheet which has the dates and details about current pay period. This is a sheet in the approval spreadsheet.***


![image.png](https://i.postimg.cc/RF9VFvjC/image.png)

- ***`updateForm` function: This function grabs the current pay period details (PP number, start date, end date, etc...) from the config sheet and update the form.***
![image.png](https://i.postimg.cc/R0142jqk/image.png)

- ***Sample Config Sheet***:

![image.png](https://i.postimg.cc/L8LpZrkJ/image.png)

- ***`restrict` function: This function closes the submission form on the saturday after the submission deadline and reopens it on the saturday of the next week.***

![image.png](https://i.postimg.cc/Kj6WG8HJ/image.png)

## Triggers
These triggers are the schedule where the functions actually run. Navigate to the triggers section on the left and add triggers by the button on the right.

- ***Trigger for `restrict`: This function runs every week. One week it closes the form, while the other week, it reopens the form.***

![image.png](https://i.postimg.cc/BnqrXXvV/image.png)

- ***Trigger for `updateForm`: This function should run every two weeks to update the form with each pay period. However, there is no biweekly triggers and there is no harm from running it every week, so just keep it similar to the `restrict` function.***

![image.png](https://i.postimg.cc/xdBpyC0Y/image.png)