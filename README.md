# conda-bld

conda(-forge) builds from staged-recipes - for packages not yet in official conda-forge repos.
AXC2 supported source format.

- gives you prefix aware distri independent binary packages
- packed within single files
- with a [well documented](https://conda.io/docs/user-guide/tasks/build-packages/environment-variables.html) build machinery

> Before you bite into this apple first check conda and conda-forge if your required package is already there, you have pretty good chances.

[This](http://wesmckinney.com/blog/conda-forge-centos-moment/) about conda.


# HowTo

## Get educatd on conda forge

https://github.com/conda-forge/staged-recipes

## Install conda and condabuild

say, into /xc

## Get this repo

```
cd /xc
git clone git@github.com:axiros/conda-bld
```

## Create a build recipe and build

e.g. for tinc

```
git clone git@github.com:axiros/staged-recipes.git
cd staged-recipes
cp -a example/gnutls tinc

<edit tinc/build.sh and tinc/meta.yml>

conda build tinc # creates the artifact within /xc/conda-bld/tinc....tar.bz2

```

## Test, Push

```
cd /xc/conda-bld
git add linux-64/tinc-...bz2 # only this
git commit -am 'inital build of a great vpn solution for containers'
git push
```







