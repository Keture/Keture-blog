---
title: Hosting Web page on Firebase
date: '2023-05-07'
tags: ['DEPLOY', 'CI/CD', 'GITHUB-ACTIONS']
draft: false
summary: CommonJS vs ECMAScript Modules
authors: ['miththiran']
---

## Hello Folks!

If you're feeling unsure about how to host your webpage on a hosting site and are seeking solutions, you've come to the right place. This article will provide you with the knowledge you need to successfully host your webpage on Firebase. It will cover both **MANUAL** hosting and hosting through the **CI/CD** method.

To clarify, this article will focus primarily on hosting a webpage on Firebase, providing you with step-by-step instructions to ensure that you can do so with ease. Whether you choose to host manually or through the CI/CD method, this article will provide you with the necessary information to help you make an informed decision. Lets dive in to the article.

## Creating Firebse Account and Set up a Firebase project.

To create a Firebase account, you'll need to open your web browser and search for Firebase. You can also click on this link: https://firebase.google.com/ to access the Firebase website directly. Once you're on the website, you can proceed with creating your account.

After creating your account, the next step is to create a project space on Firebase where you can deploy your React app. To do this, sign in to your account and click on the **"Go to console"** option located in the top right corner of the page. Once you click on this button, you'll be taken to the project creation page.

![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/Firebase01.png)

On the project creation page, you'll find a **"Create project"** option that you need to click. This will take you through a simple three-step process that you can easily complete on your own. Once you've finished all three steps, click on the **"Create project"** button. Don't worry too much about the steps; they're straightforward and easy to follow. After few seconds you can see this page:

![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/Firebase02.png)

## Create-React-App.

Before proceeding with deploying your React app using Firebase Hosting, it's important to have a React app in place. For this tutorial, we'll use Create React App to create a new React app. To create your app, simply run the following command:

```
npx create-react-app firebase-hosting-demo
```

This command will set up a new React app for you with the name **"firebase-hosting-demo"**.

## Install Firebase tool on your local System.

The next step is to install Firebase tools which are necessary for deploying your app. To install these tools, run the following command:

```
npm install firebase-tools -g
```

This command will install the Firebase tools **globally** on your system.

## Login to Firebase

Next, you'll need to log in to Firebase through your terminal. If you're not already logged in, you'll be prompted to enter your email and password. It's important to ensure that you're inside the root directory of your React app before running this command. In my case, the root directory is located at ~/firebase-hosting-demo. To log in to Firebase, simply run the following command:

```
firebase login
```

This command will log you in to Firebase and allow you to proceed with deploying your app.

## Initialize Firebase in Your React App

Great! Now that you're logged in, you'll need to initialize Firebase within your React app. To do this, run the following command:

```
firebase init
```

This command will prompt you with a series of questions and configuration options that we'll walk through together.
The first qestion look like this:
![Image description](<https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase03%20(2).png>)

if you ready for action then press 'y' and then press enter.

After that, The command will prompt you with some qestions. in that questions you have to select **"Hosting: Configure files for Firebase Hosting and (optionally) set up GitHub Action deploys"**
![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase04.png)

After selecting that option you'll be presented with a set of options in your terminal. From these options, you'll need to select **"Use an existing project"** since we've already created a project in Firebase console.
![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase05.png)

That's right. After selecting "Use an existing project", Firebase will show you a list of your available projects. In this scenario, you'll want to select the "firebase-hosting-demo" project. Once you've selected your project, you'll be presented with a series of questions that look like this:
![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase06.png)

You'll need to specify the folder where Firebase will look for assets to deploy. By default, Create React App generates a build folder that contains the production assets. Unless you've modified the default configuration, you should enter **"build"** for this option.

You'll also be prompted to indicate whether Firebase should be configured as a single-page app. For this option, you should enter **"y" (Yes)**.

If you haven't yet created a build for your app, you won't be prompted with the final option of whether Firebase should overwrite your existing build/index.html file. However, if you have created a build, you'll want to enter **"N" (No)** for this option to avoid accidentally overwriting your file.

You'll also be asked whether you want to set up automatic builds and deploys with GitHub. In this scenario, you should select **"No"** since you'll be deploying manually first.
![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase07.png)

## Auto-Generated Configuration Files

Once you have completed the initialization, two new files will be generated - `.firebaserc` and `firebase.json`. It's important to save and commit these files to your git repo since they contain your Firebase hosting configuration. You can ignore the .firebase directory for now.

Your `.firebaserc` file should look similar to the following:
![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase08.png)

The `firebase.json` file should look exactly like the following:
![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase09.png)

## Deploying Your App

Before deploying your React app on Firebase, it is recommended to run the command `npm run build`. Although you can also use `npm run start`, running `npm run build` will optimize your code, resulting in a more efficient page render.

Now that you've completed all the necessary steps, you're ready to deploy your app. Simply run the command

```
firebase deploy
```

and Firebase will provide you with a unique URL where your deployed app can be accessed. This URL will be secured with https, which is another benefit of Firebase hosting. With the quick and easy deployment process, you're all set to enjoy the benefits of Firebase hosting.

## Firebase hosting through the **CI/CD** method.

Before we delve into this topic, let's briefly discuss **Continuous Integration** and **Continuous Deployment** (CI/CD).

## What is **CI/CD**? and How it's work?

CI/CD, or Continuous Integration and Continuous Deployment, is a software development practice that automates the process of building, testing, and deploying applications. It enables frequent and reliable releases, enhances collaboration, reduces risks, and ensures faster time-to-market by automating the delivery pipeline.

CI/CD works by automating the software development lifecycle. It involves integrating code changes into a shared repository, followed by automated builds, tests, and deployments. Continuous Integration ensures that code changes are regularly merged and validated. Continuous Deployment automates the release process, allowing for frequent and reliable deployments to production environments.

Here are some example of CI/CD tools:
![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase10.png)

## How to setup CI/CD for Firebase hosting.

In this session, I'm using GitHub Actions as the CI/CD tool. Now, let's dive into the article on setting up GitHub Actions for Firebase Hosting. We will explore the potential challenges that may arise during the setup and discuss effective solutions to overcome them.

The first step is to create a repository on GitHub, and then we need to push and commit our entire project to that repository. In this case, let's create a repository named "Hosting-on-firebase." Once we finish pushing and committing, we can proceed to clone this repository locally. Although it's ideal to do this at an early stage, in this case, we have already created the project before setting up the GitHub repository. After cloning the repository, we can open the project in our preferred code editor. In this case, I will be using Microsoft Visual Studio Code.

After this process, we need to initialize the Firebase tool in our root directory using the terminal. After that, we can follow the procedure outlined below to set up GitHub Actions for Firebase Hosting.

Here we use

```
firebase init
```

command for initiate firebase tools

After tool is initated we can press **Y** and continue our progress.

After that, The command will prompt you with some qestions. in that questions you have to select "Hosting: Configure files for Firebase Hosting and (optionally) set up GitHub Action deploys". Then, we proceed by following the instructions as mentioned previously, with a slight modification in the process.

In the previous **Manual** process, we selected "No" for the question "Set up automatic builds and deploys with GitHub?" However, this time we want to utilize GitHub Actions, so we will choose **"Yes"** (**refer to the 7th photo**) to enable automatic builds and deploys.

After selecting "Yes" for the question "Set up automatic builds and deploys with GitHub?" the following section will appear:

![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase11.png)

In this section, we need to provide our GitHub username and the repository where we have set up GitHub Actions. As shown in the instructions, we should write it in the following format: "username/hosting-on-firebase" (replace "username" with your actual GitHub username and "hosting-on-firebase" with the name of your repository).

After providing the answer to the previous question, several questions will be prompted in our terminal. We need to answer these questions accordingly, this photo:
![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase12.png)

After completing all the instructions mentioned above, we will notice a new folder named **"github"** appearing in our project folder. Inside this folder, two .yml files will be present: **"firebase-hosting-merge.yml"** and **"firebase-hosting-pull-request.yml"**. These files will be structured as per the requirements outlined in the instructions.

firebase-hosting-pull-request.yml:
![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase13.png)

firebase-hosting-merge.yml:
![Image description](https://ipsacfwdrqizntxwwbkg.supabase.co/storage/v1/object/public/Article%20Imgs/firebase14.png)

These steps conclude the setup of GitHub Actions for Firebase hosting. Once completed, we can carry out our daily work on the project, make changes, save them, and push and commit them to the GitHub repository. When we push these changes to the repository, GitHub Actions will automatically handle the deployment process to Firebase for us. However, it's important to note that certain faults or issues may arise during this process. Let's now discuss some potential challenges and how to address them.

## What problems may occour during this progress? and How we solve them?
