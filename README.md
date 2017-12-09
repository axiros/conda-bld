# conda-bld

conda(-forge) builds from staged-recipes - for packages not yet in official conda-forge repos.
AXC2 supported source format.

- gives you prefix aware distri independent binary packages
- packed within single files
- with a [well documented](https://conda.io/docs/user-guide/tasks/build-packages/environment-variables.html) build machinery

> Before you bite into this apple first check conda and conda-forge if your required package is already there, you have pretty good chances.

[This](http://wesmckinney.com/blog/conda-forge-centos-moment/) about conda.


# HowTo

## Get educated on conda forge

https://github.com/conda-forge/staged-recipes

## Install conda and condabuild

say, into /xc

## Get this repo

```
cd /xc
git clone git@github.com:axiros/conda-bld
```

## 

```bash
conda install conda-build jinja
yum groupinstall 'Development Tools'
```

## Create a build recipe and build

e.g. for tinc I did:

```
cd /root/
git clone git@github.com:axiros/staged-recipes.git
cd staged-recipes
cp -a example/gnutls tinc

<edit tinc/build.sh and tinc/meta.yml>

# add deps, see below
conda build tinc # creates the artifact within /xc/conda-bld/tinc....tar.bz2

```

### Handling Dependencies

tinc required openssl, ncurses lzo... 

I had no luck marking those as build and/or run dependencies, have to investigate.

So I took them from the host package mgr for now (yum install zlib-devel ....)




## Test, Push

```
cd /xc/conda-bld
git add linux-64/tinc-...bz2 # only this
git commit -am 'inital build of a great vpn solution for containers'
git push
```







