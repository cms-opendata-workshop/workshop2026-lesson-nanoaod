---
title: Setup
---

The first episodes of this lesson can be worked through in a web browser.

Episodes 4, 5, and 6 require a Python environment. This can be on a terminal on your
local machine or on a server. Alternatively, you can run Python in a jupyter notebook. In 
this case, the Python commands will remain the same, but for shell commands marked as *BASH*
you will have to add a `!` to the beginning of the command, as demonstrated below.


Install the following packages with `pip`:

```bash
pip install cernopendata-client uproot awkward numpy matplotlib jupyterlab
```

If in the jupyter notebook:

```bash
!pip install cernopendata-client uproot awkward numpy matplotlib jupyterlab
```

You will also need XRootD support to stream files directly from the CERN Open Data storage. Install it with:

```bash
pip install xrootd fsspec-xrootd
```

A Unix terminal (Linux, macOS terminal, or Windows WSL2 Ubuntu terminal) is required for the command-line steps.

