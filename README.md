## Jean's technical blog
* [homepage](http://jeansung.github.io/)
* [technical blog](http://jeansung.github.io/blog/)

## Pre reqs
* Install hugo via `brew install hugo`
* Install the material-design theme by `cd themes` and `git clone https://github.com/pdevty/material-design.git`

## Testing
Use `hugo server --watch` to test locally. It will update automatically when you save new files. Use `subl blog` to open the folder in the [Sublime Text Editor](https://www.sublimetext.com/docs/2/osx_command_line.html). 

## Add new content
* Use `hugo new post/{FILE}.md` where `FILE` is the name is the new post. The file is automatically populated with:

```
+++
Categories = ["Jean's Journey", "Musings", "Spotlights and Solutions", "Projects"]
Tags = []
date = "2016-07-25T16:31:16-07:00"
title = "college grad reflections"

+++
```

* Delete the categories in `Categories` that is not relevant, and update `title`. 

## Uploading new changes 
Please use `./deploy` or `./deploy <commit message>` to push new changes. 