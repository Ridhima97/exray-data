# Overview

This repository accompanies the paper "Ex-Ray: Detection of History-Leaking Browser Extensions".
A blog post describing the paper is available [here](http://mweissbacher.com/blog/2017/10/05/ex-ray-finding-browser-extensions-that-spy-on-your-browsing-habits/).
A brief description of the files is provided below, for details please see the paper.

Generally, extensions are named with their 32 character extension ID and end with their version number.

## Unsupervised Flagging

File `unsupervised-flagged.txt` contains unsupervised flagging data based on traffic data alone.
This step is based on counterfactual analysis of network traffic, after executing an extension in multiple stages.
We treat the extension as a controlled environment and the size of history as input variable.
The observed network traffic is the output variable.


## Linear Regression

File `linear_regression.json` - labeled set of 212 samples that were flagged by the linear regression system including false positives.

## Triage Data

File `triagereport.txt` features a run of our extension triage component.
We split up extension network flows by remote hostname, and calculate a score how likely it is to leak.
The lower the less likely it is to leak, and vice versa.
Scores below 1 mean it is unlikely to leak, up until 100 it is possibly leaking, above that it is likely to leak.
We would like to emphasize that this is an add-on component with the goal of aiding an analyst, not providing definite decisions.


# Getting Chrome Extensions

Extensions are either available for the official store,
alternatively from https://crx.dam.io - this site also features older versions.

