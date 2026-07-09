---
title: "NanoAOD exercises"
teaching: 10
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- What have we learned in the pre-exercises and how can we apply it?
- What is the structure and content of the nanoAOD format?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Apply what we have learned in the pre-exercises
- Learn about the structure and content of nanoAOD

::::::::::::::::::::::::::::::::::::::::::::::::

## Exercises with NanoAOD

::::::::::::::::::::::::::::::::::::: challenge 

## Exercise 1: Get data file locations

Let's select a ZprimeToTT sample for a given mass and using
the `cernopendata-client` to get the associated data files

Recall what you've learned from the [pre-exercise](https://cms-opendata-workshop.github.io/workshop2024-lesson-dataset-scouting/instructor/04-cli-through-cernopendata-client.html) on the `cernopendata-client`. 

:::::::::::::::::::::::: solution 

## Solution

Search for the ZprimeToTT samples in the CERN Open Data Portal. The resulting query is [here](https://opendata.cern.ch/search?q=ZprimeToTT%2A&f=experiment%3ACMS&f=year%3A2016&f=file_type%3Ananoaodsim&f=category%3AExotica%2Bsubcategory%3AHeavy%20Gauge%20Bosons&f=type%3ADataset&l=list&order=asc&p=1&s=10&sort=bestmatch).

Next, select a dataset. Here we fetch [this one](https://opendata.cern.ch/record/75124), record 75124, "Simulated dataset ZPrimeToTT_M1000_W100_TuneCP2_13TeV-madgraph-pythia8 in NANOAODSIM format for 2016 collision data" where the Z' mass is 1000 GeV.

Fetch the Docker image for the `cernopendata-client`:

```bash
docker pull docker.io/cernopendata/cernopendata-client
```

and refresh your memory on the commands:
```bash
docker run -i -t --rm docker.io/cernopendata/cernopendata-client --help
```
```output
Usage: cernopendata-client [OPTIONS] COMMAND [ARGS]...

  Command-line client for interacting with CERN Open Data portal.

Options:
  --help  Show this message and exit.

Commands:
  download-files      Download data files belonging to a record.
  get-file-locations  Get a list of data file locations of a record.
  get-metadata        Get metadata content of a record.
  list-directory      List contents of a EOSPUBLIC Open Data directory.
  verify-files        Verify downloaded data file integrity.
  version             Return cernopendata-client version.
```

Then fetch the files for record 75124:
```python
cernopendata-client get-file-locations --recid 75124
```

```output
http://opendata.cern.ch/eos/opendata/cms/mc/RunIISummer20UL16NanoAODv9/ZPrimeToTT_M1000_W100_TuneCP2_13TeV-madgraph-pythia8/NANOAODSIM/106X_mcRun2_asymptotic_v17-v2/2520000/65A0736B-22F3-C94C-99AE-36717B28629C.root
http://opendata.cern.ch/eos/opendata/cms/mc/RunIISummer20UL16NanoAODv9/ZPrimeToTT_M1000_W100_TuneCP2_13TeV-madgraph-pythia8/NANOAODSIM/106X_mcRun2_asymptotic_v17-v2/2520000/6E508763-A12F-8846-A295-F39EE7DDAA52.root
http://opendata.cern.ch/eos/opendata/cms/mc/RunIISummer20UL16NanoAODv9/ZPrimeToTT_M1000_W100_TuneCP2_13TeV-madgraph-pythia8/NANOAODSIM/106X_mcRun2_asymptotic_v17-v2/2530000/7B2D5CD5-9CAE-C046-A9AB-50CE9D48B187.root
http://opendata.cern.ch/eos/opendata/cms/mc/RunIISummer20UL16NanoAODv9/ZPrimeToTT_M1000_W100_TuneCP2_13TeV-madgraph-pythia8/NANOAODSIM/106X_mcRun2_asymptotic_v17-v2/260000/1A50245D-8213-6340-8EA0-CB064EEC6AF3.root
http://opendata.cern.ch/eos/opendata/cms/mc/RunIISummer20UL16NanoAODv9/ZPrimeToTT_M1000_W100_TuneCP2_13TeV-madgraph-pythia8/NANOAODSIM/106X_mcRun2_asymptotic_v17-v2/270000/09FA6C37-21D6-7846-B3E1-F8086CBA0E9E.root
http://opendata.cern.ch/eos/opendata/cms/mc/RunIISummer20UL16NanoAODv9/ZPrimeToTT_M1000_W100_TuneCP2_13TeV-madgraph-pythia8/NANOAODSIM/106X_mcRun2_asymptotic_v17-v2/270000/3AAB5B1E-7169-9C4D-841C-CB2D6E40CBAE.root
http://opendata.cern.ch/eos/opendata/cms/mc/RunIISummer20UL16NanoAODv9/ZPrimeToTT_M1000_W100_TuneCP2_13TeV-madgraph-pythia8/NANOAODSIM/106X_mcRun2_asymptotic_v17-v2/270000/820C3EBC-0E1D-CE41-9418-FA1615123FC2.root
http://opendata.cern.ch/eos/opendata/cms/mc/RunIISummer20UL16NanoAODv9/ZPrimeToTT_M1000_W100_TuneCP2_13TeV-madgraph-pythia8/NANOAODSIM/106X_mcRun2_asymptotic_v17-v2/270000/CF54D079-349C-FB4F-B6E5-3D579D89EDE4.root
http://opendata.cern.ch/eos/opendata/cms/mc/RunIISummer20UL16NanoAODv9/ZPrimeToTT_M1000_W100_TuneCP2_13TeV-madgraph-pythia8/NANOAODSIM/106X_mcRun2_asymptotic_v17-v2/80000/E964C281-43FB-D349-A436-9A3FDA0BAA28.root
```
:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::: challenge

## Exercise 2: Inspect the data file

:::::::::::::: solution


::::::::::::::

::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints 

- Use `.md` files for episodes when you want static content
- Use `.Rmd` files for episodes when you need to generate output
- Run `sandpaper::check_lesson()` to identify any issues with your lesson
- Run `sandpaper::build_lesson()` to preview your lesson locally

::::::::::::::::::::::::::::::::::::::::::::::::

[r-markdown]: https://rmarkdown.rstudio.com/
