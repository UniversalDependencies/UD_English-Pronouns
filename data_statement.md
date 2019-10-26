# Data Statement for English Pronouns Universal Dependencies 

This is the data statement to accompany the [English Pronouns Universal Dependencies dataset](https://github.com/UniversalDependencies/UD_English-Pronouns/)

The data statements follows the structure recommended in "Data Statements for Natural Language Processing:
[Toward Mitigating System Bias and Enabling Better Science](https://techpolicylab.uw.edu/wp-content/uploads/2018/10/Data-Statements-TACL.pdf) by Emily M. Bender and Batya Friedman:

## Curation Rationale

The Independent Genitive pronoun "hers" is wrongly classified as a noun or adjective by the most widely used parsers (in October of 2019). This includes (alphabetically) Amazon Comprehend, Google Natural Language API, and the Stanford Parser. This error was traced to the data - not the algorithms themselves - and so this dataset was created to fix these errors.

## Language Variety

The dataset is in English and has examples of the five most common singular Independent Genitive pronouns "hers", "hers", "yours", "mine", "theirs". 

There is code released with the dataset that allows someone to extend the dataset programmatically to other pronouns.

## Speaker/Annotator Demographic

The dataset set is synthetic examples created and annotated by Robert Munro whose English is from Australia, UK, Sierra Leone, and the USA. 

## Speech Situation and Text Characteristics

The dataset consists of synthetic examples that aimed to maximize the diversity of linguistic contexts that  Independent Genitive pronouns can occur in: Subject, Object, Relative clauses, Conjunctions, etc. 

The examples cover a range of registers, from formal speech to informal speech.

One set of sentences were created, each with a Independent pronoun in them (like "theirs") and the other sentences were created programmatically from those original sentences and then hand-checked.

