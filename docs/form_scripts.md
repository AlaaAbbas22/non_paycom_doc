## Quick Get Started

- ***Update the links and sheet IDs***

## Introduction

This section provides details about the code used for automating the `Payroll Log Form`. It will be very detailed, and while knowledge about JavaScript is helpful, it's not required. The explanations focus on handling the closure/opening of the Google Form and editing the questions. For scripts related to the Approval Sheet, check [here](/non_paycom_doc/sheet_scripts).

## Accessing It

- ***You can find the code in the scripts of the form.***

![Code Access](https://i.postimg.cc/yxsJwmVP/image.png)

- ***This is what you would see:***

![Code View](https://i.postimg.cc/8z971Qps/image.png)

## Code

- ***First 2 lines: These lines set up the name of the config sheet, which contains the dates and details about the current pay period. This is a sheet in the approval spreadsheet.***

![Config Setup](https://i.postimg.cc/RF9VFvjC/image.png)

- ***`updateForm` function: This function retrieves the current pay period details (PP number, start date, end date, etc.) from the config sheet and updates the form.***

![updateForm Function](https://i.postimg.cc/R0142jqk/image.png)

- ***Sample Config Sheet:***

![Sample Config Sheet](https://i.postimg.cc/L8LpZrkJ/image.png)

- ***`restrict` function: This function closes the submission form on the Saturday after the submission deadline and reopens it on the Saturday of the next week.***

![restrict Function](https://i.postimg.cc/Kj6WG8HJ/image.png)

## Triggers

These triggers define the schedule on which the functions run. Navigate to the triggers section on the left and add triggers using the blue button on the bottom right.

- ***Trigger for `restrict`: This function runs every week, alternating between closing the form one week and reopening it the next.***

![Trigger for restrict](https://i.postimg.cc/BnqrXXvV/image.png)

- ***Trigger for `updateForm`: This function is intended to run every two weeks to update the form with each pay period. However, there is no biweekly trigger, and it does no harm to run it every week, so you can set it to run weekly like the `restrict` function.***

![Trigger for updateForm](https://i.postimg.cc/xdBpyC0Y/image.png)
