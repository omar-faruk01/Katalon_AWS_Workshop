# Katalon_AWS_Workshop

This repository is for the testing portion of the workshop for AWS by Katalon. You can clone this repository into Katalon to modify and run the tests.

Prerequisites:

1. A GitHub Account and a GitHub personal access token (Make sure to store this token somewhere secure, as it will be used in the workshop)
https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens

2. An AWS account to set up AWS Codebuild

3. A Katalon Account - You can sign up for free and have access to a 30 day trial of KSE and KRE
https://login.katalon.com/realms/katalon/login-actions/registration?client_id=katalon-marketing&tab_id=0lzZ5IsqZco

4. Download Katalon Studio
https://katalon.com/download


Instructions

Step 1: Retrieve your Katalon API Key
 - Login to testops.katalon.io using your Katalon account
 - Navigate to https://testops.katalon.io/user/settings and select 'Katalon API Key' from the left side menu
 - Copy the default key (or create a new key and copy it)
    - The API Key will be used in Step 2 to configure your AWS Codebuild project
 
Step 2: Go to AWS Codebuild and create a New Project
 - Give the project a name
 - In the 'Source' section, select "GitHub Repository" as the source
    - Authenticate GitHub with your personal access token (Or OAuth if supported)
    - Select "Public Repository" and provide this repository url: https://github.com/giaesposito/Katalon_AWS_Workshop.git
        * Alternatively, you can fork this repository, and choose 'Repository in my GitHub Account' to select your own version if you wish to make            updates.
 - In the 'Environment' section, click the 'Additional Configuration' dropdown
    - Click 'Create Parameter'
    - Enter 'KATALON_API_KEY' as the name and provide your API Key which you retrieved earlier as the value and click 'Create Parameter'
    - Enter 'KATALON_API_KEY' in the name column next to the newly created paramter (this is the name of the environment variable)
 - In the 'Buildspec' section, select 'Use a buildspec file' (this file is included and pre-populated in this Git Repository)
 - Click 'Create Build Project'

Step 3: Grant Permissions
 - Navigate to https://console.aws.amazon.com/iam/ 
 - On the left side menu, select 'Roles'
 - Select the role associated with your codebuild project name
 - Click on the 'Add Permissions' dropdown and select 'Attach Policies'
 - Search for 'AmazonSSMReadOnlyAccess'
 - Select the checkbox and click 'Add Permissions'


