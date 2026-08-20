---
layout: page
title: Ultramutator classifier
description: separating POLE driver from passenger mutations in targeted panel data
importance: 2
category: research
---

Whole-genome and whole-exome data make it relatively easy to spot an ultramutated tumor by its
mutational signature. Targeted panels — which is what most patients actually get sequenced with —
are a much harder problem: the panel covers too little of the genome for signature analysis to work
the way it does at whole-exome scale.

This project builds machine learning classifiers on [AACR GENIE](https://www.aacr.org/professionals/research/aacr-project-genie/)
targeted-panel data to tell *POLE* driver mutations apart from passengers, across panels of
differing composition. Features are engineered from mutation context rather than raw counts, which
is what makes the signal survive the drop in covered territory.

Beyond classification, the framework nominates candidate novel driver variants — ones not yet
characterized experimentally — as targets for functional follow-up in yeast.

Presented as a poster at the 25th Annual Midwest DNA Repair Symposium.
