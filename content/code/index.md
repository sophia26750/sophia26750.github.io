---
layout:     posts
title:      "The Coding Behind the Scenes"
subtitle:   "How I coded this website and published it."
date:       2024-12-31
author:     "Sophia"
image:      "coding_bg.jpg"
---

### A Light Introduction

---

When I began creating this website, I ran into numerous issues with Hugo and  GitHub. There were many folders, commits, and templates that did not deliver the results it promised. As a result, I created this page to hopefully help the public with how I commited this code. 

---
---

# Start

1. Install Hugo:
``` 
brew install hugo
```

2. Find a desired template for use on [Hugo themes](https://themes.gohugo.io/) (I used the [hugo-theme-cleanwhite](https://github.com/zhaohuabing/hugo-theme-cleanwhite) for this website). 
3. In the desired template, press the download button. This will bring you to the GitHub page. 
4. Scroll down to read the instructions provided in the README. 

_For this next step, most Hugo Themes require these steps but may differ from theme to theme._ 

5. 
 ```
    $ mkdir test
    $ cd test 
    $ mkdir themes
    $ cd themes
```
The following code was inputted into terminal _strictly_ for this theme. Only follow if you wish to use this theme. 
```
    $ git clone https://github.com/zhaohuabing/hugo-theme-cleanwhite.git
    $ cp -r hugo-theme-cleanwhite/exampleSite/** ../
    $ cd .. 
    $ hugo serve
```
For this theme, the original programmer allowed a template for reference. Input this into terminal (make sure you are in themes folder):
```
$ git clone https://github.com/gurusabarish/hugo-profile.git
```

---
---

# GitHub

### Creating Repository

For the following, this is how to set up your website for deployment. 

1. Create a new repository using Github.
![Screenshot](/screenshot_1.jpg)  

2. Add a repository name in this format: "any-name-you-want.github.io" 

3. Check yes for "Public" and "Add a README file"

4. Press create repository. 

5. Drag the themes folder into the new created repository (it should be a folder with your repository name) using finder for MacOS.

6. Use terminal to cd into the repository folder. Click on branches

### Branches

From here, we should create a new branch to prevent error in the main deployment of your website's project.

7. Open terminal and make sure you are in your repository folder. 

8. Type this into terminal: 
```
git checkout -b "name of branch you want."
```
This created a new branch, and you should be able to see this branch on github

9. Go to your Github account and open your repository, and press on branches. You should see your new created branchname on top. 
![Screenshot](/screenshot_2.jpg) 

10. If you are using Visual Studios, make sure you are in the repository folder and input into terminal :
```
code .
``` 
11. Now check if you are in your branch by checking the bottom left corner. If you do not see this, close Visual Studios and reopen it with code . 
![Screenshot](/screenshot_4.jpg) 

At this point, a branch has been created. Run your website locally by inputting this into terminal:
```
hugo serve 
```
_This will run a local server of your website._ This means the Github pages link does not work yet. For the safest option, running the program locally allows you to see direct changes without the public seeing possible errors. 

12. You will see a link that looks something like: http://localhost:1313. Copy that link and paste it in your search bar. This will run a local server of your website that displays your live changes. If you wish to end this, just press Crtl + c. If you wish to bring it back, just input hugo serve into terminal to start the local server again. 

---
---

# Website Making 

Most websites will be using markdown as its main language for coding. Click here for a YouTube video that helps with hugo and markdown programming ==> [YouTube Video (0:00 - 37:14)](https://www.youtube.com/watch?v=hjD9jTi_DQ4). 

When you are working and changing your website, it is always important to continously commit the current code to your branch in case of huge errors because you could restore your code back to your last change. Think of this process like _creating checkpoints_ throughout your code. If your code were to blow up, you can access your branches and restore the version before the blowup. The more commits you make, the safer your chances are of restoring if accidents were to happen. 

### Commit code to branch

To commit your code into your branch for a safe checkpoint, do the following steps.  

1. If your website it running locally with Hugo Serve, make sure to end it with crtl + c

2. Enter the following code line by line into terminal:
```
git status
git add .
git commit -m "Add a good note of the changes you did in the quotes. You can will see these on Github later."
git push origin branchName
```
What these commands do:

| Git command | Action | 
|----------|----------|
| git status | Is a command used in Git, which is a version control system that helps manage code changes and project history. It shows you the current state of your working directory and staging area. |
| git add . | When you run this command, it stages all the modified, newly created, and deleted files in the directory for the next commit. The "." adds all the changes in the current directory and its subdirectories to the staging area. | 
| git commit -m "Type good message" | Creates a new commit with a message that describes the changes you've made. | 
| git push origin yourBranchName | Pushes your local branch to the remote repository. | 


### Restore code using last commit
_Oh no!_ Let's say you made a mistake and now your code refuses to cooperate. Follow the steps provided below to go back to your last commit (aka your last checkpoint). 

1. Go here (for visual studios)
![Screenshot](/screenshot_14.jpg)

2. You can view the changes you made here. To discard previous changes, press this:
![Screenshot](/screenshot_15.jpg)


---
---

# Setting up deployment of your website

In this portion, this will allow you to publish your website using Github pages. 
***There are many ways one could do this, but this is the easiest way I did:*** 


### Create github Actions 

1. Make sure you are still in your repository and your branch. 
 
2. In Visual Studios, add a folder and name it .github
![Screenshot](/screenshot_5.jpg) 

3. Create a folder in .github and name it workflows

4. In workflows, create a new file named hugo.yml
![Screenshot](/screenshot_6.jpg) 

This folder and file is known as github Actions. This helps deploy code to Github pages everytime the repository link is open. 

Right now, the changes made are stored in the branch. In order allow main to see the changes made and publish it on a website, the code needs to be converted into HTML or Javascript. This conversion is knows as minify. 

To allow your code to automatically minify, follow the following steps. 

5. Set up github Actions for deploying code to GitHub pages by copying and pasting the following code into your [hugo.yml](../../.github/workflows/hugo.yml) file (click the hugo.yml for the code required).

6. Go to Settings and go to Pages  
![Screenshot](/screenshot_10.jpg) 
![Screenshot](/screenshot_11.jpg) 

7. Change the source from deploying from branch to Github actions. 
![Screenshot](/screenshot_12.jpg) 

This allows you to open your website and see the changes you have made. This also allows you to minify all files you have for your hugo website without you needing to make it yourself. 

If a new branch is needed in future, this allows you to run the website locally to see changes. _BUT_ when the branch is merged with main, it does not require you to minify all files; it will automatically do it.

### Commit branch to main 

8. Commit your branch into main.
    1. go to your repository in Github
    2. Press Pull requests 
    ![Screenshot](/screenshot_7.jpg)   
    3. Press Create pull request __OR__ if Github shows your branch with the button "Compare &pull request" press that and skip step 4 and 5. 
    ![Screenshot](/screenshot_8.jpg)
    ![Screenshot](/screenshot_16.jpg)
    4. change compare:main to your branch that you want to commit
    ![Screenshot](/screenshot_9.jpg) 
    5. Press Create pull request.
    6. This will bring you to textbox. Write a summary of all the changes you did in this branch. Then press Create pull request.  
    ![Screenshot](/screenshot_17.jpg)  
    7. You will need to scroll down until you see the Merge pull request button. Press it. 
    ![Screenshot](/screenshot_18.jpg)
    8. Press Confirm merge. 
    ![Screenshot](/screenshot_19.jpg)
    9. There will be an option to delete previous branch. Make sure you do.
    ![Screenshot](/screenshot_21.jpg) 

The following steps are for seeing the website and seeing Github's process of deploying your website. 

9. Go to Github actions. You can see the process of Github moving from build to deployment. Once the deployment is done, there will be a link of your website under "deploy". Press it and you can see your website. 
 ![Screenshot](/screenshot_20.jpg) 

 ### Add new changes to website AFTER deleting branch

10. If you want to create more changes, make sure you make a new branch. _IT IS THE SAFEST OPTION TO CREATE A NEW BRANCH IF YOU WANT TO ADD TO YOUR WEBSITE_. Follow these steps:

    1. Because you deleted the branch in Github, your local computor is NOT aware of this change. To update your local status, bring up terminal and input these lines:
    ```
    git checkout main
    git pull
    ``` 
    2. Now create a new branch with: 
    ```
    git checkout -b nameOfNewBranch
    ```
    3. Go back to step 11 in Branches to double check your Visual Studios is working. 

<!-- 9. To see your website go to the link at the top where it says **"Your site is live at"**
![Screenshot](/screenshot_13.jpg)  -->

