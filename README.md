# Summary

The SSJ treebank is the reference UD treebank for Slovenian, consisting of approximately 13,000 sentences and 267,097 tokens from fiction, non-fiction, periodical and Wikipedia texts in standard modern Slovenian. As of UD release 2.10 in May 2022, the original version of the SSJ UD treebank has been partially manually revised and extended with new manually annotated data. 

# Introduction

The original Slovenian SSJ UD Treebank, first released as part of UD v1.2 in 2015 (Dobrovoljc et al. 2017), was created through a fine-grained rule-based conversion of the ssj500k treebank (Krek et al. 2021), the largest collection of manually syntactically annotated data in Slovenian, originally annotated in the JOS annotation scheme (Erjavec et al. 2010). With the exception of the manual disambiguation of the AUX and VERB occurrences of the verb 'biti' (to be), the conversion was fully automatic, based on a set of rules for both morphosyntactic and syntactic layer, which include different lexical, morphological and dependency features, while the original ssj500k tokenization and lemmatization principles remained unchanged. The rules and conversion scripts are available at https://github.com/clarinsi/jos2ud.

In 2022, the original SSJ UD treebank was partially manually revised to correct the previously identified annotation inconsistencies, and implement the newly introduced changes in the annotation guidelines. In addition, the treebank was substantially extended to almost double the original size, with new manually annotated sentences coming from the previously unreleased subset of the ssj500k corpus, and the Slovenian subset of the ELEXIS parallel sense-annotated corpus of Wikipedia texts (Martelli et al. 2021). Despite the extension, the data split remained unchanged with the original SSJ sentences being preserved as part of the same train-dev-test subset. More details on the latest SSJ UD version are given in Dobrovoljc and Ljubešić (2022).

The metadata for most documents in the treebank includes also the document genre. The documents fall into six different genre categories: newspaper, magazine, internet, professional, fiction, other.

The *issues* section of this repository serves as a platform for general discussion regarding suggestions for the Slovenian UD guidelines and other open issues.

# Acknowledgments

We wish to thank all of the contributors to the original ssj500k training corpus (Kristina Bizjak, Živa Blaževič, Klara Canzutti, Lea Cibrič, Kaja Dobrovoljc, Tadeja Dušej, Tomaž Erjavec, Ivana Fekeža, Nanika Holz, Urška Kamenšek, Simon Krek, Andreja Košir, Robert Kuret, Nina Ledinek, Andrej Lovšin, Boštjan Marhold, Nina Mikulin, Barbara Modrijan, Sara Može, Tanja Novak, Lea Peršič, Tanja Radovič, Simona Šinkovec, Urška Vranjek, Jerneja Umer, Petra Žalodec), and the annotators within the Development of Slovene in the Digital Environment project (Tina Munda, Ina Poteko, Rebeka Roblek, Luka Terčon and Karolina Zgaga).

## Key references

* Kaja Dobrovoljc, Tomaž Erjavec, Simon Krek. 2017. The Universal Dependencies Treebank for Slovenian. In: Proceeding of the 6th Workshop on Balto-Slavic Natural Language Processing (BSNLP 2017), 33–38. Valencia, 2017.

* Kaja Dobrovoljc, Nikola Ljubešić. 2022. Extending the SSJ Universal Dependencies Treebank for Slovenian: Was it Worth it?. In: Proceedings of the 16th Linguistic Annotation Workshop (LAW-XVI), LREC 2022, 15–22. Marseille, 2022.

## Other

* Tomaž Erjavec, Darja Fišer, Simon Krek and Nina Ledinek. 2010. The JOS Linguistically Tagged Corpus of Slovene. In: Proceedings of the Seventh International Conference on Language Resources and Evaluation (LREC'10). Malta, 2010.

* Simon Krek et al. 2021. Training corpus ssj500k 2.3, Slovenian language resource repository CLARIN.SI, ISSN 2820-4042, http://hdl.handle.net/11356/1434.

* Federico Martelli et al. 2022. Parallel sense-annotated corpus ELEXIS-WSD 1.0, Slovenian language resource repository CLARIN.SI, ISSN 2820-4042, http://hdl.handle.net/11356/1674.


# Changelog

<pre>
2025--04-30 v 2.16
-- Added genre information for most documents in the treebank

2024-04-29 v2.14
-- Reran the automatic conversion of sole object dependency relations from semantic role labels to address some errors
-- Manually checked the remaining sole object relations in the portion of the treebank that does not have SRL tags available
-- Implemented additional fixes to conform to new guidelines changes:
--- Manually corrected instances of reported speech to conform to new guidelines
--- Manually corrected foreign language expressions in the treebank to conform to the revised flat:foreign guidelines
-- Revised the annotations of emphatic particles and adverbs, so that they are now consistently attached to the following phrase
-- Manually checked all instances of the lemma "saj", converting 'cc' to 'advmod' where appropriate
-- Manually checked all syntactic trees made up of only two leaf nodes and corrected them if they proved to be errors
-- Improved consistency of expressions using the 'fixed' relation

2023-10-30 v2.13
-- Various fixes made to conform to the new guidelines changes in UDv2, i.e.
--- Fixed sufficiency and excess constructions to have proper annotations
--- Revised sole objects in sentences via automatic conversion from semantic role labels (recepients are aligned with the iobj relation)
--- Revised optional depictives, they are now consistently annotated as 'advcl'
-- Improved consistency of certain constructions using the 'flat', 'xcomp', and 'orphan' relations
-- Various other fixes pertaining to the use of certain words/phrases ('ne glede', 'pol', 'kaj', 'saj', etc.)

2022-08-10 v2.10
-- Updated the readme file to document the treebank extension in v2.10 (post-release)
-- Fixed some annotation errors in the test set to be released as part of v2.11
-- Fixed legacy validation errors relating to erroneous dual subjects to be released as part of v2.11
-- Changed license to CC-BY-SA

2019-10-28 v2.5
-- Fixed legacy validation errors, i.e.
--- Re-attaching the punctuation causing non-projectivity
--- Changing numerical adjuncts from 'advmod' to 'obl'
--- Re-attaching leafs of unlike parents
--- (Temporarily) changing 'aux' to 'dep' for colloquial contracted forms
-- Created the language overview page

2019-10-28 v2.5
-- Fixed legacy validation errors, i.e.
--- Re-attaching the punctuation causing non-projectivity
--- Changing numerical adjuncts from 'advmod' to 'obl'
--- Re-attaching leafs of unlike parents
--- (Temporarily) changing 'aux' to 'dep' for colloquial contracted forms
-- Created the language overview page

2019-01-24 v2.4
-- Performed new conversion from (draft) ssj500k 2.2
-- Removed bugs related to # text and SpaceAfter=No
-- Changed conversion rules, i.e.
--- Attributed Polarity=Neg to all 'ne' particles
--- Moved 'obilo' from ADV do DET

2018-04-15 v2.2
-- Repository renamed from UD_Slovenian to UD_Slovenian-SSJ.
-- Changed two flat:name errors.

2017-01-31 v2.0
-- New rules for conversion from UDv1 to UDv2
-- Fixed a few errors in the original ssj500k treebank (ssj500k_v1.6)

2016-05-15 v1.3
-- Added PronType to possessive pronouns
-- Added PronType to some determiners
-- Fixed a few minor issues in the conversion script based on content validation
-- Fixed a few errors in the original ssj500k treebank
-- Fixed the SpaceAfter=No bug
</pre>

<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v1.2
License: CC BY-SA 4.0
Includes text: yes
Genre: news nonfiction fiction
Lemmas: manual native
UPOS: converted with corrections
XPOS: manual native
Features: converted with corrections
Relations: converted with corrections
Contributors: Dobrovoljc, Kaja; Erjavec, Tomaž; Krek, Simon
Contributing: elsewhere
Contact: kaja.dobrovoljc@ijs.si
===============================================================================
</pre>
