# conda-bld

conda-forge builds from staged-recipes

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







