# NLP-hw

1. Implementation of transformer for [Transliteration task](https://codalab.lisn.upsaclay.fr/competitions/12240)

2. Text categorization *contest* [Argument Mining Competition](https://codalab.lisn.upsaclay.fr/competitions/786)

**Methodology**

I tried to use 2 pretrained models: mbert and rubert-tiny because these models are lighter than xmlr and rubert. I decided to use new model for each class.

Firstly I decided to see how each model deals with task of classification by itself, then tried to make a simple ansamble: took an average of logits for each label which were predicted by each model.

Also I wanted to try some augmentations with the best model: use lemmas instead of initial text and to use paraphraser.

3. Text detoxification and style transfer *contest* [RUSSE 2022 Russian Text Detoxification Based on Parallel Corpora](https://codalab.lisn.upsaclay.fr/competitions/642)

**Methodology**

First, I merged all the text columns into one to create a consolidated dataset for model training.

The choice of the 'sberbank-ai/ruT5-base model' is based on its training on a large volume of Russian-language texts.

For prediction, I use the paraphrase function. It performs a grid search to find the optimal beam size based on metrics such as BLEU score and a metric indicating the probability that the generated text is non-toxic, obtained from the 'SkolkovoInstitute/russian_toxicity_classifier' model.
