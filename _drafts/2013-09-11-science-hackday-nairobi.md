I have participated in the Science Hack Day(SHD) events for the second year now. It is usually a great opportunity to create new exciting things in just 48 hours of hacking. To learn more about Science Hack Day and how it started visit [Science Hack Day Home](http://sciencehackday.org).

It all started in April, 2012 when the first Science Hack Day came to Nairobi - the "Green City in the Sun". I was very excited as everyone I talked to was. In fact, the motto of SHD is to "Get excited and make things happen with science". The organizers had set up a wiki where participants are encouraged to post their hack ideas before the big day. For a list of SHD Nairobi 2012 hacks ideas visit [SHD Nairobi Wiki](http://shdnairobi.pbworks.com/w/page/52729796/nairobihacks2012). 

![Mouns Flight Path Presentation by @chiteri](http://davidajowi.com/images/chiteri_muons_flight_path.jpg)

One of the organizers, having participated in SHD San Fransisco, hinted at the availability of Large Hadron Collider(LHC) datasets from the Compact Muon Solenoid(CMS) experiments. This would form the basis of our hack at the first SHD Nairobi event. A team of three, we obtained the datasets to create the Mouns Flight Path.

Muons Flight Paths is an animated representation of the journey elementary particles would go if they were to travel un-interrupted from the Physics labs at CERN. This happens after an extremely high-energy proton-proton collision at near the speeds of light inside the LHC. See the animation in action below.


**The Animation**

A small red dot represents the coordinates of CERN, which straddles the borders of France and Switzerland. 

A pulsating square of green, red, and black is located at the coordinates of Nairobi, Kenya, the location for this Science Hack Day. 

A pink line, pointing from CERN to the west, is the definition of the z-axis, along which LHC is colliding the proton beams inside of the CMS detector.

For detailed explanation of the animation and the physics behind it see the project's GitHub page at (SHD Nairobi LHC Data Hack)[https://github.com/ajowi/shdnbi_lhcdatahack]

Hats off to all the (winning hacks)[http://www.sciencehackday.or.ke/post/2012/apr/18/winning-hacks/] SHD Nairobi 2012.


**SHD Nairobi 2013**

In June, 2013., came the second SHD with a whole lot of new experiences. The number of participants in this edition more than doubled -- an indication of just how SHD gets people involved in creating new exciting things. See (list of hacks)[] for SHD Nairobi 2013.

Again, during this event I worked on the  Machine Learning (ML) for Physics hack - a project based on ideas of Machine Learning (M.L). The group had to train computers to accurately recognize sentences in either Swahili or English out of reading entries from Wikipedia in both languages. Similar rules and techniques were applied afterwards to detect the presence of particular sub-atomic particles inside Physics data collected from the Compact Muon Solenoid (C.M.S) experiment at CERN.

The first task was to extract sentences from the Swahili and English Wikipedia articles dump. Latest dumps for the [Swahili Wiki](http://dumps.wikimedia.org/swwiki) and [English Wiki](http://dumps.wikimedia.org/enwiki) can be downloaded online. This [WikiExtractor](http://alas.matf.bg.ac.rs/~mr04069/WikiExtractor.py) script was useful in extracting the topics/sentences from the wiki dumps. 

We wrote the extracted set of sentences to seperate files. Once this was done we wrote a python scipt to count number of occurances a partucular letter say 'u' appeared in both the sets of Swahili and English sentences. We then calculated the fraction of the number of times the letter appeared in each sentence and wrote the results to a file, as columns. This would be our training data.

{%highlight ruby%}
0.131868 0.087912 0.098901 0.076923 0.065934 0.153061 0.091837
0.051020 0.081633 0.091837 0.157895 0.073684 0.105263 0.042105
0.115789 0.170213 0.056738 0.127660 0.049645 0.042553 0.212121
{%endhighlight%}

Armed with [SciKit Learn](http://scikit-learn.org/stable/) and [NumPy](http://www.numpy.org/) and the above training data, we were ready start the standard machine learning procedure. Our algorithm of choice was the Decision Trees(DT) for supervised learning. This would help us create a model that predict the value of a target variable by learning simple decision rules. These rules are inferred from the training data features. For example, with our data were able to tell that a sentence is Swahili or English based on the letter occurances in that particular sentence. DTs have their share od advantages and disadvatages -- find our more at the [SciKit Learn DTs](http://scikit-learn.org/stable/modules/tree.html) page.


Credits: [@matt_bellis](https://twitter.com/matt_bellis), [@chiteri](), [Morris Mwanga](http://nerd.co.ke/morris),[@FOnuonga](), Jessica Muenkel 

A list of tools used and source code can be found at [SHD Nairobi 2013 Machine Learning](https://github.com/ajowi/shdnbi2013_machinelearning) page on GitHub.


**SHD Nairobi 2014**

Am already psyched up for SHD Nairobi 2014. As always looking forward to learning new ways of doing things and making new friends. There are already ideas coming through on what topics we should hack on. But, that is a subject for a future post.