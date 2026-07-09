---
title: "Introduction"
teaching: 10
exercises: 0
---


:::::: questions
- What is the point of these exercises?
- How do I find the data I want to work with?

::::::::::::::::::::::

:::::: objectives
- To understand why we start with the Open Data Portal
- To understand the basics of how the datasets are divided up

::::::::::::::::::::::


:::::: callout
## Ready to go?
The first part of this lesson is done entirely in the browser. 
 
Then, [Episode 4: How to access metadata on the command line?](04-cli-through-cernopendata-client.md) requires the use of a command-line tool. It is available as a Docker container or it can be installed with `pip`. Make sure you have completed the [Docker pre-exercise](https://cms-opendata-workshop.github.io/workshop2024-lesson-docker/) and have docker installed.

[Episode 5: What is in the data?](05-what-is-in-the-data.md) is done in the root or python tools container. Make sure you have [these containers available](https://cms-opendata-workshop.github.io/workshop2024-lesson-docker/03-docker-for-cms-opendata.html).

::::::


:::::: checklist

## You've got a great idea! What's next?

Suppose you have a great idea that you want to test out with real data! You're going to want
to know:

- [x] What **year** were the data taken that would work best for you?
- [x] In which **primary dataset** were the data of your interest stored?
- [x] What **Monte Carlo datasets** are available and appropriate for your studies?

   This may mean
   - finding simulated physics processes that are **background** to your signal
   - finding simulated physics processes for your **signal**, if they exist
   - possibly just finding simulated datasets where you *know* the answer, allowing you to test your new analysis techniques.

:::::: 

In this lesson, we'll walk through the process of finding out what data and 
Monte Carlo are available to you, how to find them, and how to examine what 
data are in the individual data files. 

:::::: callout
## What is a Monte Carlo dataset?
You'll often hear about physicists using *Monte Carlo data* or sometimes just referring to
*Monte Carlo*. In both cases, we are referring to *simulations* of different physics processes, 
which then mimics how the particles would move through the CMS detector and how they
might be affected (on average) as they pass through the material. This data is then 
processed just like the "real" data (referred to as *collider data*). 

In this way, the analysts can see how the detector records different physics processes
and best understand how these processes "look" when we analyze the data. This better
helps us understand both the signal that we are looking for and the backgrounds
which might hide what we are looking for. 
:::::: 


First of all, let's understand how the data are stored and why we need certain
tools to access them. 


## The CERN Open Data Portal

In some of the earliest discussions about making HEP data publicly available there were many concerns about 
people using and analyzing "other people's" data. The concern centered around well-meaning scientists improperly 
analyzing data and coming up with incorrect conclusions. 

While no system is perfect, one way to guard against this is to only release well-understood, well-calibrated 
datasets and to make sure open data analysts *only* use these datasets. These datasets are given
a [Digital Object Identifier (DOI)](https://www.doi.org/) code for tracking. And if there
are ever questions about the validity of the data, it allows us to check the 
[data provenance](https://en.wikipedia.org/wiki/Data_lineage#:~:text=Data%20provenance%20refers%20to%20records,the%20data%20and%20its%20origins.).

## DOI

The [Digital Object Identifier (DOI)](https://www.doi.org/) system allows people to assign a unique
ID to any piece of digital media: a book, a piece of music, a software package, or a dataset. If you want to learn
more about the DOI process, you can learn more at their [FAQ](https://www.doi.org/faq.html).  

:::::: challenge
## Challenge!
You will find that all the datasets have their DOI listed at the top of their page on the portal. 
Can you locate where the DOI is shown for this dataset, Record 30521,
[ DoubleEG primary dataset in NANOAOD format from RunG of 2016 (/DoubleEG/Run2016G-UL2016_MiniAODv2_NanoAODv9-v1/NANOAOD)](https://opendata.cern.ch/record/30521)

![](fig/portal_screenshot_cms_2016_doubleeg_nanoaod.png)

With a DOI, you can create citations to any of these records, for example using a tool like [doi2bib](https://www.doi2bib.org).
:::::: 

## Provenance

You will hear experimentalists refer to the "*provenance*" of a dataset. From the 
[Cambridge dictionary](https://dictionary.cambridge.org/us/dictionary/english/provenance), provenance
refers to "*the place of origin of something*". 
The way we use it, we are referring to how we keep track of the history of how a dataset was 
processed: what version of the software was used for reconstruction, what period of calibrations
was used during that processing, etc. In this way, we are documenting the 
[data lineage](https://en.wikipedia.org/wiki/Data_lineage#:~:text=Data%20provenance%20refers%20to%20records,the%20data%20and%20its%20origins.)
of our datasets. 

:::::: testimonial
## From  [Wikipedia](https://en.wikipedia.org/wiki/Data_lineage#:~:text=Data%20provenance%20refers%20to%20records,the%20data%20and%20its%20origins.)
Data lineage includes the data origin, what happens to it and where it moves over time.
Data lineage gives visibility while greatly simplifying the ability to trace errors back to the root cause in a data analytics process.
:::::: 

Provenance is an an important part of our data quality checks
and another reason we want to make sure you are using only vetted and calibrated data. 


## This lesson

For all the reasons given above, we encourage you to familiarize yourself with the search features and options
on the portal. With your feedback, we can also work to create better search tools/options and landing
points. 

This exercise will guide you through the current approach to finding data and Monte Carlo. Let's go!

:::::: keypoints
- Finding the data is non-trivial, but all the information is on the portal
- A careful understanding of the search options can help with finding what you need

::::::::::::::::::::::