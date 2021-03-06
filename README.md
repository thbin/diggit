# Diggit [![Build Status](https://travis-ci.org/jrfaller/diggit.svg?branch=master)](https://travis-ci.org/jrfaller/diggit) [![Coverage Status](https://coveralls.io/repos/jrfaller/diggit/badge.svg?branch=master)](https://coveralls.io/r/jrfaller/diggit?branch=master) [![Inline docs](http://inch-ci.org/github/jrfaller/diggit.svg?branch=master)](http://inch-ci.org/github/jrfaller/diggit) [![Dependency Status](https://gemnasium.com/jrfaller/diggit.svg)](https://gemnasium.com/jrfaller/diggit)

A ruby tool to analyze Git repositories

# Installation

## From a gem

Just run `gem install diggit`.

## From the source

Clone diggit using the following command: `git clone https://github.com/jrfaller/diggit.git`. The `dgit` tool is in the `bin` folder.

# Usage

Don't forget that dgit binary has an associated help that can be consulted using `dgit help`.

## Configuration

The diggit tool is designed to help you analyze software repositories. Firstly you have to create a new folder in which you launch the `dgit init` command. This way, the folder becomes a diggit folder in which you can configure repositories and analyses.

### Setting-up the repositories

You can add some repositories to be analyzed with the following command: `dgit sources add https://github.com/jrfaller/diggit.git`.

### Using addons

Addons add features the the diggit tool: for instance capability of writing to a MongoDB database, etc. To enable addons for your current diggit folder you can use the following command: `dgit addons add TestAddon`.

### Setting-up analyses

An analysis is applied to each repository. You can configure the analyses to be performed with the following command: `dgit analyses add TestAnalysis`. Analyses are performed in the order they have been added.

### Setting-up joins

A join is performed after all analyses of all repositories have been performed. You can configure the joins to be performed with the following command: `dgit joins add TestJoin`. Joins are performed in the order they have been added.

## Running analyses

Once diggit is configured you can perform the analyses. First, you have to clone the repositories by using `dgit clones perform`. Then you can launch the analyses by using `dgit analyses perform`. Finally, the joins are executed via the command `dgit joins perform`. You can use the `mode` option to handle the cleaning of joins or analyses.

At all time, you can check the status of your diggit folder by using `dgit status`.
