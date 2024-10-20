# CRISP-DM Template

This repository contains a cookie-cutter Python repository for use with the CRISP-DM workflow.
CRISP-DM is a data science workflow, meaning that it describes a process specific for executing data
science projects. Such processes are becoming more necessary the more data science experiments you
run, as they are messy and highly iterative in nature, and traditional software engineering
workflows aren't always very practical to apply.

Why use this template?

- Easy to follow along -
  [The theory of the workflow](https://www.kde.cs.uni-kassel.de/wp-content/uploads/lehre/ws2012-13/kdd/files/CRISPWP-0800.pdf)
  is described in wonderful detail, but there's a complete lack of practical examples on how to use
  it.
- Inline reporting - Instead of writing your report in say a Word document, you can write it inside
  a Jupyter notebook! This makes the process much easier to follow. You'll have to perhaps take a
  bit more care formatting your cell output, but this is still preferable over putting together a
  document from fragments of code, results and text.
- Best practices - This report was structured based on some common best practices. It's based on
  [this article from neptune.ai](https://neptune.ai/blog/best-practices-for-data-science-project-workflows-and-file-organizations),
  and uses Poetry as the main package manager.

## This repository

This repository contains the following folders for you to use.

```text
crisp-dm-template
---data | datasets for your experiment
    ---raw | datasets as you've orginally received them
    ---interim | datasets that are transformed, but not ready for modeling yet 
    ---processed | datasets at the end of your data preparation, ready for modeling
---docs | phased notebooks to write your CRISP-DM report in
```

Using the template is simple.

1. Fork or clone the repository to create a new experiment
2. Set up a new virtual environment, and install the packages with `poetry install`, courtesy of the
   [poetry](https://python-poetry.org/) package manager.
3. Follow the steps in `docs`, with assistance from the source material of CRISP-DM.

## Notes

### What if i need an extra file/folder?

This repository is supposed to be flexible, it's a template in the end. As such, if your specific
experiment requires say, some extra files or folders to stay organised, then don't feel afraid to do
so. A common example might be adding a `source` folder for code that is better suited for a separate
Python file, if it's too large or very reusable for example.

**However**, make these changes are made with consideration, for the sake of consistency. No one
wants everyone single experiment of yours to be structured differently, as this makes it
substantially harder to find the right information.

### Switching to another language

Python is by far the most popular language for data science purposes, which is why i used this as
the basis for this template. If you want to switch Programming language, this should be relatively
simple, provided your language supports
[Jupyter notebooks](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels).

1. Remove poetry related files (poetry.lock and pyproject.toml).
2. Switch to your preferred programming language.
3. Add the steps necessary to reproduce the project environment in your language of choice.
4. Make sure you can run
