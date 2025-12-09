# Jenkins CI/CD for HTML Website

This project is a small CI/CD setup I made to understand how Jenkins works.

I created a simple HTML website and uploaded the code to GitHub. Then I installed Jenkins on my Windows machine and connected it to the GitHub repo.

## What this project does
Whenever I update my HTML files on GitHub, Jenkins automatically:
1. Pulls the latest code from the repo
2. Copies it into the XAMPP htdocs folder
3. Updates the website on http://localhost/site1/

So the site gets deployed without me doing it manually.

## Tools I used
- GitHub
- Jenkins (freestyle job)
- XAMPP (Apache server)
- Windows batch commands for deployment

## How I set it up
1. Made a new GitHub repo for the website
2. Installed Jenkins and added Git + GitHub plugin
3. Created a Freestyle Job in Jenkins
4. Added my GitHub repo link and personal access token
5. Added a build step with this command:

xcopy "%WORKSPACE%\*" "C:\xampp\htdocs\site1" /E /I /Y

6. After saving, I clicked Build Now and the website deployed.

## What I learned
- Basic idea of CI/CD
- How Jenkins pulls code from GitHub
- Automating deployments
- Connecting Jenkins with Apache (XAMPP)

## Folder structure
site1/
  - index.html
  -  contact.html

## Future improvements
- Add GitHub webhooks for automatic trigger
