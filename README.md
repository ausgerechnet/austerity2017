# Text and Images of Austerity in Britain: the Corpus

## Databasis
After removing duplicates that are due to download errors, we are left
with 23,688 published in 2010 or later for which we parse relevant
meta data from the text, namely the date, source (Telegraph or
Guardian), its journal code, the section, page, length (in words), and
its edition. In order to improve the quality of our corpus and its
metadata, we (1) process the meta variables and (2) remove duplicates
and further unwanted texts from the corpus, resulting in a final
corpus of 15,264 texts.

The following three meta variables are added:
1. a binary meta variable for the distinction between medium (online
   vs. print). We base this distinction on four easy rules: Firstly,
   articles published on guardian.com according to the text are
   "online"; secondly, all Telegraph articles are "print" (as a manual
   inspection shows); thirdly, all Guardian articles published after
   2014 are online content. Last but not least, articles that do not
   have any page number in text are classified as "online" (this is
   consistent with the first three rules).
2. We also add a dummy variable showing whether a given article
   contains an image whose caption contains the token "austerity" (323
   articles).
3. We introduce coarse-grained sections by means of collapsing the
   sections found in the text.

## Removal of unwanted online content
The removal of unwanted articles is slightly more complex. In a first
step, we remove any article that is easily identifiable as unwanted
online content: articles that contain "society daily" in the headline
(an online column that we are not interested in) and articles that
contain the tokens "cribsheet" or "block-time" in their body (obvious
markers for online blog content gained from qualitative inspection of
the articles); this procedure removes a total of 910 articles.

## Rule-based deduplication
We then proceed to perform a rule-based deduplication based on text
similarity. In a first step, we therefore perform pairwise comparisons
of all texts: For a given text A, we calculate the proportion of
tokens of A that appear in sentences which also appear in any other
text B of the corpus. (If A is totally contained in B, this value is
1, even if B is much longer than A.) Afterwards, we create a
stratified sample of text pairs with different similarity values and
interpret these qualitatively with regard to their (near-)duplicate
status in order to decide upon the cut-off value for the similarity
measure and to develop a more sophisticated decision rule for the
detection of duplicates with the help of the meta-data (see the
[Codebook](codebook.md)). We leave out duplicate-pairs in which one
article appears on page 1 and the other on a following page in the
same newspaper (since these "duplicated" articles represent teasers on
the front-page which we want to keep for qualitative reasons).

All other article-pairs with a (unilateral) similarity-score of 0.2 or
higher are processed as folows:
1. The articles are checked for their medium: if one of the articles
   is from a print medium and the other from an online medium, we
   remove the online articles (this removes 474 articles).
2. We check for editions: if one of the articles appears in an edition
   with a lower count (say, edition 1 compared to edition 3), the
   article of the later edition is being kept. Likewise, we remove any
   article in duplicate-pairs for which there exists a version of the
   'national' edition compared to local (Scottish, Irish)
   edition. This edition-wise deduplication removes a further 1,705
   articles.
3. We build transitive clusters of duplicates (i.e. we include any
   article in a given cluster that shows a similarity score of at
   least 0.2 to some other article in the cluster) and chose articles
   based on two simple rules: (a) We keep articles with images and (b)
   we remove any but the longest article (based on the number of
   tokens) of each cluster. This last rule removes 2,244 articles.

## Removal of further on-line articles
For the purpose of making the two newspaper subcorpora comparable, we
remove further articles published on-line by the Guardian: Since we do
not have any on-line content in the Telegraph subcorpus, we remove any
remaining on-line content for the Guardian for the time period in
which there are also printed articles available. This holds for all
years up until the end of 2014; after that LexisNexis only provided
on-line content for the Guardian. We thus removed all on-line content
published before December 31, 2014, amounting to 3,089.

**Disclaimer**: In fact, there is no print content for the Guardian
starting _November_ 2014, meaning that we mistakenly removed _all_
articles of the Guardian for November and December 2014; we thus
removed 194 articles too many.

## Summary
The whole corpus preparation thus reduced the number of articles in
the corpus from 24,743 that have been downloaded from LexisNexis to
15,264 (including 289 multimodal articles).

| original download        | 24,743     |
|--------------------------|------------|
| download errors          | 1,057      |
| unwanted on-line content | 910        |
| on-line and print        | 474        |
| several editions         | 1,705      |
| transitive clusters      | 2,244      |
| further on-line content  | 3,089      |
| **final corpus**         | **15,264** |
