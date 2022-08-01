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

- [Dockerfile snippets](#dockerfile-snippets)
  - [Installing packages and software](#installing-packages-and-software)
- [I/O operations](#io-operations)
  - [Writing out stdout](#writing-out-stdout)
- [Contributors](#contributors)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---

### Dockerfile snippets

#### Installing packages and software

- **Installing Miniconda**
  - Anaconda is an extremely useful open source package and environment management system
  - To install it from a `Dockerfile`, paste the instruction in the `installing_conda.txt` file inside your `Dockerfile`
  - The commands in the text execute the following tasks:
    - download and install `miniconda` in the indicated folder
    - add the conda binary to the `$PATH`
  - Conda can now be used normally (e.g `conda install samtools`)
  - [snippet](snippets/installing_conda.txt) | [example code](Coming soon)
  - Snippet by: [Matteo Bolner](https://github.com/matteobolner)

<br />

- **Installing from PyPi using a requirements.txt file**
  - Popular software used by bioinformaticians are distributed via PyPi and can easily be incorporated into LatchBio workflows.
  - To do so, create a `requirements.txt` that details the packages to download in the same directory as your `Dockerfile`. Next, add `COPY requirements.txt requirements.txt; RUN pip install -r requirements.txt` to your `Dockerfile`.
  - [snippet](snippets/installing_from_pypi.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_clipkit)
  - Snippet by: [Jacob L. Steenwyk](https://jlsteenwyk.com/)

<br />

- **Installing from PyPi without using a requirements.txt file**
  - Import the necessary subpackages (e.g. matplotlib, pylab, Bio) using the `Dockerfile` of in your workflow 
  - To do so, specifically add `RUN python3 -m pip install matplotlib pylab biopython` to your `Dockerfile`.
  - Snippet and example code coming soon!
  - [snippet](snippets/installing_from_pypi_alternative.txt) | [example code coming soon!]
  - Snippet by: [Pedro Lovatt Garcia](https://github.com/uniformelk1)

<br />

- **Download and compile software**
  - Software can be distributed in tar gzipped directories. The source code often needs to be compiled into binaries, which is often done by executing the command `make install`.
  - To handle these types of software in a `Dockerfile` for use in a Latch workflow, a series of commands can be strung together to automatically download and compile the workflow. The general steps are the same as when working in the terminal wherein the software is downloaded using something like `curl`, unzipped, and `make` commands are executed. 
  - [snippet](snippets/download_and_compile_software.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_infer_phylogeny)
  - Snippet by: [Jacob L. Steenwyk](https://github.com/JLSteenwyk)
 
<br />

- **Installing R**
  - `R` has proven to be a statistical workhorse for bioinformaticians. The following snippet details how to download and install `R` in your `Dockerfile`.
  - [snippet](snippets/installing_R_in_the_dockerfile.txt)
  - Snippet by: [Jacob L. Steenwyk](https://jlsteenwyk.com/)
  - Original author: [Akshay Suhuag](https://github.com/aa20g217) in the LatchBio SDK Slack channel.

<br />


- **Installing Java**
  - Numerous bioinformatic software is written in `Java`. Latch workflows that use `Java` require download and installation instructions for `Java` to be specified in the `Dockerfile`. Use this code snippet for downloading and installing `Java`.
  - [snippet](snippets/installing_java_in_the_dockerfile.txt)
  - Snippet by: [Jacob L. Steenwyk](https://jlsteenwyk.com/)
  - Original author: [Kenny Workman](https://github.com/kennyworkman) in the LatchBio SDK Slack channel.

<br />

### I/O operations

#### Writing out stdout

- **capturing stdout**
    - bioinformaticians are frequently captured the stdout using the `>` character from one software to feed into another. Use this code snippet for writing the stdout to a file and returning the output.
    - [snippet](snippets/capturing_stdout.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_codon_optimization)
    - Snippet by: [Jacob L. Steenwyk](https://jlsteenwyk.com/)

<br />

- **handling multiple output files**
    - numerous software will generate multiple output files that have the same prefix
    - the best way to deal with this is by writing them all to a directory and then returning the resulting directory
    - [snippet](snippets/returning_a_directory_of_results.txt) | [example code](https://github.com/JLSteenwyk/latch_wf_infer_phylogeny)
    - Snippet by: [Jacob L. Steenwyk](https://jlsteenwyk.com/)

<br />

- **Piping stdout to a different command**
    - Lots of command line tools only take input from the standard input stream, so pipes ("|") are necessary when composing lots of these tools together. Use this snippet for piping the output of one process to the input of another.
    - [snippet](snippets/piping_output_to_a_command.txt)
    - Snippet by: [Ayush Kamat](https://github.com/ayushkamat)

<br />

- **Returning one or a few files**
  - SDK developers may want to return only one or a few files out of many. In these cases, the shutil.move() or os.rename() functions may be useful.
  In this example, a specific output file is moved to a preferred directory. 
  - [snippet](snippets/capturing_single_file_output.txt) | [Example code](https://github.com/GeOdette/cutadapt.git)
  - Snippet by: [Geodette](https://github.com/GeOdette)
  - Explanation edited by: [Jacob L. Steenwyk](https://jlsteenwyk.com/)

### Contributors
![Your Repository's Stats](https://contrib.rocks/image?repo=jlsteenwyk/latch_library)
