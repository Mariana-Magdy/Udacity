# Udagram Pipeline Description

Udagram pipeline steps:
1. Installing the environment requirements (Node.js, AWS CLI, EB CLI, and browser tool).
2. List the required jobs.
3. First Job: Build Job
   - Select the required docker image.
   - Install the required node version.
   - Checkout code (clone code from GitHub repository).
   - Install browser tool for running front end unit tests (running mocha in a CI)
   - Install Front-End dependencies `npm install -f`
   - Install backend API dependencies `npm install`
   - Lint Front-End `npm run lint`
   - Build Front-End `npm run build`
   - Run Front-End Unit Test `npm run test`
   - Build backend API `npm run build`
4. Second Job: Deploy Job
   - Select The required docker image
   - Install the required node version
   - Setup EB (AWS Elastic Beanstalk CLI)
   - Setup AWS CLI
   - Checkout code (clone code from GitHub repository).
   - Deploy Backend
   - Deploy Front-End
5. Workflow Steps
   - Run Build Job first
   - Hold in case of master branch only for approval and this required the build action to be done successfully.
   - Deploy and this required hold action to be done successfully by approve the deploy manually.