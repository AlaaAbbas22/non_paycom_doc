## **Welcome to the Payroll System For Non-Paycom students!**

This is the documentation for automation of the different sheets regarding Bill.com. It is designed to help you navigate, understand, pull information, make updates, or get started at the beginning of each year.

The main sheet is here: [Approval Sheet of 2023/2024](https://docs.google.com/spreadsheets/d/1h--NTEjqyUzLndCXJbNB5af5pqv4vK5-beLuPCsWYnE/edit).

To get started, you'll need the sheet from last year. Instead of building everything from scratch, we clone the sheet of the previous year, along with the automation scripts, and then update the necessary details.



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

<br/>

## **The Logic**
***Important video to complement this documentation (Thanks, Alfonso!)***

<iframe width="560" height="315"
src="https://www.youtube.com/embed/rVOnnysEqlI" 
frameborder="0" 
allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen></iframe>
<br/>

***For Development Team:***
## **Project layout**

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        getting_started.md # getting started
        form_scripts.md # code for the form automation
        sheet_scripts.md # code for the sheet automation
        about.md # About