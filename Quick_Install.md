# Install OPAM in 2 minutes

This page describes how to install and configure OPAM.
For further help on how to use OPAM, either read
`opam --help` or move on to the [Basic Usage](Basic_Usage.html) guide.

## Installing OPAM with your distribution

You can use the OPAM package of your distribution if
available. Here is a list of supported distributions:

#### Archlinux

The [opam](http://aur.archlinux.org/packages.php?ID=62127) and [opam-git](http://aur.archlinux.org/packages.php?ID=62387) packages are available in the [AUR](https://wiki.archlinux.org/index.php/AUR). Replace `opam` with `opam-git` in the following instruction to get the development version:

```
  yaourt -S opam
```

#### Debian

Binary packages of OPAM 1.1.1 are available for the [testing](http://packages.debian.org/jessie/opam) and [unstable](http://packages.debian.org/sid/opam) distributions.  Wheezy users are left with the options of compiling from source, pinning the packages from the testing repository, requesting a backport from Debian, or using our binary installer below.

#### [Exherbo](http://exherbo.org)

Simply install the [`dev-ocaml/opam`](http://git.exherbo.org/summer/packages/dev-ocaml/opam/index.html) package: `cave resolve -x dev-opam/ocaml`.  
You might need to add the `::ocaml-unofficial` repository first: `cave resolve -x repository/ocaml-unofficial`.

#### Mageia

The opam package for Mageia can be installed with the command:

```
  urpmi opam
```

#### OSX

OPAM packages for [homebrew](http://mxcl.github.com/homebrew/) and [MacPorts](http://www.macports.org/) are available:

```
  brew install opam                   # using Homebrew on OSX Mavericks
  brew install opam --without-aspcud  # using Homebrew on OSX Mountain Lion (or lower)
  port install opam                   # using MacPort
```

See also [howto setup Emacs.app](https://github.com/ocaml/opam/wiki/Setup-Emacs.app-on-macosx-for-opam-usage) for opam usage.

#### Ubuntu (Precise, Quantal, Raring and Saucy)

```
  add-apt-repository ppa:avsm/ppa
  apt-get update
  apt-get install ocaml opam
```

There are also PPAs available that are [pinned to specific revisions](http://launchpad.net/~avsm) of OCaml and OPAM to help with [automated testing](http://anil.recoil.org/2013/09/30/travis-and-ocaml.html).

#### Ubuntu Trusty LTS

OCaml 4.01.0 and OPAM 1.1.1 are included in Ubuntu Trusty's `universe` repository, so just install them as normal.

```
  apt-get update
  apt-get install ocaml ocaml-native-compilers camlp4-extra opam
```

## Binary installer

Pre-compiled versions for most common architectures and OSes are available on [the Github "releases" page](https://github.com/ocaml/opam/releases/latest). We also provide a very simple installer script that will automatically download the right version for you, put it in your binary directory and initialize it.

```
  wget https://raw.github.com/ocaml/opam/master/shell/opam_installer.sh
  sh ./opam_installer.sh /usr/local/bin
```

You can also specify which version of OCaml you want to install:

```
  sh ./opam_installer.sh /usr/local/bin 3.12.1 # Install the latest OPAM and OCaml 3.12.1
  sh ./opam_installer.sh /usr/local/bin system # Install the latest OPAM using the system compiler (if any)
```

## From Sources

#### Getting the Sources

Sources of the latest stable version of OPAM are available on [Github](https://github.com/ocaml/opam/releases). You can also download the full archives, including OPAM dependencies:

* [1.1.1](https://github.com/ocaml/opam/releases/download/1.1.1/opam-full-1.1.1.tar.gz) MD5 (opam-full-1.1.1.tar.gz) = a7bebe947b3e6c1c10ccafabb839d374
* [1.1.0](http://www.ocamlpro.com/pub/opam-full-1.1.0.tar.gz) MD5 (opam-full-1.1.0.tar.gz) = d6e2f56b10c0be73b5677963e6659d24

Once the archive downloaded and extracted, you can then run the usual commands:

```
./configure && make && make install
```

See [Advanced Install](Advanced_Install.html) guide for more information.

#### Using ocamlbrew

[ocamlbrew](https://github.com/hcarty/ocamlbrew) is a script that can bootstrap an OCaml environment including OPAM, from source.  This option does not require an existing OCaml installation, or a pre-compiled OPAM binary for your platform.  To bootstrap a new OCaml environment including OPAM, make sure that you have the necessary pre-requisites installed to run ocamlbrew, and then run:

```
curl -kL https://raw.github.com/hcarty/ocamlbrew/master/ocamlbrew-install | env OCAMLBREW_FLAGS="-r" bash
```
