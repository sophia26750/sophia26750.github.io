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

_Most Hugo Themes require these steps but may differ from theme to theme._ 

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

4. set up github Actions for deploying code to GitHub pages 
this sets up the .github file, which has [hugo.yml](../../.github/workflows/hugo.yml) file     
