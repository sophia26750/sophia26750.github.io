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
[Screenshot](/screenshot_2.jpg) 

8. Then press on new branch in the top right corner. Name this branch and press create new branch! 
[Screenshot](/screenshot_3.jpg) 

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
[Screenshot](/screenshot_4.jpg) 


In this part of the code required, you

4. set up github Actions for deploying code to GitHub pages 
this sets up the .github file, which has [hugo.yml](../../.github/workflows/hugo.yml) file     