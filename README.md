# Katalon_AWS_Workshop

This repository is for the testing portion of the workshop for AWS by Katalon. You can clone this repository into Katalon to modify and run the tests.

Prerequisites:

1. A GitHub Account and a GitHub personal access token
https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens

2. An AWS account to set up AWS Codebuild

3. A Katalon Account - You can sign up for free and have access to a 30 day trial of KSE and KRE
https://login.katalon.com/realms/katalon/login-actions/registration?client_id=katalon-marketing&tab_id=0lzZ5IsqZco

4. Download Katalon Studio
https://katalon.com/download


Instructions

Step 2: Go to AWS Codebuild and create a New Project
 - Give the project a name
 - Select "GitHub Repository" as the source
 - Authenticate GitHub with your personal access token (Or OAuth if supported)
 - Select "Public Repository" and provide this repository url: https://github.com/giaesposito/Katalon_AWS_Workshop.git
 - In the buildspec section, select 'Use a buildspec file'


