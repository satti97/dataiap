# Introduction

Before we can start playing with data, let's set up our environment.
We'll install some software, packages, and downlaod some datasets to
get started!

## Prereqs

We assume you have a working knowledge of python (6.01) and are
willing to write code.  Most of the code you interact with will come
with an example that you can modify.  Hopefully little specialized
code will be generated except for programs you're inspired to write!

## What we will teach

We will teach the basics of data analysis through concrete examples.
All of your programming will be written in python.  The schedule is as follows:

* Day 0 (today): setup

* Day 1: An end-to-end example getting you from a
  dataset found online to several plots of campaign contributions.

* Day 2: Lots of visualization examples, and practice going from data
  to chart.

* Day 3: Statistics basics, including T-Tests, Linear Regression, and
  statistical significance.  We'll use campaign finance and per-county
  health rankings.

* Day 4: Text processing on a large text corpus (the Enron email
  dataset) using tf-idf and cosine similarity.

* Day 5: Scaling up to process large datasets using Hadoop/MapReduce
  on a larger copy of the Enron dataset.

* Day 6: You tell us!  Get into groups or work on your own to analyze
  a dataset of your choosing, and tell us a story!

## What we will not teach

* *R*.  R is a wonderful data analysis, statistics, and plotting
framework.  We will not be using it because we can achieve all of our
objectives in Python, and more MIT undergraduates know Python.

* Visualization using browser technology (canvas, svg, d3, etc) or in
  non python languages ([Processing](http://processing.org/).  These
  tools are very interesting, and lots of visualizations on the web
  use these tools (e.g., [nytimes
  visualizations](http://open.blogs.nytimes.com/2008/10/27/the-new-york-times-data-visualization-lab/)),
  however they are out of the scope of this class.  We'll teach you
  how to visualize data in static charts.  If this is an area of
  interest for you, the next step will be to build interactive
  visualizations that the world can explore, and we can point you in
  the right direction with these.

## Programming Environment

We assume that you are developing in a unix-like environment and are
familiar with the common commands.  If you are a windows user, we
assume you are using cygwin.

## Tools and Libraries 

In this class, you will need to install a number of tools.  The major
ones are:

* [python 2.7](http://www.python.org/getit/releases/2.7/)
	* Python is
  usually installed in Mac OSX and major unix distributions.  Type
  `python --version` to make sure it is the right version
* [easy_install](http://pypi.python.org/pypi/setuptools#files)
	* python package manager.
* [pip](http://pypi.python.org/pypi/pip#downloads)
	* Makes installing python packages really easy.  Requires easy_install
* [git](http://git-scm.com/)
    * git is a version control system.  Using it, you can check out our code and examples.
    * If everything is working, check the dataiap sourcecode into a
      directory called `dataiap` using `git clone
      https://github.com/dataiap/dataiap.git dataiap`

We will also require a number of python modules:

- [numpy 1.6.x](http://sourceforge.net/projects/numpy/files/NumPy/1.6.1/)
	* PIP users can type `sudo pip install numpy`
- [scipy 0.10](http://sourceforge.net/projects/scipy/files/scipy/0.10.0/)
	* PIP users can type `sudo pip install scipy`
    * Ubuntu users can type `sudo apt-get install python-scipy`
	* Unfortunately, scipy installation might not work from PIP, and you may have to [compile it from source](https://scipy.org/Installing_SciPy/Mac_OS_X) (see "Obtaining and Building NumPy and SciPy").  Try something akin to
      > git clone https://github.com/scipy/scipy.git  
      > cd scipy  
      > python setup.py build  
      > python setup.py install  
- [matplotlib 1.1.0](http://sourceforge.net/projects/matplotlib/files/matplotlib/matplotlib-1.1.0/)
    * PIP users can type `sudo pip install matplotlib`
    * Note: If compiling from source, matplot lib requires a number of other libraries: 
    ([libpng](http://www.libpng.org/pub/png/libpng.html), [freetype 2](http://download.savannah.gnu.org/releases/freetype/))
- [mrjob](https://github.com/yelp/mrjob)
	* MapReduce package.  We will use it in day 5.
	* PIP users can type `sudo pip install mrjob`
	* If compiling from source, it requires [boto](http://code.google.com/p/boto/downloads/list) (try `sudo pip install boto`).


## Datasets

We will be working with several datasets in this course.  Some are fairly large, so we ask that you download them before the class,

* [2008 Presidential Campaign Contributions](ftp://ftp.fec.gov/FEC/Presidential_Map/2008/P00000001/P00000001-ALL.zip)
    * The linked file contains all of the 2008 campaign contributions to each presidential candidate.  You can look at the [2012 campaign](http://fec.gov/disclosurep/PDownload.do) for various primary candidates as well, but we'll work with 2008 since it's complete.
): click "All.zip" and unzip the file
* [2011 County Health Rankings](http://www.countyhealthrankings.org/): The necessary data should already be in the git repository you cloned in   
> `dataiap/datasets/county_health_rankings/additional_measures_cleaned.csv`  
> `dataiap/datasets/county_health_rankings/ypll.csv`  
* The Enron dataset: $$$