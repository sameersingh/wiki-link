# [Wikilinks Data](http://www.iesl.cs.umass.edu/data/wiki-links) #

The project includes code for the following:

## Google Data ##

Package: edu.umass.iesl.cs.wikilinks.google

Support for directly reading and analyzing the basic Wikilinks dataset as provided by Google.
Instructions on obtaining the dataset are available [here](http://www.iesl.cs.umass.edu/data/wiki-links) and [here](http://googleresearch.blogspot.com/2013/03/learning-from-big-data-40-million.html).

Please see the [Wiki](https://code.google.com/p/wiki-link/wiki/GoogleDataset) for details.

## Expanded Data ##

Package: edu.umass.iesl.cs.wikilinks.expanded

Further, UMass has released an expanded version of the same dataset containing the complete websites, their cleaned HTML, and extracted context for each mention.

Please see the [Wiki](https://code.google.com/p/wiki-link/wiki/ExpandedDataset) for details.

## Dataset creation ##

The code used to create the expanded dataset is also included as a combination of shell scripts and Scala code.

Please see the [Wiki](https://code.google.com/p/wiki-link/wiki/DatasetCreation) for details.

# Usage #

The approaches described below assume that you don't want to check out the repository and download the code. To build the code yourself, check out the repository, cd to `process`, run `mvn install`, and use the Maven dependency as described below.

## Maven ##

In your `pom.xml`, include the following:

```
<repositories>
    ...
    <repository>
      <id>iesl.cs.umass.edu</id>
      <name>IESL release repository</name>
      <url>https://dev-iesl.cs.umass.edu/nexus/content/repositories/releases/</url>
    </repository>
    <repository>
      <id>snapshot.iesl.cs.umass.edu</id>
      <name>IESL snapshot repository</name>
      <url>https://dev-iesl.cs.umass.edu/nexus/content/repositories/snapshots/</url>
    </repository>
    ...
</repositories>
...
<dependencies>
    <dependency>
      <groupId>edu.umass.cs.iesl.wikilink</groupId>
      <artifactId>wikilink</artifactId>
      <version>0.1-SNAPSHOT</version>
    </dependency>
</dependencies>
```

## Jar ##

In the [Downloads](https://code.google.com/p/wiki-link/downloads/list) section, we have included the jar with all the dependencies that you can include in your classpath.


### Authors ###

This library is maintained by [Sameer Singh](http://sameersingh.org), with contributions from [Brian Martin](http://www.cs.umass.edu/~martin/) and [Harshal Pandya](http://harshalgem.wordpress.com/).