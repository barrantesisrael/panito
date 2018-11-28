# pANIto
Calculate genome wide average nucleotide identity (gwANI) for a multiFASTA alignment.  

[![Build Status](https://travis-ci.org/sanger-pathogens/panito.svg?branch=master)](https://travis-ci.org/sanger-pathogens/panito)      
[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-brightgreen.svg)](https://github.com/sanger-pathogens/panito/blob/master/LICENSE)  

## Contents
  * [Introduction](#introduction)
  * [Installation](#installation)
    * [OSX/Linux \- from source](#osxlinux---from-source)
    * [OSX/Linux \- Homebrew](#osxlinux---homebrew)
  * [Usage](#usage)
    * [Input format](#input-format)
    * [Output](#output)
  * [License](#license)
  * [Feedback/Issues](#feedbackissues)
  * [Etymology](#etymology)

## Introduction
Given a multi-FASTA alignment, output the genome wide average nucleotide identity (gwANI) for each sample against all other samples. A matrix containing the percentages is outputted. This software loads the whole file into memory.

## Installation

### OSX/Linux - from source
Ensure you have a standard development environment installed (e.g. gcc, automake, autoconf, libtool). Download the software from GitHub and unzip.

```
autoreconf -i -f
./configure
make
sudo make install
```

### OSX/Linux - Homebrew
```
brew tap tseemann/bioinformatics-linux
brew install panito
```

## Usage
```
   $ panito
   Usage: panito [-hV] <file>
   This program calculates the genome wide ANI for a multiFASTA alignment.
    -h		this help message
    -V		print version and exit
    <file>		input alignment file which can optionally be gzipped
```

### Input format
The input file must be a multi-FASTA file, where all sequences are the same length:

```
   >sample1
   AAAAAAAAAA
   >sample2
   AAAAAAAAAC
   >sample3
   AAAAAAAACC
```

### Output
```
        sample1	    sample2	    sample3
sample1	100.000000	90.00000	80.000000
sample2	-			100.000000	90.000000
sample3	-			-			100.000000
```
## License
pANIto is free software, licensed under [GPLv3](https://raw.githubusercontent.com/sanger-pathogens/panito/master/LICENSE)

## Feedback/Issues
Please report any issues to the [Issues page](https://github.com/sanger-pathogens/panito/issues) or email path-help@sanger.ac.uk.

## Etymology
pANIto has 'ani' in the middle.  In Spanish it means babylon.
