<img src="img/latch_library_logo.jpg" alt="logo" width="200"/>

<br />

>"The only thing that you absolutely have to know, is the location of the library." - Albert Einstein 

### Mission

There are common snippets of code used across diverse workflows in the [LatchBio SDK](https://console.latch.bio/explore). This community-led encyclopedia aims to catalog common code snippets and save developer time. Please feel free to [contribute](CONTRIBUTING.md)!

### Join the community!
Become an [SDK contributor](https://latch.bio/sdk)! To join the Slack community, send [Kenny Workman](https://github.com/kennyworkman) a direct message.

[![SLACK](https://img.shields.io/badge/Slack-4A154B?style=for-the-badge&logo=slack&logoColor=white)](https://twitter.com/LatchBio/status/1527781165783867392)

<br />




<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table of Contents

- [I/O operations](#io-operations)
  - [Writing out stdout](#writing-out-stdout)
- [Contributors](#contributors)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---

### I/O operations

#### Writing out stdout

- **capturing stdout**
    - bioinformaticians are frequently captured the stdout using the `>` character from one software to feed into another. Use this code snippet for writing the stdout to a file and returning the output.
    - [snippet](snippets/capturing_stdout.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_codon_optimization)

<br />

- **handling multiple output files**
    - numerous software will generate multiple output files that have the same prefix
    - the best way to deal with this is by writing them all to a directory and then returning the resulting directory
    - [snippet](snippets/returning_a_directory_of_results.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_infer_phylogeny)

<br />

### Contributors
![Your Repository's Stats](https://contrib.rocks/image?repo=jlsteenwyk/latch_library)