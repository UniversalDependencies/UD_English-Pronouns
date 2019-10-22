# Summary

UD English-Pronouns is aimed to make pronoun identification more accurate and with a more balanced distribution across genders. The dataset is initially targeting the Independent Genitive pronouns, hers, (independent) his, and (singular) theirs.

# Introduction

The Independent Genitive pronoun "hers" is wrongly classified as a noun or adjective by the most widely used parsers (in October of 2019.) This includes (alphabetically) Amazon Comprehend, Google Natural Language API, and the Stanford Parser. 

## Cause of errors: missing examples

The cause of the errors in the most popular syntactic parsers are most likely because "hers" is rare in the existing datasets. The pronoun "hers" only occurs three times in the entire Universal Dependencies datasets in of October 2019. Of those three times, it is never marked with "Case=Gen", "Poss=Yes", or "PronType=Prs" which would be the correct ;ist of morphological features (FEATS) to indicate that it is a Genitive. 

In one case only of three, "hers" was correctly annotated as "P3SG-GEN-INDEP" in the Language-specific part-of-speech tag (XPOS) field. But this field is largely ignored by general purpose syntactic parsers.

The three examples are in the training data, so the complete absense of "hers" in the development and test data might have let this error slip under the radar. 

## Inherent gender bias 

The Feminine Dependent and Independent Genitive pronouns differs from the Masculine Genitive pronouns by having two forms, "her" and "hers", instead of using the same for both, "his". For example: "her car", "car of her*s*" / "his car", "car of his".

It is almost certain that the most popular syntactic parsers correctly identify the Masculine Independent Genitive pronouns correct purely because "his" is the same form as the Dependent. 

So, while the errors result from arbitrary linguistic distinctions that are not any person's fault, they have results in a situation that patterns with gender bias. 

As many individuals prefer "they/them/their/theirs" as their personal pronouns, and every instance in the existing datasets are annotated as plurals, this also presents a gender bias in the data. So, this dataset is also targeting examples of singular "theirs".

The Independent Genitive can occur in more syntactic contexts than any other pronoun: pretty much anywhere that a noun phrase can be occur. So, the new dataset is adding a lot of grammatical diversity, too! 

## How the dataset was created and is structured

The dataset was created manually, targeting syntactic diversity. For example, there are sentences with "hers" appearing as the subject, object, indirect object, and oblique arguments, sentences with "hers" in a conjunction, in a complement clause, etc. 

About 90% of the sentences are completely unique, and the remaining 10% alternate an important linguistic feature in English, like regular and irregular verbs, or linguistic features that would have different syntax and morphology in other languages, like the locative/ablative case distinction.

The "comment" field describes exactly what grammatical structure(s) are captured in each sentence.  

A "previous" field is also added to include a previous sentence. Independent pronouns refer to unnamed entities and those entities are typically made salient by context. It was too unnatural to always make the entity explicit in the same sentence, so the previous sentence should help. Here are two examples:

\# sent_id = 20
\# text = Hers accelerated.
\# comment = subject to regular intransitive verb
\# previous = What did Alex's car do?

\# sent_id = 55
\# text = Hers is easy to clean.
\# comment = extraction/raising via "tough extraction" and clausal subject
\# previous = What did the dealer like about Alex's car?

The "previous" sentence should also make it clear that the "theirs" variants are unambiguously singular in this context. Many pre-trained models rely on sentence adjacency prediction, so this means that these sentences can also be used for these models.

It was simply for lack of time that the previous sentences don't also get annotations in this corpus: that would be a fine extension! 

In version 1.0, 57 unique sentences were created with an Independent Genitive pronoun and they were copied with all pronoun alternations to make 342 total sentences with 2,034 total words. Experiments to semi-automate the expansion of the dataset are ongoing.

# Acknowledgments

The dataset was created by [Robert Munro](http://www.robertmunro.com) while writing [Human-in-the-Loop Machine Learning](bit.ly/huml_book ) (Manning Publications)

Please cite this book if using this dataset.

# Changelog

* 2019-10-17 v1.0
  * First release in UD


<pre>
=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.5
License: CC BY-SA 4.0
Includes text: yes
Genre: grammar-examples
Lemmas: manual
UPOS: manual
XPOS: manual
Features: manual
Relations: manual
Contributors: Munro, Robert
Contributing: elsewhere
Contact: rmunro@alumni.stanford.edu
===============================================================================
</pre>
