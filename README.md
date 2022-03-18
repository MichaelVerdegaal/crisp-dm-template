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
    ---raw | datasets as you've orginally received them
    ---processed | datasets at the end of the data preparation stage
---docs | phased notebooks to write your CRISP-DM report in
---source | contains Python functions that are used to produce your report
```

Using the template is simple.

1. Fork or clone the repository to create a new experiment
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

### Why Python specific?

Python is by far the most popular language for data science purposes, which myriads of online sources could confirm. Due to the popularity and personal preferences the decision has been made to primarily tailor this template towards Python, however, just because this is the focus, that doesn't mean you can't use the template in another language. In case you want to switch programming languages, take these steps:

1. Remove poetry related files (poetry.lock and pyproject.toml).
2. Remove python files in `source`, and switch the file type to the desired language choice.
3. Add the steps necessary to reproduce the project environment in your language of choice.
4. Make sure to include any packages necessary to get the Jupyter Notebooks to run.

In case your language somehow doesn't support Jupyter Notebooks ([which is pretty difficult)](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels), then you'll have to do more manual labor. The notebooks are filled with markdown text, which you'll have to extract from the notebooks cells (text inside the `#%% md` blocks)to another suitable file format.

