[![codecov](https://codecov.io/gh/DanielDanzo/Integrating-Codecov/graph/badge.svg?token=tl4RAR98sH)](https://codecov.io/gh/DanielDanzo/Integrating-Codecov)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/7ab7a87467f44a198115a8b7299cf5b9)](https://app.codacy.com/gh/DanielDanzo/testing-codecov/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)
# How to add codecov to your github repo- Javascript

This is a guide to help begininers about using codecov to show coverage. This guide will help beginners test and and show coverage for their projects.

## Prerequisites

Before we begin ensure you have the following:

- A codecov account
- npm should be installed
- Jest
- vs code

## Step-by-Step Guide

### 1. Setting up codecov account

Head over to codecov and create an [account](https://about.codecov.io/) . Create your account(make sure you login using github). Select the repo to which your want to display code-coverage. 

### 2. Adding codecov_token as secrets in github

Displayed on the dashboard is your codecov token. Copy the token. Head over to your github project. Head over to settings->secrets and variables->actions. Click on the add repository secret. For this tutorial name the secret "CODECOV_TOKEN" and as the value paste your codecov token.

### 3. Tests and test coverage

Ensure you have your tests for your code. An example of this is the math.js (which is code to be tested) and math.test.js(which is the code that does tests), which can be found on this repo. Ensure your test files are named in this format *.math.js(where * represents your desired name) and that your .js file and .math.js file are in the same folder.

### 4. Install and initialization

Firstly we need to initialise node. Do this by running the following command on your terminal.

```bash
npm init -y
```

If you do not have Node installed, head over to [Node website](https://nodejs.org/en) and install Node for your operating system. Then run the command. Next step is to install jest for your project. Use the following command to install jest:

```bash
npm install --save-dev jest
```

Jest is a Node module that allows for running tests and generating a code coverage for your project. Run Jest inorder to generate code coverage reports.

```bash
npx jest
```

As you might have noticed, after running this command, you should have a coverage folder. This folder is generated by jest, which has your code coverage.

### 5. Creating dot github folder

In your project root folder create another folder called ".github". Inside this folder create a new folder called "workflows". This is used to configure or to make actions when committing to your github repo. Inside the workflows folder you should have a *.yml file. An example of this is in this current repo under .github/workflows/ci.yml. 

#### Alternatively

You can copy this code into your *.yml file

```yaml
name: Workflow for Codecov example-javascript
on: [push, pull_request]
jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Upload coverage to Codecov
        uses: codecov/codecov-action@v4
        env:
          CODECOV_TOKEN: ${{ secrets.CODECOV_TOKEN }}
```

Which enables uploading of the reports generated by Jest to codecov. Meaning on a push or pull request it should checkout of your branch, then upload coverage to codecov.

### 6. Commit your changes to Github

Commit all your changes. Once Github Actions is done, head over to codecov to your repo and your coverage will be displayed on your repo dashboard.

### 7. Adding codecov badge to Github

Once all is done. Head over to codecov to the repo you are working on. Go to settings-> Badges and Graphs , copy the markdown code. Go to your Github README.md file in you github repo. Paste the code there. Once succeffully commited, your codecov badge will be displayed on your repo.


## Basics

In this tutorial you test your code locally, and Generate your test coverages. Upload those coverages to codecov which will show code coverage. In every test case that we implement, ensure you run the test command to generate new code coverage reports that will be uploaded to codecov. In most codecov documentations, the reports are generated on github, where the npx jest is ran in Github. But the offset to this is that you need to grant access to run the command. 
