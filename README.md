[![codecov](https://codecov.io/gh/DanielDanzo/testing-codecov/graph/badge.svg?token=tl4RAR98sH)](https://codecov.io/gh/DanielDanzo/testing-codecov)
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

Ensure you have your tests for your code. An example of this is the math.js (which is code to be tested) and math.test.js(which is the code that does tests). Ensure your test files are name in this format *.math.js(where * represents your desired name).

### 4. Install and initialization

Firstly we need to initialise node. Do this by running the following command on your terminal.

```bash
npm init -y
```

If you do not have Node installed, head over to [Node website](https://nodejs.org/en) and install Node for your operating system. Next step is to install jest for your project. Use the folleing command to install jest:

```bash
npm install --save-dev jest
```

Jest is a Node module that allows for running tests and generating a code coverage for your project. Run Jest inorder to generate code coverage reports.

```bash
npx jest
```

### 5. Creating dot gihub folder

In your project folder create another folder called ".github". Inside that folder create a new folder called "workflows". This is used to configure or to make actions when committing to your github repo. Inside the workflows folder you should have a *.yml file. An example of this is in this current repo under .github/workflows/ci.yml

