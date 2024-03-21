# Katalon_AWS_Workshop

This repository is for the testing portion of the workshop for AWS by Katalon. You can clone this repository into Katalon to modify and run the tests.

The steps below contain instructions for creating a testing build through AWS Codebuild. The Codebuild project can be added as part of a pipeline, and triggered to run tests automatically on application deployments.

**Prerequisites**:

1. A GitHub Account and a GitHub personal access token (Make sure to store this token somewhere secure, as it will be used in the workshop)
https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens

2. An AWS account to set up AWS Codebuild

3. A Katalon Account - You can sign up for free and have access to a 30 day trial of KSE and KRE
https://login.katalon.com/realms/katalon/login-actions/registration?client_id=katalon-marketing&tab_id=0lzZ5IsqZco

4. Download Katalon Studio
https://katalon.com/download


**Instructions**

**Step 1: Fork this GitHub Repository**
 - https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo
  
**Step 2: Clone the Katalon Studio Project from the Forked Repository**
 - Activate Katalon Studio using your Katalon Account (Select Log in from Browser)
 - Select 'Clone Git Project'
 - Enter the repository URL from the forked repository
 - Authenticate with your email and personal access token (instead of a password), and be sure to check 'Save Authentication'
 - Click 'Next', then 'Next' again, and 'Finish' to complete cloning

**Step 3: Update the Katalon Project and commit the changes**
 - For this workshop, we will walk through using the 'Katalon Recorder' to create a new test case
 - Add the new test case to a test suite
 - On the git icon, click 'commit'
    - Move all items from 'Unstaged Changes' to 'Staged Changes'
    - Write a commit message describing the change
    - Click 'Commit and Push'

**Step 4: Retrieve your Katalon API Key**
 - Login to testops.katalon.io using your Katalon account
 - Navigate to https://testops.katalon.io/user/settings and select 'Katalon API Key' from the left side menu
 - Copy the default key (or create a new key and copy it)
    - The API Key will be used in Step 2 to configure your AWS Codebuild project
 
**Step 5: Go to AWS Codebuild and create a New Project**
 - Give the project a name
 - In the 'Source' section, select "GitHub Repository" as the source
    - Authenticate GitHub with your personal access token (Or OAuth if supported)
    - Choose 'Repository in my GitHub Account' to select your forked repository.
 - In the 'Environment' section, click the 'Additional Configuration' dropdown
    - Click 'Create Parameter'
    - Enter 'KATALON_API_KEY' as the name and provide your API Key which you retrieved earlier as the value and click 'Create Parameter'
    - Enter 'KATALON_API_KEY' in the name column next to the newly created paramter (this is the name of the environment variable)
 - In the 'Buildspec' section, select 'Use a buildspec file' (this file is included and pre-populated in this Git Repository)
 - Click 'Create Build Project'

**Step 6: Grant Permissions**
 - Navigate to https://console.aws.amazon.com/iam/ 
 - On the left side menu, select 'Roles'
 - Select the role associated with your codebuild project name
 - Click on the 'Add Permissions' dropdown and select 'Attach Policies'
 - Search for 'AmazonSSMReadOnlyAccess'
 - Select the checkbox and click 'Add Permissions'

**Step 7: Build your Project**
 - In AWS Codebuild, select your new project in 'Build Projects'
 - Click on 'Start Build' to build your project
 - The tests will execute and you will be able to see the logs
