Instructions relevant to traversing and analyzing the original dataset as distributed by Google. Note that Google format is quite straightforward to use yourself, as described in https://web.cs.umass.edu/publication/docs/2012/UM-CS-2012-015.pdf.

# Introduction #

The Scala code is available in process/ under the edu.umass.cs.iesl.wikilnks.google package. It consists of the following relevant classes:

  * `Mention`/`Webpage`: basic data structures for representing the Google dataset
  * `MentionIterator`/`WebpageIterator`: given the directory where the Google data files have been downloaded
  * `Baselines`: coreference baselines that are included in the tech report

# Examples #

`edu.umass.cs.iesl.wikilnks.google.analysis.Stats` contains an example of going through all Mentions and Webpages, and computing simple statistics on them. For other examples, see `Baselines` and `WebpageIteratorRunner`.