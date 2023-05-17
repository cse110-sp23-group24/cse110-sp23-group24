# Phase 1 CI/CD Pipeline

## Introduction
The goal of this phase is to create a vetting phase of the CI/CD pipeline that ensures code quality and automates the testing and documentation generation process. This is achieved through the use of linting, code quality tools, human review, unit testing, and documentation generation tools.

## Pipeline Overview

The pipeline is built on Github Actions and consists of the following steps:

### Linting and Code Style Enforcement: 

This step checks for code style consistency and formatting issues using ESLint. If there are any issues, the pipeline fails and provides feedback to the developer. <br> 

We chose to use this as Haoyang has experience with it and he recommended it. ESLint is an open source project that helps you find and fix problems with JavaScript code. In addition, it statically analyzes code to quickly find problems, and it is built into text editors and runs ESLint as part of our project’s continuous integration pipeline to find issues. After it finds the issues, it will fix problems automatically most of the time and be syntax-aware, which means we won’t face errors introduced by transitional find-and-repace algorithms. In addition, if we want,  we can customize it. For example, pre-processs code, use custom parsers, and add rules besides ESLint’s built-in rules.The guidelines to use ESList can be found [here](https://eslint.org/docs/latest/). <br>


Installation Instructions: 
- (A) Install Node.js ready and built with SSL support.
- (B) Install ESLint using command `npm init @eslint/config`. Then choose third option “To check syntax, find problems, and enforce code style”.
![Image](install_eslint1.png)
- (C) Configure ESLint using command `npm init @eslint/config -- --config semistandard`
![Image](/admin/cipipeline/install_eslint2.png)
- (D) Run ESLint on any file, such as yourfile.js using command `npx eslint yourfile.js`

Pros of Using ESLint: <br>
a. Rules Are Customizable. <br>
b. Provides Code consistency. <br>
c. Helps in Catching errors. <br>

Cons of Using ESLint: <br>
a. Not Always Correct. <br>
b. Gives False Positives. <br>
c. Doesn’t Fix Unused Variable. <br>

Some useful resources to use ESLint:
- [Why I always use ESLint in my projects](https://youtu.be/ZuDIXV94Z1w)
- [Use ESLint in Your Project](https://eslint.org/docs/latest/use/)
- [ESLint Quickstart - find errors automatically](https://www.youtube.com/watch?v=qhuFviJn-es&ab_channel=freeCodeCamp.org)


### Code Quality Via Tool: 

This step is vital in ensuring good software quality. To avoid repetition, maintain readability of code and have help in pointing out errors, we choose to use CodeClimate. It is a GitHub friendly tool with many advantages. We decided to use this tool as it is free for Open Source. "Code Climate’s flagship product, Velocity, analyzes all the data from your GitHub repos and provides you with heads-up displays, real-time analytics, and custom reports to give you a clearer perspective on how your engineering team is working." ([Link](https://codeclimate.com/company#:~:text=Code%20Climate's%20flagship%20product%2C%20Velocity,your%20engineering%20team%20is%20working.))

Codeclimate can be integrated with Github. [Adding Code Climate to Your Workflow](https://docs.codeclimate.com/docs/workflow)

Pros of Using CodeClimate: <br>
a. Locally Installable API. <br>
b. Helps in Producing Better and Cleaner Code. <br>
c. Auto Sync With Github. <br>

Cons of Using CodeClimate: <br>
a. Is a "Dashboard of Engineering Leadership". ([refer here](https://www.swarmia.com/alternative/code-climate-velocity/?utm_term=codeclimate&utm_campaign=SRH-COMPETITORS-USA-EN&utm_source=adwords&utm_medium=ppc&hsa_acc=6644081770&hsa_cam=16463390797&hsa_grp=134848023835&hsa_ad=616241566270&hsa_src=g&hsa_tgt=kwd-512657187732&hsa_kw=codeclimate&hsa_mt=p&hsa_net=adwords&hsa_ver=3&gclid=CjwKCAjw04yjBhApEiwAJcvNoUQn-K_7qGP7w4ULqvKiw5W3eehyMMmOwsE4cgJoeLr8B-c_713sABoCozMQAvD_BwE))<br>
b. Only focuses on tracking activity of individual developers. <br>
c. CodeClimate offers a wide range of features and settings, which can make it initially challenging for new users to navigate and configure. <br>
