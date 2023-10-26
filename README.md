[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=12516987&assignment_repo_type=AssignmentRepo)
# Tech Test for QA Applications

As part of the hiring process, we ask you to demonstrate some skills with automation by producing a test suite that automates a series of user workflows. You should also include any tests that you believe would be relevant but are not covered below, however focus on the objective of the user story and what it is trying to verify.
Please cover as many user stories as you can, whilst maintaining good readability and reusable codes. It's better you have a functional automated test suite rather than a framework with only 1 or 2 automated tests.

**Requirements:**
  - We request that you use a Python automation framework. Humanforce uses PyTest.
  - Please respond to this assessment with a code package, preferably hosted in a git repository.
  - Automated tests should run in headless mode.
  - Automated tests should be executable by a single command (e.g., pytest --pyargs package_name).

Spend no more than 4 hours on this assessment. It is not intended that you achieve 100% coverage in this time period. We would like to see what you can do in 4 hours' time.

**Note: Account credentials for the tenant will be provided to you separately.**

**Note: You might see introductory popup windows the first time you open up certain pages, these can be closed before running the test.**

Bonus points (if you have capacities to do all of these, you are more than welcome to show us your skills and experience):

- Code is clean and easy to read.
- Language is in Python
- Use Page Object Model style for the project.
- Functions that are repeated are stored in a helper file and referenced as necessary.
- Failed tests are retried a few times before failing.
- Documentation and comments as required.
- Tests can be retried multiple time without failing.
- Password are stored in a separate file (using dot env)

### User Story #1 - Easy ###
```
As an anonymous User
When I visit https://www.humanforce.com/
Then I should see the Humanforce public homepage
Verify Humanforce logo is visible
When I scroll to the bottom and select 'Time & Attendance'
Then I should see Helpful Resources, when I scroll to the bottom.
Then I select '7 benefits of workforce analytics for business'
Then I should see an article about this topic
```
### User Story #2 - Easy ###
```
As a non-logged in user
When I visit <test instance>
Then I should see the login page <test instance>/Account/LogOn?ReturnUrl=%2f
Verify username and password fields are visible
```
### User Story #3 - Medium ###
```
As an authenticated user <Manager user> MNGR01
When I visit <test instance>/Account/LogOn?ReturnUrl=%2f
Then I should see the login page
When I login with the correct credentials
Then I should see the dashboard
Verify the greeting is visible (eg. Hello <name>)

Then I click on 'HF Academy' at the bottom left of the page
Verify that there is a pop up window

Then I type 'Personal' in to the search box
Then I click on 'How do I view or update my details' article
Verify that the engine opens up a new browser tab

Then I close the current tab
Then I navigate back to the Home Page(<test instance>/Home)
Then I log out
```
### User Story #4 - Hard ###
```
As an authenticated user <Admin> ADM01
When I visit <Test instance>/Admin/Area
Then I press 'Add new record' button
Then I enter all of the mandatory data
Then I press 'Save' button
Then I see 1 newly Area listed

Then I create 2 more new Areas by repeating the previous steps
Then I see 3 new Areas listed
Then I click 'Edit' for one of the 3 new Areas
Then I change the Name of the Area and click 'Save'
Then I click 'Delete' for one of the 3 new Areas
Verify out of the 3 Areas created, only the first 2 Areas area listed

Then I click on the 'Undelete button'
Then I click 'Restore' for the Area I deleted previously
Then I click 'Close' to close the popup window
Verify that all 3 newly created Areas are listed
```
### User Story #5 - Very Hard ###
```
Prerequisite: 
Download the provided CSV file and update the FirstName and LastName column with your own

As an authenticated user <Admin> ADM01
When I visit <Test instance>/IntegrationsCentral
Then I click on the 'Add New' button
Then I click on 'File Import'
Then I enter a task name
Then I select the Data type of 'Employee Basic' from the drop-down box
Then I click 'Browse'
Then I select and upload the provided CSV file
Then I click 'Next' at the bottom of the page
Then I click 'Import Only'
Then I should see 'File import complete'

Then I navigate to <Test instance>/EmployeeManagement
Verify there is an employee with my first name and last name
Verify the Employee Code of that employee matches with the EmployeeCode in the provided CSV file
```
### User Story #6 - Easy ###
```
As an unauthenticated user <Employee user> EMP01
When I visit <Test instance>/EmployeeManagement
Then I should see the login page
When I login with the correct credentials
Then I should see 'Sorry, that is not currently allowed...'
Verify that the 'Home' button is visible
Verify clicking 'Home' button will redirect user back to the home page
```
### User Story #7 - Medium ###
```
As an authenticated user <Admin> ADM01
When I click 'View all messages' under the MESSAGES section
Then I should see a chat window
Then I click 'New' button
Then I select an employee from the list on the left
Then I click 'Add' button
Then I type a message into the textbox
Then I click 'Send' button
Verify that the name of the recipient is correct
Verify that the message I sent is visible in the chat box
```
### User Story #8 - Easy ###
```
As an authenticated user <Manager> MNG01
When I navigate to <Test instance>/EmployeeManagement
Then I double click on my own employee profile (same Employee Code used to log in)
Then I should see the popup warning message advising I cannot edit my own profile
Verify that the 'Save' button is not visible
```
### User Story #9 - Medium ###
```
As an authenticated <Manager> MNG01
When I visit <Test instance>/TimesheetApp/modules/timesheetAdmin
Then I Click on 'New' button
Then I select 'Timesheet from defaults'
Then I select my own employee using the radio button
Then I click 'Done' button
Then I click 'Save' button
Verify that a timesheet is now visible on the grid for my employee

Then I click on the 3 dots symbol next to my timesheet
Then I click 'Delete'
Then I refresh the page
Verify that the created timesheet is now no longer visible

Take a screenshot of the result everytime this test is run
```
