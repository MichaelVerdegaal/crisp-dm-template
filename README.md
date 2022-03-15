# CRISP-DM Template

This repository contains a cookie-cutter Python repository for use with the CRISP-DM workflow. 
CRISP-DM is a data science workflow, meaning that it describes a process specific for 
executing data science projects. Such processes are becoming more necessary the more 
data science experiments you run, as they are messy and highly iterative in nature, and 
traditional software engineering workflows aren't always very practical to apply. 

While [the theory of the workflow](https://www.the-modeling-agency.com/crisp-dm.pdf) 
is described in wonderful detail, i found myself frustrated with the lack of practical examples 
online. The best one i found was from a project of 
[RyusukeKimura](https://github.com/RyusukeKimura/crisp-dm), but this is in Japanese, and so 
too hard to follow (technical lingo) for non-native speakers.  Due to this reasoning i decided to 
set up a template project that anyone can follow, inspired by the code layout as proposed in 
[this article](https://neptune.ai/blog/best-practices-for-data-science-project-workflows-and-file-organizations) 
from neptune.ai.

## This repository

This repository contains the following folders for you to use.

```text
crisp-dm-template
---data | datasets for your experiment
    ---raw | datasets as you've received them
    ---processed | datasets at the end of the data preparation stage
---docs | notebooks to write your CRISP-DM report
---source | will contain Python functions that are used to produce your report
```

Using the template is simple.

1. Fork the repository to create a new experiment
2. Set up a new virtual environment, and install the packages with `poetry install`, courtesy of 
the [poetry](https://python-poetry.org/) package manager.
3. Follow the steps in `docs`, with assistance from the source material of CRISP-DM, optionally 
writing code in `source` to help write your report.

## Notes

### What kind of functions should `source` contain?

This is best left up to personal interpretation, but a good generic rule is to move code to a new 
function in `source` if:
- You reuse a piece of code more than once
- A piece of code is considerably lengthy, and detracts from the reading experience in docs
- A piece of code requires extra documentation/context to be properly understood

### What if i need an extra file/folder?

An important consideration for this repository is that it's supposed to be flexible, it's a 
template in the end. As such, if your specific experiment requires say, an extra file in `source` 
to stay organised, then don't feel afraid to do so. 

**However**, it is important that these changes are made with consideration, for the sake of 
consistency. No one wants your experiments to have a different structure for every single 
experiment, as this makes it substantially harder to find the right information.




