---
title: "NanoAOD datasets"
teaching: 10
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- How do we find a specific nanoAOD dataset?
- How to we explore the content of our nanoAOD dataset?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Know how to find nanoAOD datasets
- Know how to explore the content of nanoAOD 

::::::::::::::::::::::::::::::::::::::::::::::::

## Find and explore a nanoAOD dataset

Let's find and explore a particular which we will get even further into
later: simulated Z' events in which the Z' decays to a top and antitop quark pair.

:::::: callout
A Z' ("Z-prime") is a hypothetical heavy gauge boson that could come from
extensions of the Standard Model. A review of searches for the Z' 
can be found [here](https://pdg.lbl.gov/2024/reviews/rpp2024-rev-zprime-searches.pdf)
::::::

### Find the dataset

All data can be found via the [CERN Open Data Portal](https://opendata.cern.ch).
Let's go to the website and search the simulated Z' datasets. 

Dataset naming in CMS can seem obscure but let's do something simple and search for "Zprime*":

![](fig/ZprimeODP.png){alt='Search for Zprime* at the CODP'}

The query results are [here](https://opendata.cern.ch/search?q=Zprime%2A&l=list&order=asc&p=1&s=10&sort=bestmatch) and you can see that there are many (over 1000) records returned:

![](fig/ZprimeODP-results.png){alt='Search results for Zprime*'}

Let's narrow down the results and select "Type: Dataset", "Experiment: CMS", "Year: 2016", "File type: nanoaodsim", and "Category: Heavy Gauge Bosons". We've now reduced the number of [matches](https://opendata.cern.ch/search?q=Zprime%2A&f=experiment%3ACMS&f=year%3A2016&f=file_type%3Ananoaodsim&f=category%3AExotica%2Bsubcategory%3AHeavy%20Gauge%20Bosons&f=type%3ADataset&l=list&order=asc&p=1&s=10&sort=bestmatch) from over 1000 down to 210:

![](fig/ZprimeODP-results2.png){alt='Narrowed search results for Zprime*'}

We can discern some of the logic behind the simulated dataset naming. "Zprime" is the particle produced and it decays to various products. We want $Z^{'} \rightarrow t\bar{t}$ which shows up as the third result so let's [narrow the search](https://opendata.cern.ch/search?q=ZprimeToTT%2A&f=experiment%3ACMS&f=year%3A2016&f=file_type%3Ananoaodsim&f=category%3AExotica%2Bsubcategory%3AHeavy%20Gauge%20Bosons&f=type%3ADataset&l=list&order=asc&p=1&s=10&sort=bestmatch) further and search with "ZprimeToTT*":

![](fig/ZprimeToTT-results.png){alt='Narrowed search results for Zprime*'}

We can also discern that the dataset names also include the mass (in GeV) of the hypothetical Z' (e.g. "_M2000"). 

TO-DO: what do the other strings mean in the dataset name?

Possible challenge: have them select a mass and search for the dataset and select a file for the next part.

Next, let's use the `cernopendata-client` command-line tool to find the datasets
and fetch a file.

### Explore a file

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

Inline instructor notes can help inform instructors of timing challenges
associated with the lessons. They appear in the "Instructor View"

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints 

- Use `.md` files for episodes when you want static content
- Use `.Rmd` files for episodes when you need to generate output
- Run `sandpaper::check_lesson()` to identify any issues with your lesson
- Run `sandpaper::build_lesson()` to preview your lesson locally

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
