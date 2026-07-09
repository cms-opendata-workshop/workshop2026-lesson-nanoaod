---
title: "How to access metadata on the command line?"
teaching: 5
exercises: 10
---

:::::: questions
- What is cernopendata-client?
- How to use cernopendata-client container image?
- How to get the list of files in a dataset on the command line?

::::::

:::::: objectives
- To be able to access the information programmatically

::::::

## Dataset information

Each CMS Open Data dataset comes with metadata that describes its contents (size, number of files, number of events, file listings, etc) and provenance (data-taking or generator configurations, and information on reprocessings), or provides usage instructions (the recommended CMSSW version, Global tag, container image, etc). The previous section showed how this information is displayed on the CERN Open Data portal. Now we see how it can also be retrieved programmatically or on the command line.


## Command-line tool

[cernopendata-client](https://cernopendata-client.readthedocs.io/en/latest/) is a command-line tool to download files or metadata of CERN Open Data portal records. It can be [installed](https://cernopendata-client.readthedocs.io/en/latest/installation.html) with `pip` or used through the container image.

As you already have [Docker]((https://cms-opendata-workshop.github.io/workshopwhepp-lesson-docker)) installed, we use the latter option. Pull the container image with:

```bash
docker pull docker.io/cernopendata/cernopendata-client
```

Display the command help with:

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

This is equivalent to running `cernopendata-client --help`, when the tool is installed with `pip`. The command runs in the container, it displays the output and exits. Note the flag `--rm`: it removes the container created by the command so that they are not accumulated in your container list each time you run a command.

### Get dataset information

Each dataset has a unique identifier, a record id (or `recid`), that shows in the dataset URL and can be used in the cernopendata-client commands.
For example, in the previous sections, you have seen that file listings are in multiple text files. To get the list of **all** files in the [/SingleMuon/Run2016H-UL2016_MiniAODv2_NanoAODv9-v1/NANOAOD](http://opendata.cern.ch/record/30563) dataset, use the following (`recid` of this dataset is 30563):

```bash
docker run -i -t --rm docker.io/cernopendata/cernopendata-client  get-file-locations --recid 30563 --protocol xrootd
```

or pipe it to a local file with:

```bash
docker run -i -t --rm docker.io/cernopendata/cernopendata-client  get-file-locations --recid 30563 --protocol xrootd > files-recid-30563.txt
```

:::::: prereq
## Explore other metadata fields
See how to get the metadata fields in JSON format with

```bash
docker run -i -t --rm docker.io/cernopendata/cernopendata-client  get-metadata --recid 30563
```

Note that the JSON format can be displayed in the CERN Open data portal web interface by adding `/export/json` in the dataset URL. Try it! 
::::::::::::

## Summary

`cernopendata-client` is a handy tool for getting dataset information programmatically in scripts and workflows.

We will be working on getting all metadata needed for an analysis of CMS Open Data datasets retrievable through cernopendata-client, and some improvements are about to be included in the latest version. Let us know what you would like to see implemented!
 <!-- on [Mattermost](https://mattermost.web.cern.ch/cmsodwswhepp24/channels/town-square)! -->

:::::: keypoints
- cernopendata-client is a command-line tool to download dataset files and metadata from the CERN Open Data portal.
::::::
