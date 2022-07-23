# Tigrinya Analogy Test

Tigrinya Analogy Test for evaluating word embeddings models.

## Introduction

The Tigrinya is translated from the Google Analogy Test set for the English language. The translation of each word was verified manually by a native Tigrinya speaker.
More information about the English task can be found at the [ACL Wiki](https://aclweb.org/aclwiki/Google_analogy_test_set_(State_of_the_art)).

There are a total of `18465` samples in the Tigrinya Analogy Test set, while the source English data has 19544 samples.
We discarded some examples when adapting the task for Tigrinya.
A sample is dropped if the translations led to one of the following conditions:

 1. If the source word pair map to one Tigrinya word. For example, weird & weirdest (ስግንጢር), lucky & luckiest (ዕድለኛ).
 2. If the source word results in a multi-word expression. For example, grandson (ወዲ ጓል / ወዲ ወዲ), granddaughter (ጓል ጓል / ጓል ወዲ) .

## Test Sections

The analogy test is a well-established strategy to empirically evaluate the quality of word-embedding models.
The test includes a series of semantic and syntactic analogies divided up into subsections including world capitals, countries’ currencies, family, tense, and plurality.

Sections:

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

Examples:

- Semantic section of World Capitals: “ኣስመራ: ኤርትራ as ፓሪስ: ?” and if the model responds correctly it will return: “ፈረንሳ.”
- Semantic section of Family section: “ሰብኣይ: ሰበይቲ as ወዲ: ጓል.”
- Syntax section with tense, a sample analogy might be “Walk: Walked as Run: Ran.”

## Evaluation

The final accuracy of a model is the proportion of the questions that the model answers correctly.
Generally, a better-quality model would answer more questions correctly than a model of lower quality.
However, note that a model with low performance on this analogy test, might still contain useful information, but may not be robust or good enough for more complex tasks.

**Limitations**
While the analogy test could be a good indicator of quality, one should avoid overreliance when comparing models trained on different data.
The score can be affected by the size, vocabulary, and domain of the text with which the models are trained.
For example, this may not be a good benchmark to compare models trained on news text *vs* comments on social media.
Moreover, one can improve performance by tweaking the hyperparameters, particularly the dimension, context window, learning rate, and iterations.

The dataset might contain errors, if you discover any, please open an issue or send a pull request.

## Citation

If you use this resource in your research, please cite as follows:

``` markdown
@data{fgaim2022analogytest,
  title={Tigrinya Analogy Test},
  author={Fitsum Gaim},
  link={https://github.com/fgaim/tigrinya-analogy-test},
  year={2022}
}
```

## License

The Tigrinya Analogy Test set is made available under the MIT license.
