# Instructions on how the expanded dataset was created.

# Introduction #

**Note:** This sections is currently unfinished. We will include detailed instructions on how the expanded dataset was created. Meanwhile, feel free to browse the code and figure it out yourself :)

# Details #

The dataset with context is produced in several stages.  At the moment this includes: retrieval and processing.

## Retrieval ##

> Download the webpages that are referred to in the Google Dataset

> To retrieve the webpages:

> > cd retrieve/; ./retrieve.sh /path/to/original/wiki-link-data

> This will result in several new files in retrieve/:
> > - wiki-link-urls.dat -- a file consisting of one URL per line which was used by retrieve.sh
> > - logs/ -- the output of wget for each downloaded file
> > - pages/ -- the files which were downloaded
> > > - 000000/
> > > > - 0
> > > > - 1
> > > > - 2
> > > > - ...

> > > - 000001/
> > > > - ...

> > > - ....

## Processing ##

Extract HTML structure and context from the downloaded webpages, and store as thrift files.


> To process the downloaded files:

> > cd process/; mvn scala:run