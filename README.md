# Shovill
Faster smarter SPAdes assembly of Illumina reads

## Introduction

The SPAdes genome assembler has become the *de facto* standard *de novo* genome assembler
for Illumina whole genome sequencing data of bacteria and other small microbes. SPAdes
was a major improvement over previous assemblers like Velvet, but it can be very slow to run
and does not handle overlapping paired-end reads well.

Shovill is a pipeline which uses SPAdes at its core, but alters the steps before and after
the primary assembly step to get near-identical results in far less time.  

## Main steps

1. Estimate genome size and read length distribution from reads (SOON)
2. Correct reads conservatively
2. Pre-overlap paired-end reads
3. Assemble with "vanilla" SPAdes with modified kmer range and PE + long SE reads
5. Use contigs not scaffolds
4. Correct minor assembly errors (SOON)

## Installation

### Homebrew

```
brew tap homebrew/science
brew tap tseemann/bioinformatics-linux
brew install shovill
```
Using Homebrew will install all the dependencies for you: 
[Linux](http://linuxbrew.sh) or [MacOS](http://brew.sh)

### Source

```
git clone https://github.com/tseemann/shovill.git
./shovill/shovill -h
```
You will need to install all the dependencies manually:
* SPAdes
* Lighter
* FLASH
* SAMtools >= 1.3
* BWA MEM
* PILON
* KmerStream
* seqtk
* datamash
* Java

## Feedback

Please file questions, bugs or ideas to the [Issue Tracker](https://github.com/tseemann/shovill/issues)

## License

[GPLv3](https://raw.githubusercontent.com/tseemann/shovill/master/LICENSE)

## Citation

Not published yet.

## Authors

* *Torsten Seemann*
* Jason Kwong
* Anders Goncalves da Silva
* Mark Schultz
* Dieter Bulach
