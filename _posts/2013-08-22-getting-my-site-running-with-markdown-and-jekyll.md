---
layout: post
title:  "Getting My Site Running With Markdown + Jekyll!"
date:   2013-08-22 10:45:14
categories: jekyll markdown
---

I finally managed to get this site up and running, thanks to this tool -> [Jekyll](http://jekyllrb.com/). What Jekyll does is transform your plain text files into static web pages -- it is a static site generator written by [Tom Preston](http://tom.preston-werner.com/).

This being my first post I am going to write about my experience setting up this website. First, I wanted to have a website that could easily be managed using version control. So anytime am pushing my files to the server the website gets updated instantly. I have heard about GitHub Pages before. And since I love Git I ultimately made a decision to host this site on [GitHub](http://github.com) using [GitHub Pages](http://pages.github.com) - and what's more, it is free of charge. Yes, I love "Free" -- where I come from "Free" means "Freedom".

I will be working locally on a PC-BSD 9.1 Isotope Edition installation. This, after my beloved ***sibuor*** (my native language for Mountain Lion) got lost over the weekend -- still suffering from Mountain Lion depression syndrome. 

These are the requirements:-

1. a github account
2. ruby 1.9.3 - github-pages requires this version of ruby
3. github-pages gem - this installs Jekyll and other required gems

My GitHub account is active. There are two different types of pages available with GitHub Pages that I can create. For my website I will be creating a User Page. 

GitHub's naming scheme dictates that all User pages **must** exist in a directory named username/username.github.io.

I signed in to my GitHub account and created my repo at ajowi/ajowi.github.io.

Then cloned the repo

```    
git clone https://github.com/ajowi/ajowi.github.io.git
```    

Checked my Ruby version

```
ruby -v
```

The installed Ruby version on my local machine is ruby 1.8.7. github-pages needs version 1.9.3. I  achieve this by installing Ruby Version Manager(RVM) - "a command-line tool which allows you to easily install, manage, and work with multiple ruby environments from interpreters to sets of gems."

```
\curl -L https://get.rvm.io | bash -s stable --ruby=1.9.3
```

My default shell is zsh and for rvm to work perfectly ok I need to edit my ~/.zshrc file by appending the following line

**[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"**


Followed by a restart of my shell program for the changes to take effect. Then enable ruby 1.9.3.

```
rvm list
rvm use ruby-1.9.3-p448 --default
ruby -v
```

I now have ruby 1.9.3 as my default ruby version. 

Installing github-pages will also install Jekyll and other required gems like rdiscount, liquid, pygments...

```
sudo gem install github-pages
gem list --local
```

The last line above verifies all gems are installed. 

Everything seems to be in order. I now create my new Jekyll powered site and fire up the Jekyll local server to see the generated pages.

```
cd ajowi.github.io
jekyll new site
cp site/* .
rm -rf site
jekyll serve -w
```

This results in the error:***Cannot convert***

Editing _config file and replacing markdown:maruku with markdown:rdiscount as the Markdown engine solved the problem.

By pointing my browser to http:localhost:4000. I am able to see my new website -- just like that!

It is really easy and fun setting up a webpage with Jekyll (such an awesome tool) - truly gets you running in seconds. And the GitHub integration is just the killer. I can now have all my web content in text files beautifully formated in Markdown/Textile and hosted on GitHub.  I publish my work locally, push changes to GitHub and there you go! My website is up to date.