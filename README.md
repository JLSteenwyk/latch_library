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

### Dockerfile snippets

#### Installing packages from pypi

- **Installing from PyPi**
  - Popular software used by bioinformaticians are distributed via PyPi and can easily be incorporated into LatchBio workflows.
  - To do so, create a `requirements.txt` that details the packages to download in the same directory as your `Dockerfile`. Next, add `COPY requirements.txt requirements.txt; RUN pip install -r requirements.txt` to your `Dockerfile`.
  - [snippet](snippets/installing_from_pypi.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_clipkit)
  - Snippet by: [Jacob L. Steenwyk](https://github.com/JLSteenwyk)

- **Download and compile software**
  - Software can be distributed in tar gzipped directories. The source code often needs to be compiled into binaries, which is often done by executing the command `make install`.
  - To handle these types of software in a `Dockerfile` for use in a Latch workflow, a series of commands can be strung together to automatically download and compile the workflow. The general steps are the same as when working in the terminal wherein the software is downloaded using something like `curl`, unzipped, and `make` commands are executed. 
  - [snippet](snippets/download_and_compile_software.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_infer_phylogeny)
  - Snippet by: [Jacob L. Steenwyk](https://github.com/JLSteenwyk)
 

### I/O operations

#### Writing out stdout

- **capturing stdout**
    - bioinformaticians are frequently captured the stdout using the `>` character from one software to feed into another. Use this code snippet for writing the stdout to a file and returning the output.
    - [snippet](snippets/capturing_stdout.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_codon_optimization)
    - Snippet by: [Jacob L. Steenwyk](https://github.com/JLSteenwyk)

<br />

- **handling multiple output files**
    - numerous software will generate multiple output files that have the same prefix
    - the best way to deal with this is by writing them all to a directory and then returning the resulting directory
    - [snippet](snippets/returning_a_directory_of_results.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_infer_phylogeny)
    - Snippet by: [Jacob L. Steenwyk](https://github.com/JLSteenwyk)

<br />

### Contributors
![Your Repository's Stats](https://contrib.rocks/image?repo=jlsteenwyk/latch_library)