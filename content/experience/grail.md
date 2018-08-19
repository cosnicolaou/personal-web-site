---
title: "GRAIL"
description: "Head of Technology Infrastructure, Distinguished Engineer"
from: "May 2016"
to: "present"
date: "2016-05-01"
repo: ""
tags: []
weight: 0
draft: false
---

[GRAIL](https://grail.com) is developing Next Generation Sequencing tests
that look for signs of early-stage cancer by sequencing the DNA/RNA in plasma.
This is similar to the existing notion of a liquid biopsy but aimed at screening
asymptomatic people and hence must detect much, smaller amounts of tumour material.
The first published results were at [ASCO](https://www.asco.org/about-asco/press-center/news-releases/blood-test-shows-potential-detection-tool-early-stage-lung) and [AACR](https://grail.com/wp-content/uploads/2018/05/AACR_2018_CCGAFirstReadout_Aravanis_ORP_Final.pdf).

I was responsible for building the team and systems to support the
analysis pipelines that manage and process the output from sequencing. We built
a large number of tools to make working on AWS easier for the science team
as well as tools for running the analysis software concurrently. Much of this
software is available on [github](https://github.com/grailbio) and in outline
consists of:

- a workflow manager that caches intermediate results for reuse in subsequent runs as
 well as supporting reproducible execution. This makes it possible to confidently delete
 data that is cheaper to recompute whilst being able to reuse transparently to the user
 in the interim. Given the scale of the processing involved this has saved the company
 a large amount of money as well as making it easier to build and manage the pipelines.
- a fine grained authentication system with a simple user-interface that allows us
to provide granular access to AWS resources without pushing the management of large
numbers of long-lived credentials on our users.
- general purpose file formats that support per-file encryption, concurrent reading and writing.
- bioinformatics file formats that can be used alongside the existing bcl and bam/sam
formats but that offer both better compression and concurrent access. Both of which
make a difference when running at scale.

One of my team's goals is to generally improve the software available for
bionfiormatics work across the entire industry.

In the summer of 2018 I transitioned to an individual contributor role on
a part time basis.

