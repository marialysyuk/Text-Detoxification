# Text-Detoxification

## Task description

This is the first competition on the automatic detoxification of the Russian texts to combat offensive speech. Such a kind of textual style transfer can be used, for instance, for processing toxic content in social media and chatbot text filtering. In addition to the first parallel corpus of toxic / detoxified data for Russian, the organisers also provide baseline approaches to style transfer and a set of evaluation metrics based on the state-of-the-art approaches to evaluation.

## My scores

The results of the competition are presented here: https://codalab.lisn.upsaclay.fr/competitions/532#results.

**Style transfer accuracy**: 1/11

**ChrF1** : 4/11.


## Methodology

The baseline solution is taken from here https://github.com/yandex/mlcup/blob/main/nlp/offline_baseline.ipynb

The main idea of the solution is as follows:

1) Use pretrained Roberta model to predict the toxicity of the word.

2) If the toxicity of the word is higher than some threshold, then remove it. By the way, in the initial solution it's assumed that we don't remove the word but substitute it by the non-toxic synonym that lies in KDTree. However, this solution doesn't work well with our train data (partly, because the algorithm for obtaining synonyms is not that good, partly since from the train data it's vivid that in many cases we don't need substitution).

Upgrade over the baseline:

1) Impovement over the toxicity dictionary

2) Custom changes for some particular words substitution

3) Swap of the idea - not to substitute but simply remove in the majority of cases
