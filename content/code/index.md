---
layout:     posts
title:      "The Coding Behind the Scenes"
subtitle:   "How I coded this website and published it."
date:       2024-12-31
author:     "Sophia"
# image:      "https://img.zhaohuabing.com/post-bg-2015.jpg"
---

### A Light Introduction

---

When I began creating this website, I ran into numerous issues with Hugo and  GitHub. There were many folders, commits, and templates that did not deliver the results it promised. As a result, I created this page to hopefully help the public with how I commited this code. 

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

# GitHub
For the following, this is how to set up your website for deployment. 

1. Create a new repository using Github.
![Screenshot](/screenshot_1.jpg)  

2. Add a repository name in this format: "any-name-you-want.github.io" 

3. Check yes for "Public" and "Add a README file"

4. Press create repository. 

5. Drag the themes folder into the new created repository (it should be a folder with your repository name) using finder for MacOS.

6. Use terminal to cd into the repository folder. Click on branches 

From here, we should create a new branch to prevent error in the main deployment of your website's project. 

7. Go to your Github account and open your repository, and press on branches.
![Screenshot](/screenshot_2.jpg) 

8. Then press on new branch in the top right corner. Name this branch and press create new branch! 
![Screenshot](/screenshot_3.jpg) 

You have now created a new branch on _Github_. However, your _local comupter_ is not aware of this new branch, and you are still working on main. 

9. To transition into the new branch, input each line one by one into terminal (make sure you are still in your repository folder). 
```
$ git checkout main 
$ git pull 
$ git checkout -b "name of branch you want"
```
10. If you are using Visual Studios, make sure you are in the repository folder and input into terminal :
```
code .
``` 
11. Now check if you are in your branch by checking the bottom left corner. 
![Screenshot](/screenshot_4.jpg) 

At this point, a branch has been created. Run your website locally by inputting this into terminal:
```
hugo serve 
```
_This will run a local server of your website._ This means the Github pages link doe snot work yet. For the safest option, running the program locally allows you to see direct changes without the public seeing possible errors. 

---
# Website Making 

When you are working and changing your website, it is always important to continously commit the current code to your branch in case of huge errors because you could restore your code back to your last change. If your code were to blow up, you can access your branches and restore the versin before blowup. The more commits you make, the safer your chances are of restoring if accidents were to happen. 

1. If your website it running with Hugo Serve, make sure to end it with crtl + c
2. Enter the following code:
```
git status
git add .
git  
```


---

# Setting up deployment of your website
### In this portion, this will allow you to publish your website using Github pages. 
#### _There are many ways one could do this, but this is the easiest way I did:_ 

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

6. Commit your branch into main .
    1. go to your repository in Github
    2. Press Pull requests 
    ![Screenshot](/screenshot_7.jpg)   
    3. Press Create pull request
    ![Screenshot](/screenshot_8.jpg)
    4. change compare:main to your branch that you want to commit
    ![Screenshot](/screenshot_9.jpg) 
    5. Press Create pull request. 
    6. There will be an option to delete previous branch. Make sure you do. 

The following steps are for seeing the website:

7. Go to Settings and go to Pages  
![Screenshot](/screenshot_10.jpg) 
![Screenshot](/screenshot_11.jpg) 

8. Change the source from deploying from branch to Github actions. 
![Screenshot](/screenshot_12.jpg) 

This allows you to open your website and see the changes you have made. This also allows you to minify all files you have for your hugo website without you needing to make it yourself. 

If a new branch is needed in future, this allows you to run the website locally to see changes. _BUT_ when the branch is merged with main, it does not require you to minify all files; it will automatically do it.  

9. To see your website go to the link at the top where it says **"Your site is live at"**
![Screenshot](/screenshot_13.jpg) 

