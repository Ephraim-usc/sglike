gLike
========

genealogical Likelihood (gLike) is a maximum likelihood method to infer the demographic history
of given populations that best explains the observed genealogical relationships between sample haplotypes. 
This is, to our knowledge, the first attempt to infer all types of parameters
(split times, admixture times and proportions, migration rates) in a complex demography model under a unified framework.


Installation
------------

download the package and install from local:

    git clone https://github.com/Ephraim-usc/glike.git
    
    pip3 install ./glike


Full likelihood of genealogical trees
------------

Core functionality

    logp = glike.glike_trees(trees, demo)
    
Where `trees` is any enumerable that contains `tskit` genealogical trees.
And `demo` is the hypothesized Demography created manually or from provided models in `models.py`.
It returns the probability that such genealogical trees are generated under hypothesized demography.


Demography customization
------------

A Demography object is initialized with

    demo = glike.Demography()
    
And a number of discrete or continuous Phases are added into this Demography

    demo.add_phase(phase)

A continuous Phase is created by

    phase = ContinuousPhase(t1, t2, Q, n)

Where (t1, t2) is the time interval, Q is the infinitesimal generator of the Markov process for a single lineage (i.e., migration rate matrix with negative diagonal elements so that row sums are zero), and n is the vector of coalescent rates.


A discrete Phase is created by

    phase = DiscretePhase(t, P)

Where t is the time of the event, and P is the transition matrix.




About this project
-------------

This is an ongoing project, please refer to our poster at ASHG 2022 for a brief introduction.

If you are interested in knowing more, please let us know. Email the author: caoqifan@usc.edu

![](images/poster_ashg.png)
