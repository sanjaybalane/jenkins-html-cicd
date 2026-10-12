# Jenkins Deployment Job for a Static Website

A Jenkins freestyle job that pulls a static HTML website from GitHub and deploys it to a local Apache server (XAMPP) on Windows.

## What it does

When the job runs, Jenkins:
1. Pulls the latest code from this repository
2. Copies the files into the XAMPP htdocs folder
3. Serves the updated site at http://localhost/site1/

## Tools

- GitHub
- Jenkins (freestyle job, Git and GitHub plugins)
- XAMPP (Apache)
- Windows batch command

## Setup

1. Create a GitHub repository for the site
2. Install Jenkins with the Git and GitHub plugins
3. Create a Freestyle job and add the repository URL with a credential
4. Add a Windows batch build step:

   xcopy "%WORKSPACE%\*" "C:\xampp\htdocs\site1" /E /I /Y

5. Run the job with **Build Now**

## Repository structure

- index.html
- contacte.html

## Limitations and next steps

- The job is started manually. Adding a GitHub webhook would trigger it on every push.
- It deploys to a local machine. The next step is deploying to a cloud server such as AWS EC2.
