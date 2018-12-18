# Windows CI/CD Systems

[![build status](https://travis-ci.org/SashaNullptr/WindowsCICD.svg?branch=master)](https://travis-ci.org/SashaNullptr/WindowsCICD)

## What is this Guide?

A (highly opinionated) overview of how to set up a CI/CD System for Windows systems.

## Automatic Builds

This project is automatically re-built each time a commit is made to master. The
most recent passing build will update the GitHub Pages
[site for this project](https://sashanullptr.github.io/WindowsCICD/).

## Building Manually

If you want to build this project by hand instead of viewing the
[project site](https://sashanullptr.github.io/WindowsCICD/)
(for some reason) here are the steps you'll need to take.

### Things You'll Need

* MkDocs
* Cinder Theme for MkDocs

Assuming you have [Chocolatey](https://chocolatey.org/) installed, the following PowerShell script should install all required pre-requistes.

```shell
choco install -y python3
choco install -y mkdocs
python -m pip install mkdocs-cinder
```
You may also need to add the `C:\Python37\Scripts` folder to the PATH in order for MkDocs to be usable from the command line.

```shell
env:Path = "C:\Python37\Scripts";
```

### Building

Simply run `mkdoc build` from the project route--this will build the project
and place the results in a directory named `site`.
