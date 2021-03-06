# Codebook fo Annotation of Near-Duplicate Status

This codebook explains the qualitative steps that have been taken with
respect to the detection of (near-)duplicates that are described
above. The coding was conducted by Sophie-Marie Himmler, Karolina Kohl
and Tim Griebel during February 2018. Please contact Tim for more
information about the de-duplication process.

## Definition of (near-)duplicates

"Two documents are regarded as duplicates if they comprise identical
document content. Documents that bear small dissimilarities and are
not identified as being 'exact duplicates' of each other but are
identical to a remarkable extent are known as near duplicates"
[Alsulami et
al. 2012](https://www.researchgate.net/publication/266005488_Near_Duplicate_Document_Detection_Survey)

Similarities in content concern the forms of texts on the linguistic
level, not on the argumentative or ideological level. The basic
question is: Does a pair of texts contain (basically) the same article
twice? We are not concerned here with the much broader question if a
pair of texts deals with the same topic or contains the same arguments
or ideologies although they do not show similarities in their
linguistic forms.

## Coding Rules with Regard to the Detection of Duplicates
1. Open the (near-)duplicate database and the excel file "Duplicate
   detection_manual_annotation".
2. Look at each pair of texts and decide if they contain a (near-)duplicate.
	1. If the pair does not contain a (near-)duplicate, both texts
	should be kept within the corpus. So, put an "x" into both columns
	"keep_A" "keep_B" in the excel file.
	2. If the pair does contain a (near-)duplicate, only one text
	should be kept within the corpus. Keep the longer article and put
	an "x" into the column of this text.
	3. Special rules for the Guardian for the steps 2 (i) and 2 (ii):
	    1. If a pair of (near)duplicates contains both printed and
		online content, keep always the text for the printed version
		2. Take care about the year that an article has been
		published. Do not keep articles that contain online content
		for the Guardian in the years 2010-2014. The marker here is
		"Guardian.com" in the meta data
3. Indicate any observation that might be interesting for the
   evaluation of the quality of the (near-)duplicate detection in the
   column "remark".
