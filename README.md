# ![InSee logo](Readme-assets/InSee-Logo.png)InSee

An application for code linting and reviewing with fully customizable rules for every ServiceNow developer/reviewer.

## Install Notes:

* Download the update sets from https://github.com/SNDevTools/InSee/tree/master/Dist and install on your instance.
* Pre-requisites: 
     1. Need to have a MID Server configured to your instance. 
     2. PHP (https://www.mamp.info) 
     3. Installing ESLint (http://eslint.org) commands and installed globally and running on the machine where the MID Server is configured.
          1. *Windows*
               1. run the command  *>npm install eslint --save-dev* from agent folder.
               2. add *"<Agent folder>/node_modules/.bin"* to the environment variable *"PATH"*
          2. *Linux*
               1. run the command *>npm install -g eslint*
* Setup the application on MID Server by following the below steps:
     1. System Administrator needs to change the scope to "Automated Code Review". 
     2. Go to Navigator -> Automated Code Review -> Setup
     3. Provide the name of the MID Server used for code reviewing along with the integration user credentials. 
     Note: Integration user needs to have admin role.
     4. Change the "Code Sync Status" from "Not Initialized" to "Intialized" and
     5. Click on Save. Wait for couple of minutes and refresh the page to see if the status changed to "Completed".
     
     
 ![Setup Process](Readme-assets/Setup-process.png)
 
## About:

*InSee* is designed for developers to comply with the best practices recommended by the ServiceNow platform along with the customizable rule development capability for adding new rules specific to your team or company coding standands and practices.

*Every developer* can do the code reviewing on a single entity (Script Include, Business Rule, UI Script, Client Script etc) or on the updateSet to fix the non-compliant practices then and there. 

*Every reviewer* can do the code reviewing on multiple updateSets and the developer will have the visibility of the review validation results simultaneously to act upon in brining the highest quality of code quickly.

## Developer Persona:

1. Developers will be able to see an UI action *"Code Review"* on form view of tables that extend from sys_metadaa. for the initial release 1.0, this UI action is available on Business Rules, Client Scripts and Script Includes.
2. Upon clicking this UI action, the file contents will be synced on to mid server and thus gets validated by ESlint rules and the review results are populated under *review resulsts* related list.

-- following are some quick snapshots to viz this UI action in action.

## Reviewer Persona:

Reviewer can review code at 2 levels
  1. story
  2. update set
  
  Reviewer will be able to see application Automated code review and Review Request module. Upon navigating to this menu, Reviewer can create a new record with a story number, owner and other story related information. Also reviewer selects the update sets that contains the changes for the mentioned story and then Reviewer clicks on the Code Review UI action.
  
  Alternatively, Reviewer can also do the same UI action directly on an update set level.
  
  In both cases, review results will be populated under *"review results"* related list in story/update set respectively.

## Rules Administrator Persona:

Rule Administrator has access to Automated code review application with the all the following navigations.

1. Code Review Rules
2. Review Requests
3. Review Results
4. Configuration
     1. setup
     2. Eslint Globals
     3. ACR Sources

## License:

MIT
