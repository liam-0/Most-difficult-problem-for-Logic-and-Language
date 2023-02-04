# Most-difficult-problem-for-Logic-and-Language
This repository contains three files. 

NLI_final.ipynb, is the file of the coding part of the Logic and Language final project. Which contains two parts:
* Data preparation
* Data analysis, and automatic filter design

Two .csv files are the result data of models' prediction (not the result of our designed filter), with the human manual check and some modifications. It's a merged version of the result of the "Data preparation" section in NLI_final.ipynb. And these two files will be used in the second section "Data analysis, and automatic filter design" to test the filter performance.


# NLI_final.ipynb:
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1za-dUNbearC0RA6lwb4weIMzflQoOrYc?usp=sharing)

## Data preparation
For this section, don't forget to run the colab pages in GPU mode, otherwise, you will take a long time. "Data preparation" contains three subsections:
* Model set up

This section is for install package and three models we applid. which are:

|Model Name|Hugging Face link|
|:--------:|:---------------:|
|ynie/roberta-large-snli_mnli_fever_anli_R1_R2_R3-nli|https://huggingface.co/ynie/roberta-large-snli_mnli_fever_anli_R1_R2_R3-nli|
|cross-encoder/nli-deberta-v3-large|https://huggingface.co/cross-encoder/nli-deberta-v3-large|
|cross-encoder/nli-MiniLM2-L6-H768|https://huggingface.co/cross-encoder/nli-MiniLM2-L6-H768|

* Loading dataset

This section is for loading the two datasets we tested. which are:

|Dataset|Hugging Face link|
|:-----:|:---------------:|
|snli|https://huggingface.co/datasets/snli|
|multi_nli|https://huggingface.co/datasets/multi_nli|


* Model prediciotn

This section is for using the test sets of the mentioned datasets to test models' performance and downing the result as .csv files.

## Data analysis, and automatic filter design
To run this section, you first need to upload the two .csv file into colab pages, which are already in this repository. You can run this section in CPU mode.

After manually checking the result of the prediction, we conclusion following 4 rules (patterns) that can be used to build a rule-based filter. Four rules:
* Check for ungrammatical words in the hypothesis (this is not strictly a subset of rule 3)
* Check for words with a (highly) negative meaning in the hypothesis
* Check for ungrammatical sentence structure in the hypothesis
* Check for ungrammatical sentence structure in the premise
