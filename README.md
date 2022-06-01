# Tigrinya Analogy Test

Tigrinya Analogy Test for evaluating word embedding models.

Download the dataset [HERE](https://zenodo.org/record/7089051).

## Introduction

This is a Tigrinya version of the Google Analogy Test set, which is used to evaluate English word-embedding models.
The analogy test is a well-established strategy to empirically evaluate the quality of word-embedding models.
More information about the English task can be found at the [ACL Wiki](https://aclweb.org/aclwiki/Google_analogy_test_set_(State_of_the_art)).
The data was first machine translated then manually verified by a native speaker to reduce errors.

Some aspects of the original analogy test is focused on English and may not transfer well to other languages, such as those related to grammar or morphology.
Therefore, when adapting the task we have discarded examples that were discovered as irrelevant in Tigrinya.
Finally, there are a total of `18465` entries in the Tigrinya Analogy Test set, while the source English data has `19544` entries.

An entry is dropped if the translations led to one of the following conditions:

 1. If the source word pair map to one Tigrinya word, for example, both *lucky* and *luckiest* correspond to *ዕድለኛ*.
 2. If the source word results in a multi-word expression. For example, *grandson* (*ወዲ ጓል* / *ወዲ ወዲ)*, *granddaughter* (*ጓል ጓል* / *ጓል ወዲ*). This because the typical word-embedding approaches such as word2vec are not designed to predict multi-word phrases.

## Test Sections

The test includes a series of semantic and syntactic analogies divided up into subsections including world capitals, currencies, family, tense, and plurality.

The test contains the following sections:

 1. capital-world
 1. currency
 1. city-in-state
 1. family
 1. gram1-adjective-to-adverb
 1. gram2-opposite
 1. gram3-comparative
 1. gram4-superlative
 1. gram5-present-participle
 1. gram6-nationality-adjective
 1. gram7-past-tense
 1. gram8-plural
 1. gram9-plural-verbs

**Examples:**

- Semantic section of World Capitals: “ኣስመራ: ኤርትራ as ፓሪስ: ?” and if the model responds correctly it will return: “ፈረንሳ”.
- Semantic section of Family section: “ሰብኣይ: ሰበይቲ as ወዲ: ጓል”.
- Syntax section with tense, a sample analogy might be “Walk: Walked as Run: Ran”.

## Evaluation

The final accuracy of a model is the proportion of the questions that the model answers correctly.
Generally, a better-quality model would answer more questions correctly than a model of lower quality.
However, note that a model with low performance on this analogy test might still contain useful information, but may not be robust enough for more complex tasks.

## Limitations

- The analogy test could be a good indicator of the quality of word-embeddings, but it should be used with caution when comparing models trained on varying domains of data. It shall not be expected to generalize equally to all domains and genres.
- The final score can be affected by the size, vocabulary, and domain of the text with which the models are trained on. For example, this may not be a good benchmark to compare models trained on news text vs posts on social media.
- One can improve performance of models on the test set without necessarily building a generally good model for the language. That is by optimizing the hyperparameters such as the vector dimension, context window, learning rate, and iterations.
- Even though a manual sanity check was performed, we note that the semi-automatic construction of the Tigrinya test set might contains errors. If you discover any, you are welcome to contribute back by opening an Issue at the [GitHub repo](https://github.com/fgaim/tigrinya-analogy-test).

## Download

The dataset can be downloaded from Zenodo [here](https://zenodo.org/record/7089051).

## Citation

If you use this resource in your research, please cite as follows:

```
@dataset{fgaim2022analogytest,
  author       = {Gaim, Fitsum and Park, Jong C.},
  title        = {Tigrinya Analogy Test for evaluating Word Embeddings},
  month        = may,
  year         = 2022,
  publisher    = {Zenodo},
  version      = {1.0.0},
  doi          = {10.5281/zenodo.7089051},
  url          = {https://doi.org/10.5281/zenodo.7089051}
  github       = {https://github.com/fgaim/tigrinya-analogy-test},
}
```

## License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />The Tigrinya Analogy Test dataset is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
