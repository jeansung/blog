+++
Categories = ["Spotlights and Solutions"]
Tags = []
date = "2015-08-03T22:01:05-07:00"
title = "My Hugo Website Setup"
+++



###  Getting Started
I was lured to use [Hugo](http://gohugo.io/) because of its pretty front end on the main website and the promise that I could develop in Markdown. I have 3 websites, my [front page](http://jeansung.github.io/frontpage/), my [blog](http://jeansung.github.io/blog/) and my [portfolio](http://jeansung.github.io/Projects/) and the first two are setup through hugo. Here's my setup story. 

### My setup 
I'm hosting it on github pages. Here's my [tutorial](https://github.com/jeansung/MyPersonalPage/wiki) how to set that up. I'm using hugo with github pages. Here's the [tutorial](http://gohugo.io/tutorials/github-pages-blog/) I used. 

When I test my changes, I run the command:

```
hugo server --watch --buildDrafts --theme=material-design
```

This command runs a local server for the website to sit on, build drafts, automatically reloads pages and then applies the theme. You can delete the `public/` folder to force the theme to reload completely. 

When I'm ready to publish, I use a modified version of the tutorial's demo `deploy.sh` script. 

```
#!/bin/bash

# Black        0;30     Dark Gray     1;30
# Red          0;31     Light Red     1;31
# Green        0;32     Light Green   1;32
# Brown/Orange 0;33     Yellow        1;33
# Blue         0;34     Light Blue    1;34
# Purple       0;35     Light Purple  1;35
# Cyan         0;36     Light Cyan    1;36
# Light Gray   0;37     White         1;37

CYAN='\033[0;36m'
NC='\033[0m'

echo -e "${CYAN} Deploying updates to GitHub... ${NC}"


# Build the project. 
hugo --theme material-design

# Add changes to git.
git add -A

# Commit changes.
msg="Rebuilding site `date`"
if [ $# -eq 1 ]
  then msg="$1"
fi
git commit -m "$msg"

# Push source and build repos.
git push origin master
git subtree push --prefix=public git@github.com:jeansung/blog.git gh-pages
```

### My thoughts

It's not all rainbows and puppies. This set up is definitely better than my last set up, which consisted mainly of using github pages to host the website and then using `HTML` tinkering to create the content. That was hard coded and unsustainable. The templates here make it much easier to change only what I need to. However, the `git subtree` workflow is very messy when it goes wrong and I had to `rm -rf` some of the earlier repos that got messed up. My setup really doesn't use the version control in the sense of branching and rolling back. It's almost entirely a linear setup, so that works. But I could imagine more heartache if you needed to `git revert` some files. Also, I need to consolidate the websites to one site, but that's for a different day. 
