# Expanded Dataset #

Instructions to obtain the expanded dataset are available here.

The expanded dataset contains the following extra information over the Google dataset:

  * Mention contexts
  * Freebase Id: Along with the Wikipedia URL, an ID to the Freebase page is also provided
  * Downloaded webpage: Missing for the context-only version of the dataset
  * Cleaned DOM structure of the HTML: Missing for the context-only version of the dataset

# Download #

The expanded dataset is available in different versions.

## Dataset with Context ##

The smallest version that contains the context and the freebase id is ~5GB in size. You can directly download the files from [here](http://iesl.cs.umass.edu/downloads/wiki-link/context-only/) or use the following script (run in an empty directory):
```rb

for (( i=1; i<110; i++)) do echo "Downloading file $i of 109"; f=`printf "%03d" $i` ; wget http://iesl.cs.umass.edu/downloads/wiki-link/context-only/$f.gz ; done ; echo "Downloaded all files, verifying MD5 checksums (might take some time)" ; diff --brief <(wget -q -O - http://iesl.cs.umass.edu/downloads/wiki-link/context-only/md5sum) <(md5sum *.gz) ; if [ $? -eq 1 ] ; then echo "ERROR: Download incorrect\!" ; else echo "Download correct" ; fi```

These data files follow the thrift format for the expanded dataset, with `PageContentItem` fields emptied out.

## Dataset with complete webpages ##

This version is currently under construction, and should be available in a few days.

# Data Format #

The data file have been encoded using [Apache thrift](http://thrift.apache.org/) and compressed using gzip. Instructions on how to use thrift for a number of languages is available [here](http://thrift.apache.org/tutorial/).

The thrift description file for the dataset is in `process/src/main/thrift` or https://code.google.com/p/wiki-link/source/browse/process/src/main/thrift/wiki-link-v0.1.thrift.

# Scala code #

For Scala, the process/ directory in this repository contains the code for iterating through all the datafiles. Once you have downloaded the expanded dataset file, you can use the `WikiItemIterator` in `edu.umass.cs.iesl.wikilinks.expanded` to iterate through the dataset. See the above thrift files on what is available in each `WikiLinkItem`.

For an example that counts the number of mentions and pages, run:

`mvn scala:run -Dlauncher=expanded-iterator -DaddArgs="/path/to/expanded/data/directory/"`