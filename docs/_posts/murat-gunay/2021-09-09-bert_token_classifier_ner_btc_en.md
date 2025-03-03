---
layout: model
title: Detect Entities in Twitter texts
author: John Snow Labs
name: bert_token_classifier_ner_btc
date: 2021-09-09
tags: [en, open_source, ner, btc, twitter]
task: Named Entity Recognition
language: en
edition: Spark NLP 3.2.2
spark_version: 2.4
supported: true
article_header:
  type: cover
use_language_switcher: "Python-Scala-Java"
---

## Description

- This model is trained on Broad Twitter Corpus (BTC) data-set, so that it can detect entities in Twitter-based texts successfully.
- `BertForTokenClassification()` module, which uses the Deep Learning (`torch`) algorithm, is used to train this model.
- The embeddings `bert_base_cased` is embedded inside the model so, you don't need to use any embeddings in the NLP pipeline.

## Predicted Entities



{:.btn-box}
<button class="button button-orange" disabled>Live Demo</button>
<button class="button button-orange" disabled>Open in Colab</button>
[Download](https://s3.amazonaws.com/auxdata.johnsnowlabs.com/public/models/bert_token_classifier_ner_btc_en_3.2.2_2.4_1631195072459.zip){:.button.button-orange.button-orange-trans.arr.button-icon}

## How to use



<div class="tabs-box" markdown="1">
{% include programmingLanguageSelectScalaPythonNLU.html %}
```python
...

tokenClassifier = BertForTokenClassification.pretrained("bert_token_classifier_ner_btc", "en")\
  .setInputCols("token", "document")\
  .setOutputCol("ner")\
  .setCaseSensitive(True)

ner_converter = NerConverter()\
        .setInputCols(["document","token","ner"])\
        .setOutputCol("ner_chunk")

pipeline =  Pipeline(stages=[documentAssembler, tokenizer, tokenClassifier, ner_converter])

model = pipeline.fit(spark.createDataFrame(pd.DataFrame({'text': ['']})))
test_sentences = ["""Wengers big mistakes is not being ruthless enough with bad players.""", """my dream FUUUUUULHAAAAAAM !!!.."""]
result = model.transform(spark.createDataFrame(pd.DataFrame({'text': test_sentences})))
```
```scala
...

val tokenClassifier = BertForTokenClassification.pretrained("bert_token_classifier_ner_btc", "en")\
  .setInputCols("token", "document")\
  .setOutputCol("ner")\
  .setCaseSensitive(True)

val ner_converter = NerConverter()\
        .setInputCols(Array("document","token","ner"))\
        .setOutputCol("ner_chunk")

val pipeline =  new Pipeline().setStages(Array(documentAssembler, tokenizer, tokenClassifier, ner_converter))

val data = Seq("Wengers big mistakes is not being ruthless enough with bad players.", "my dream FUUUUUULHAAAAAAM !!!..").toDF("text")

val result = pipeline.fit(data).transform(data)
```
</div>

## Results

```bash
+----------------+---------+
|chunk           |ner_label|
+----------------+---------+
|Wengers         |PER      |
|FUUUUUULHAAAAAAM|ORG      |
+----------------+---------+
```

{:.model-param}
## Model Information

{:.table-model}
|---|---|
|Model Name:|bert_token_classifier_ner_btc|
|Compatibility:|Spark NLP 3.2.2+|
|License:|Open Source|
|Edition:|Official|
|Input Labels:|[sentence, token]|
|Output Labels:|[ner]|
|Language:|en|
|Case sensitive:|true|
|Max sentense length:|128|

## Data Source

https://github.com/juand-r/entity-recognition-datasets/tree/master/data/BTC

## Benchmarking

```bash
              precision    recall  f1-score   support

       B-LOC       0.90      0.79      0.84       536
       B-ORG       0.80      0.79      0.79       821
       B-PER       0.95      0.62      0.75      1575
       I-LOC       0.96      0.76      0.85       181
       I-ORG       0.88      0.81      0.84       217
       I-PER       0.99      0.91      0.95       315
           O       0.97      0.99      0.98     26217

    accuracy                           0.96     29862
   macro avg       0.92      0.81      0.86     29862
weighted avg       0.96      0.96      0.96     29862
```
