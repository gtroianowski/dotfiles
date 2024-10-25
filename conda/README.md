A few notes on conda:

- (on mac) install via homebrew
- mamba is significantly faster than conda. Consider using the mamba solver instead of the conda one as detailed [there](https://www.anaconda.com/blog/a-faster-conda-for-a-growing-community)
```shell
# first, ensure the conda version is above 24.
$ conda install -n base "conda-libmamba-solver>=24"
$ conda config --set solver libmamba
```

Run this to install the environments from the yaml files (`conda create` will **not** read the name from the env file):
```shell
conda env create --file=<path-to-yaml-file>
```




