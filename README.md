# Algorithms

## Structure and Organization of the Repo

This project uses [Jupyter Book](https://jupyterbook.org/) to organize a collection of
Jupyter Notebooks into a website.

- The notebooks all live in the [notebooks]() directory.
  Note that the notebooks are stored in "stripped" form, without any outputs of execution saved.
  (They are executed as part of the build process.)
- The table of contents is located in [\_toc.yml]().
- The book configuration is in [\_config.yml]().
- The references are in [\_references.bib]().

## The Environment

The environment in which to run the notebooks and build the books is defined in
[environment.yaml]().
To recreate and activate the environment locally, run

```
conda env create -f environment.yaml
conda activate cs
```

## Building the Book

To build the book locally, you should first create and activate your environment,
as described above. Then run

```
jupyter book build .
```

To speed up the continuous integration, we also generated a
[conda lock](https://conda.github.io/conda-lock/) file for linux as follows.

```
conda-lock lock --mamba -f environment.yaml -p linux-64 --kind explicit
```

This file lives in [conda-linux-64.lock](https://github.com/m2lines/L96_demo/blob/main/conda-linux-64.lock).
It should be regenerated periorically.

When you run this command, the notebooks will be executed.
The built html will be placed in '\_build/html`.
To preview the book, run

```
cd _build/html
python -m http.server
```

The build process can take a long time, so we have configured the setup to use
[jupyter-cache](https://jupyter-cache.readthedocs.io/en/latest/).
If you re-run the `build` command, it will only re-execute notebooks
that have been changed. The cache files live in `_build/.jupyter_cache`

To check the status of the cache, run

```
jcache cache list -p _build/.jupyter_cache
```

To remove cached notebooks, run

```
jcache cache remove -p _build/.jupyter_cache
```

## Contributing

### Pre-commit

We use [pre-commit](https://pre-commit.com/) to keep the notebooks clean.
In order to use pre-commit, run the following command in the repo top-level directory:
The pre commit

```
pre-commit install
```

At this point, pre-commit will automatically be run every time you make a commit.

### Pull Requests and Feature Branches

In order to contribute a PR, you should start from a new feature branch.

```
git checkout -b my_new_feature
```

(Replace `my_new_feature` with a descriptive name of the feature you're working on.)

Make your changes and then make a new commit:

```
git add changed_file_1.ipynb changed_file_2.ipynb
git commit -m "message about my new feature"
```

You can also automatically commit changes to existing files as:

```
git commit -am "message about my new feature"
```

Then push your changes to your remote on GitHub (usually call `origin`

```
git push origin my_new_feature
```

Then navigate to https://github.com/compressed-sensing/algorithms to open your pull request.

### Synchronizing from upstream

To synchronize your local branch with upstream changes, first make sure you have the upstream remote configured.
To check your remotes, run

```
% git remote -v
origin	git@github.com:compressed-sensing/algorithms.git (fetch)
origin	git@github.com:compressed-sensing/algorithms.git (push)
upstream	git@github.com:compressed-sensing/algorithms.git (fetch)
upstream	git@github.com:compressed-sensing/algorithms.git (push)
```

If you don't have `upstream`, you need to add it as follows

```
git remote add upstream git@github.com:compressed-sensing/algorithms.git
```

Then, make sure you are on the main branch locally:

```
git checkout main
```

And then run

```
git fetch upstream
git merge upstream/main
```

Ideally you will not have any merge conflicts.
You are now ready to make a new feature branch.

## References
This repository is built based on [L96_demo](https://github.com/m2lines/L96_demo).
