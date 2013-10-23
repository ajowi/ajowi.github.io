---
layout: post
title:  "Science Hack Day Nairobi"
date:   2013-09-11 10:45:14
comments: true
categories: python machinelearning science physics lhc 
---

Science Hack Day(SHD) events are a great opportunity to learn and create new exciting things in just under 48 hours of hacking. See how [Science Hack Day](http://sciencehackday.org) started.

The first SHD event came to Nairobi, Kenya. in April, 2012. I was very excited. The organizers had set up a [Wiki](http://shdnairobi.pbworks.com/w/page/52729796/nairobihacks2012) where participants post their hack ideas before the big day. There, you can find a list of all SHD Nairobi hacks ideas. 

Muons Flight Path in action...

![Mouns Flight Path Presentation by @chiteri](http://davidajowi.com/images/chiteri_muons_flight_path.jpg)

We were very fortunate to have Large Hadron Collider(LHC) datasets from the Compact Muon Solenoid(CMS) experiments (many thanks to [@matt_bellis](https://twitter.com/matt_bellis)). I had little knowledge of the structure of this data. Nevertheless, this would form the basis of our hack at the first SHD Nairobi event. A team of three, we set to create the Mouns Flight Path.

Muons Flight Paths is an animated representation of the journey elementary particles would go if they were to travel un-interrupted from the Physics labs at CERN. This happens after an extremely high-energy proton-proton collision at near the speeds of light inside the LHC.


**The Animation**

![Mouns Flight Path Animation](http://davidajowi.com/images/muons1.png)

See the full animation in this [YouTube video](https://www.youtube.com/watch?v=ag7w0vgZj5g) (am still struggling to embed a video on GitHub Pages)
 
For detailed explanation of the animation and the physics behind it see the project's GitHub page at [SHD Nairobi LHC Data Hack](https://github.com/ajowi/shdnbi_lhcdatahack)



##SHD Nairobi 2013##

In June, 2013., came the second SHD with a whole lot of new experiences. See a (list of hacks)[] from SHD Nairobi 2013.

During this event I had the privilege to work on the  Machine Learning (ML) for Physics hack - a project based on ideas of Machine Learning (M.L). We had to train computers to accurately recognize sentences in either Swahili or English out of reading entries from Wikipedia in both languages. Similar rules and techniques were applied afterwards to detect the presence of particular sub-atomic particles inside Physics data collected from the Compact Muon Solenoid (C.M.S) experiment at CERN.

We extracted sentences from the Swahili and English Wikipedia articles dump. Latest dumps for the [Swahili Wiki](http://dumps.wikimedia.org/swwiki) and [English Wiki](http://dumps.wikimedia.org/enwiki) can be downloaded online. This cool [WikiExtractor](http://alas.matf.bg.ac.rs/~mr04069/WikiExtractor.py) script can be handy when you want to extract topics/sentences from the wiki dumps. 

Using Python programming language we wrote a script to extract set of sentences to seperate text files. Then counted the number of occurances a partucular letter say 'u' appeared in both the sets of Swahili and English sentences. We then calculated the fraction of the number of times the letter appeared in each sentence and wrote the results to a file, as columns. This would be our training data.

{%highlight ruby%}
0.131868 0.087912 0.098901 0.076923 0.065934 0.153061 0.091837
0.051020 0.081633 0.091837 0.157895 0.073684 0.105263 0.042105
0.115789 0.170213 0.056738 0.127660 0.049645 0.042553 0.212121
{%endhighlight%}

With [NumFocus](http://numfocus.org/) and related tools and the above training data, we started our machine learning process. Decision Trees(DT) for supervised learning was chosen as the ideal algorithm for training. This would help us create a model that predicts the value of a target variable by learning simple decision rules. These rules are inferred from the training data features. For example, with this data we were able to tell whether a sentence is Swahili or English based on the letter occurances in that particular sentence. DTs have their share of advantages and disadvatages -- find out more at the [SciKit Learn DTs](http://scikit-learn.org/stable/modules/tree.html) page.

Upon training we generated the below graph by plotting the letter occurrances in the different sets of our Swahili and English training datasets.


![Machine Learning in Action](http://davidajowi.com/images/ml.png)


I am still playing around with this data, hopefully in a future post I will get an opportunity explain the plots and behaviour of the LHC dataset.


A list of tools we used and source code are available at [SHD Nairobi 2013 Machine Learning](https://github.com/ajowi/shdnbi2013_machinelearning) page on GitHub. Feel free to fork.


##SHD Nairobi 2014##

Am already psyched up for upcoming SHD Nairobi. As always looking forward to learning new ways of doing things and making new friends. See you at SHD Nairobi 2014.