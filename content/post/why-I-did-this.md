+++
Categories = [
  "Jean's Journey",
  "Musings", 
  "Spotlights and Solutions",
  "Projects"]
Tags = []
date = "2015-07-16T17:54:38-07:00"
title = "Why I did this"

+++

Partly because I was curious about newfangled technology and partly because I need to try something out for more than 20 minutes.

I was eating lunch at work and looking at articles about new technology components- fancy web engines and really pretty interfaces. I’m always enthralled and I always think I should try it but it never gets very far. I start, the supposedly easy to use tool doesn’t compile twenty minutes in or I grow bored and I leave.

Hugo is the newfangled fancy thing I am trying and it is not easy. The front page is pretty and it lures you in. The defaults work pretty well but then you start to customize it and there are gaps in the documentation. Use <code> {{ delimit .Params.categories “, ” }} </code> to create comma separated categories. Oh really? Where do I stick this? It looks like it’s a function so I stuck it with the other functions in the layouts (overriding the themes defaults) but it wouldn’t render. I’ve spent about 1 hour on this issue already and it really shouldn’t be this hard. But part of this summer is learning about how to just keep moving forward in the face of all the little details being wrong and not correctly configured. Which I get is how things get done. But I don’t like it.

I also wanted some place to write up cool solutions that I had pieced together from various stack overflow answers, obscure documentation and creative tinkering. A place to feature mini projects I did that weren’t resume or portfolio worthy but could be helpful nonetheless.

There’s not really a plan for the blog but the basic layout is:


| Category |	Explanations |
|:---------|:----------------|
|Musings	| Thoughts about things. Simply, really. Posts about ideas I stumble across, books I’ve read, things I’ve learned, etc. | 
| Jean’s Journey |	This is my blog after all. Posts about seasonal routines and goals as well as tech related experiences (like GHC 2015!!) |
| Projects	| A place to feature things I’ve built. |
| Spotlights and Solutions |	My favorite category. Writeups for problems I’ve fixed and spotlights of cool technologies that solve problems I encounter. |
