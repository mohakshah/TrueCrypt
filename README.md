# TrueCrypt
[![CI Status](http://img.shields.io/travis/mohakshah/TrueCrypt.svg?style=flat)](https://travis-ci.org/mohakshah/TrueCrypt)

## About
This repo is an attempt to keep the last version of TrueCrypt (7.1a) buildable on modern versions of macOS.
Minor modifications to the TrueCrypt 7.1a source code have been made to add support for the following:
- wxWdigets 3.0
- Retina displays
- building a 64-bit version
- drives with sector size != 512 bytes
- homebrew for build dependencies

 Most of the work in this repo was done by [neurodroid](https://github.com/neurodroid/TrueCrypt).

## Building
### Installing the dependencies:
1. Install [homebrew](https://brew.sh). We'll be using it to install TrueCrypt's build-time dependencies.
````
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

````
2. Install pkgconfig, wxmac and nasm via brew:
````
brew install pkgconfig wxmac nasm
````
3. Install osxfuse via homebrew cask:
````
brew tap caskroom/cask
brew cask install osxfuse
````

### Building TrueCrypt:
- Run: `make -j4 -f Makefile.osx`
- On success, you should find `Truecrypt.app` under the 'Main/' directory.
- For more builing options, refer to Readme.txt

## Trusting this repo
I invite, even _insist_, you to audit the changes made in this repo to the TrueCrypt source before using building the code. [neurodroid](https://github.com/neurodroid/TrueCrypt) made sure to only make small, incremental changes between commits, making the audit process a breeze. I too have followed the suite while also signing my commits with my [GPG key](https://pgp.mit.edu/pks/lookup?op=vindex&search=0x774F42916CE22ED5). A good starting point should be [Commit f4633bd](https://github.com/mohakshah/TrueCrypt/commit/f4633bd8fea64bd4098050f03beff9aabe48840a), since it contains the _exact_ clone of the original TrueCrypt 7.1a source.
