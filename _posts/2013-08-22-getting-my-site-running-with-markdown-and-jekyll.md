---
layout: post
title:  "Getting My Site Running With Markdown + Jekyll!"
date:   2013-08-22 10:45:14
categories: jekyll markdown
---

I finally managed to get this site up and running, thanks to this tool -> [Jekyll](http://jekyllrb.com/). What Jekyll does is transform your plain text files into static web pages -- it is a static site generator written by [Tom Preston](http://tom.preston-werner.com/).

This being my first post I am going to write about my experience setting up this website. First, I wanted to have a website that could easily be managed using version control. So anytime am pushing my files to the server the website gets updated instantly. I have heard about GitHub Pages before. And since I love <span class="bdr">Git</span> I ultimately made a decision to host this site on [GitHub](http://github.com) using [GitHub Pages](http://pages.github.com) - and what's more, it is free of charge. Yes, I love "Free". Where I come from "Free" means "Freedom".

I will be working locally on a <span class="bdr">PC-BSD 9.1 Isotope Edition</span> installation. This, after my beloved ***sibuor*** (my native language for Mountain Lion) got lost over the weekend -- still suffering from Mountain Lion depression syndrome. 

These are the requirements:-

1. a github account
2. <span class="bdr">ruby 1.9.3</span> - github-pages requires this version of ruby
3. <span class="bdr">github-pages</span> - this installs Jekyll and other required gems

My GitHub account is active. There are two different types of pages available with GitHub Pages that I can create. For my website I will be creating a User Page. 

GitHub's naming scheme dictates that all User pages **must** exist in a directory named <span class="bdr">username/username.github.io</span>.

I signed in to my GitHub account and created my repo at <span class="bdr">ajowi/ajowi.github.io</span>.

Then cloned the repo

{% highlight bash %}    
git clone https://github.com/ajowi/ajowi.github.io.git
{% endhighlight %}   

Checked my Ruby version

{% highlight bash %}
ruby -v
{% endhighlight %} 

The installed Ruby version on my local machine is <span class="bdr">ruby 1.8.7</span>. <span class="bdr">github-pages</span> needs version 1.9.3. I  achieve this by installing [Ruby Version Manager(RVM)](http://rvm.io) - "a command-line tool which allows you to easily install, manage, and work with multiple ruby environments from interpreters to sets of gems."

{% highlight bash %}
\curl -L https://get.rvm.io | bash -s stable --ruby=1.9.3
{% endhighlight %} 

My default shell is <span class="bdr">zsh</span> and for <span class="bdr">rvm</span> to work perfectly ok I need to edit my <span class="bdr">~/.zshrc</span> file by appending the following line

**[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm"**


Followed by a restart of my shell program for the changes to take effect. Then enable <span class="bdr">ruby 1.9.3</span>.

{% highlight bash %}
rvm list
rvm use ruby-1.9.3-p448 --default
ruby -v
{% endhighlight %} 

I now have <span class="bdr">ruby 1.9.3</span> as my default ruby version. 

Installing <span class="bdr">github-pages</span> will also install Jekyll and other required gems like rdiscount, liquid, pygments...

{% highlight bash %}
sudo gem install github-pages
gem list --local
{% endhighlight %} 

The last line above verifies all gems are installed. 

Everything seems to be in order. I can now create my new Jekyll powered site and fire up the Jekyll local server to see the generated pages.

{% highlight bash %}
cd ajowi.github.io
jekyll new site
cp site/* .
rm -rf site
jekyll serve -w
{% endhighlight %} 

This results in the error:

***Conversion error: There was an error converting '_posts/2013-08-22-getting-my-site-running-with-markdown-and-jekyll.md'***

***error: MaRuKu encountered problem(s) while converting your markup.. Use --trace to view backtrace***

Editing <span class="bdr">_config.yml</span> file and replacing <span class="bdr">markdown:maruku</span> with <span class="bdr">markdown:rdiscount</span> as the Markdown engine solved the problem.

By pointing my browser to <span class="bdr">http:localhost:4000</span>. I am now able to see Jekyll in action -- my new website, just like that!

It is really easy and fun setting up a webpage with Jekyll (such an awesome tool) - truly gets you running in seconds. And the GitHub integration is just the killer. I can now have all my web content in text files beautifully formated in Markdown/Textile and hosted on GitHub.  I publish my work locally, push changes to GitHub and there you go! My website is up to date.