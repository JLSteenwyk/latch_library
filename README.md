<center>

# Latch Library <br /> <img src="img/latch_library_logo.jpg" alt="logo" width="200"/>

</center>


>"The only thing that you absolutely have to know, is the location of the library." - Albert Einstein 

<br />

There are common snippets of code used across diverse workflows in the [LatchBio SDK](https://console.latch.bio/explore). This community-led encyclopedia aims to catalog common code snippets and save developer time. Please feel free to [contribute](CONTRIBUTING.md)!

<br />

Join the Slack community! 

[![SLACK](https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white)](https://twitter.com/LatchBio/status/1527781165783867392)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table of Contents

- [Genome Assembly](#genome-assembly)
  - [De novo](#de-novo)
  - [Metrics](#metrics)
- [Multiple sequence alignment](#multiple-sequence-alignment)
  - [Align](#align)
  - [Trimming](#trimming)
  - [Summary statistics](#summary-statistics)
- [Phylogenetics](#phylogenetics)
  - [Phylogenetic inference](#phylogenetic-inference)
- [Codon analyses](#codon-analyses)
  - [Optimization](#optimization)
- [Contributors](#contributors)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---

### I/O operations

#### Writing out stdout

- **capturing stdout**
    - bioinformaticians are frequently captured the stdout using the `>` character from one software to feed into another. Use this code snippet for writing the stdout to a file and returning the output.
    - [snippet](snippets/capturing_stdout.py) | [example code](https://github.com/JLSteenwyk/latch_wf_codon_optimization/blob/main/wf/__init__.py)

<br />

- **handling multiple output files**
    - numerous software will generate multiple output files that have the same prefix
    - the best way to deal with this is by writing them all to a directory and then returning the resulting directory
    - [snippet](snippets/returning_a_directory_of_results.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_infer_phylogeny)

<br />

### Contributors
![Your Repository's Stats](https://contrib.rocks/image?repo=jlsteenwyk/latch_library)