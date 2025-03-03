# Spark NLP: State of the Art Natural Language Processing

[![build](https://github.com/JohnSnowLabs/spark-nlp/workflows/build/badge.svg)](https://github.com/JohnSnowLabs/spark-nlp/actions) [![Current Release Version](https://img.shields.io/github/v/release/JohnSnowLabs/spark-nlp.svg?style=flat-square&logo=github)](https://github.com/JohnSnowLabs/spark-nlp/releases) [![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.johnsnowlabs.nlp/spark-nlp_2.12/badge.svg)](https://search.maven.org/artifact/com.johnsnowlabs.nlp/spark-nlp_2.12) [![PyPI version](https://badge.fury.io/py/spark-nlp.svg)](https://badge.fury.io/py/spark-nlp) [![Anaconda-Cloud](https://anaconda.org/johnsnowlabs/spark-nlp/badges/version.svg)](https://anaconda.org/JohnSnowLabs/spark-nlp) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/JohnSnowLabs/spark-nlp/blob/master/LICENSE) [![PyPi downloads](https://static.pepy.tech/personalized-badge/spark-nlp?period=total&units=international_system&left_color=grey&right_color=orange&left_text=pip%20downloads)](https://pypi.org/project/spark-nlp/)

Spark NLP is a state-of-the-art Natural Language Processing library built on top of Apache Spark. It provides **simple**, **performant** & **accurate** NLP annotations for machine learning pipelines that **scale** easily in a distributed environment. Spark NLP comes with **3700+** pretrained **pipelines** and **models** in more than **200+** languages.
It also offers tasks such as **Tokenization**, **Word Segmentation**, **Part-of-Speech Tagging**, Word and Sentence **Embeddings**, **Named Entity Recognition**, **Dependency Parsing**, **Spell Checking**, **Text Classification**, **Sentiment Analysis**, **Token Classification**, **Machine Translation** (+180 languages), **Summarization** & **Question Answering**, and many more [NLP tasks](#features).

**Spark NLP** is the only open-source NLP library in **production** that offers state-of-the-art transformers such as **BERT**, **ALBERT**, **ELECTRA**, **XLNet**, **DistilBERT**, **RoBERTa**, **XLM-RoBERTa**, **Longformer**, **ELMO**, **Universal Sentence Encoder**, **Google T5**, and **MarianMT** not only to **Python** and **R**, but also to **JVM** ecosystem (**Java**, **Scala**, and **Kotlin**) at **scale** by extending **Apache Spark** natively.

## Project's website

Take a look at our official Spark NLP page: [http://nlp.johnsnowlabs.com/](http://nlp.johnsnowlabs.com/) for user documentation and examples

## Community support

- [Slack](https://www.johnsnowlabs.com/slack-redirect/) For live discussion with the Spark NLP community and the team
- [GitHub](https://github.com/JohnSnowLabs/spark-nlp) Bug reports, feature requests, and contributions
- [Discussions](https://github.com/JohnSnowLabs/spark-nlp/discussions) Engage with other community members, share ideas, and show off how you use Spark NLP!
- [Medium](https://medium.com/spark-nlp) Spark NLP articles
- [YouTube](https://www.youtube.com/channel/UCmFOjlpYEhxf_wJUDuz6xxQ/videos) Spark NLP video tutorials

## Table of contents

- [Features](#features)
- [Requirements](#requirements)
- [Quick Start](#quick-start)
- [Apache Spark Support](#apache-spark-support)
- [Databricks Support](#databricks-support)
- [EMR Support](#emr-support)
- [Using Spark NLP](#usage)  
  - [Spark Packages](#spark-packages)
  - [Scala](#scala)
    - [Maven](#maven)
    - [SBT](#sbt)
  - [Python](#python)
    - [Pip/Conda](#pipconda)
  - [Compiled JARs](#compiled-jars)
  - [Apache Zeppelin](#apache-zeppelin)
  - [Jupyter Notebook](#jupyter-notebook-python)
  - [Google Colab Notebook](#google-colab-notebook)
  - [Kaggle Kernel](#kaggle-kernel)
  - [Databricks Cluser](#databricks-cluster)
  - [EMR Cluser](#emr-cluster)
  - [GCP Dataproc](#gcp-dataproc)
  - [Spark NLP Configuration](#spark-nlp-configuration)
- [Pipelines & Models](#pipelines-and-models)
  - [Pipelines](#pipelines)
  - [Models](#models)
- [Offline](#offline)  
- [Examples](#examples)  
- [FAQ](#faq)
- [Citation](#citation)
- [Contributing](#contributing)

## Features

- Tokenization
- Trainable Word Segmentation
- Stop Words Removal
- Token Normalizer
- Document Normalizer
- Stemmer
- Lemmatizer
- NGrams
- Regex Matching
- Text Matching
- Chunking
- Date Matcher
- Sentence Detector
- Deep Sentence Detector (Deep learning)
- Dependency parsing (Labeled/unlabeled)
- Part-of-speech tagging
- Sentiment Detection (ML models)
- Spell Checker (ML and DL models)
- Word Embeddings (GloVe and Word2Vec)
- BERT Embeddings (TF Hub & HuggingFace models)
- DistilBERT Embeddings (HuggingFace models)
- RoBERTa Embeddings (HuggingFace models)
- XLM-RoBERTa Embeddings (HuggingFace models)
- Longformer Embeddings (HuggingFace models)
- ALBERT Embeddings (TF Hub & HuggingFace models)
- XLNet Embeddings
- ELMO Embeddings (TF Hub models)
- Universal Sentence Encoder (TF Hub models)
- BERT Sentence Embeddings (TF Hub & HuggingFace models)
- RoBerta Sentence Embeddings (HuggingFace models)
- XLM-RoBerta Sentence Embeddings (HuggingFace models)
- Sentence Embeddings
- Chunk Embeddings
- Unsupervised keywords extraction
- Language Detection & Identification (up to 375 languages)
- Multi-class Sentiment analysis (Deep learning)
- Multi-label Sentiment analysis (Deep learning)
- Multi-class Text Classification (Deep learning)
- BERT for Token Classification
- DistilBERT for Token Classification
- Neural Machine Translation (MarianMT)
- Text-To-Text Transfer Transformer (Google T5)
- Named entity recognition (Deep learning)
- Easy TensorFlow integration
- GPU Support
- Full integration with Spark ML functions
- +2000 pre-trained models in +200 languages!
- +1700 pre-trained pipelines in +200 languages!
- Multi-lingual NER models: Arabic, Bengali, Chinese, Danish, Dutch, English, Finnish, French, German, Hebrew, Italian, Japanese, Korean, Norwegian, Persian, Polish, Portuguese, Russian, Spanish, Swedish, and Urdu.

## Requirements

To use Spark NLP you need the following requirements:

- Java 8
- Apache Spark 3.1.x (or 3.0.x, or 2.4.x, or 2.3.x)

NOTE: Java 11 is supported if you are using Spark NLP and Spark/PySpark 3.x and above

**GPU (optional):**

Spark NLP 3.2.3 is built with TensorFlow 2.4.1 and requires the followings if you need GPU support

- CUDA11 and cuDNN 8.0.2

## Quick Start

This is a quick example of how to use Spark NLP pre-trained pipeline in Python and PySpark:

```sh
$ java -version
# should be Java 8 (Oracle or OpenJDK)
$ conda create -n sparknlp python=3.7 -y
$ conda activate sparknlp
# spark-nlp by default is based on pyspark 3.x
$ pip install spark-nlp==3.2.3 pyspark
```

In Python console or Jupyter `Python3` kernel:

```python
# Import Spark NLP
from sparknlp.base import *
from sparknlp.annotator import *
from sparknlp.pretrained import PretrainedPipeline
import sparknlp

# Start SparkSession with Spark NLP
# start() functions has 4 parameters: gpu, spark23, spark24, and memory
# sparknlp.start(gpu=True) will start the session with GPU support
# sparknlp.start(spark23=True) is when you have Apache Spark 2.3.x installed
# sparknlp.start(spark24=True) is when you have Apache Spark 2.4.x installed
# sparknlp.start(memory="16G") to change the default driver memory in SparkSession
spark = sparknlp.start()

# Download a pre-trained pipeline
pipeline = PretrainedPipeline('explain_document_dl', lang='en')

# Your testing dataset
text = """
The Mona Lisa is a 16th century oil painting created by Leonardo.
It's held at the Louvre in Paris.
"""

# Annotate your testing dataset
result = pipeline.annotate(text)

# What's in the pipeline
list(result.keys())
Output: ['entities', 'stem', 'checked', 'lemma', 'document',
'pos', 'token', 'ner', 'embeddings', 'sentence']

# Check the results
result['entities']
Output: ['Mona Lisa', 'Leonardo', 'Louvre', 'Paris']
```

For more examples, you can visit our dedicated [repository](https://github.com/JohnSnowLabs/spark-nlp-workshop) to showcase all Spark NLP use cases!

## Apache Spark Support

Spark NLP *3.2.3* has been built on top of Apache Spark 3.x while fully supports Apache Spark 2.3.x and Apache Spark 2.4.x:

| Spark NLP   |   Apache Spark 2.3.x  | Apache Spark 2.4.x | Apache Spark 3.0.x | Apache Spark 3.1.x |
|-------------|-----------------------|--------------------|--------------------|--------------------|
| 3.2.x       |YES                    |YES                 |YES                 |YES                 |
| 3.1.x       |YES                    |YES                 |YES                 |YES                 |
| 3.0.x       |YES                    |YES                 |YES                 |YES                 |
| 2.7.x       |YES                    |YES                 |NO                  |NO                  |
| 2.6.x       |YES                    |YES                 |NO                  |NO                  |
| 2.5.x       |YES                    |YES                 |NO                  |NO                  |
| 2.4.x       |Partially              |YES                 |NO                  |NO                  |
| 1.8.x       |Partially              |YES                 |NO                  |NO                  |
| 1.7.x       |YES                    |NO                  |NO                  |NO                  |
| 1.6.x       |YES                    |NO                  |NO                  |NO                  |
| 1.5.x       |YES                    |NO                  |NO                  |NO                  |

**NOTE:** Starting 3.0.0 release, the default `spark-nlp` and `spark-nlp-gpu` pacakges are based on Scala 2.12 and Apache Spark 3.x by default.

**NOTE:** Starting the 3.0.0 release, we support all major releases of Apache Spark 2.3.x, Apache Spark 2.4.x, Apache Spark 3.0.x, and Apache Spark 3.1.x

Find out more about `Spark NLP` versions from our [release notes](https://github.com/JohnSnowLabs/spark-nlp/releases).

## Databricks Support

Spark NLP 3.2.3 has been tested and is compatible with the following runtimes:

**CPU:**

- 5.5 LTS
- 5.5 LTS ML
- 6.4
- 6.4 ML
- 7.3
- 7.3 ML
- 7.4
- 7.4 ML
- 7.5
- 7.5 ML
- 7.6
- 7.6 ML
- 8.0
- 8.0 ML
- 8.1
- 8.1 ML
- 8.2
- 8.2 ML
- 8.3
- 8.3 ML
- 8.4
- 8.4 ML
- 9.0
- 9.0 ML

**GPU:**

- 8.1 ML & GPU
- 8.2 ML & GPU
- 8.3 ML & GPU
- 8.4 ML & GPU
- 9.0 ML & GPU

NOTE: Spark NLP 3.2.3 is based on TensorFlow 2.4.x which is compatible with CUDA11 and cuDNN 8.0.2. The only Databricks runtimes supporting CUDA 11. are 8.x ML with GPU.

## EMR Support

Spark NLP 3.2.3 has been tested and is compatible with the following EMR releases:

- emr-5.20.0
- emr-5.21.0
- emr-5.21.1
- emr-5.22.0
- emr-5.23.0
- emr-5.24.0
- emr-5.24.1
- emr-5.25.0
- emr-5.26.0
- emr-5.27.0
- emr-5.28.0
- emr-5.29.0
- emr-5.30.0
- emr-5.30.1
- emr-5.31.0
- emr-5.32.0
- emr-5.33.0
- emr-6.1.0
- emr-6.2.0
- emr-6.3.0

Full list of [Amazon EMR 5.x releases](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-release-5x.html)
Full list of [Amazon EMR 6.x releases](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-release-6x.html)

NOTE: The EMR 6.0.0 is not supported by Spark NLP 3.2.3

## Usage

## Spark Packages

### Command line (requires internet connection)

Spark NLP supports all major releases of Apache Spark 2.3.x, Apache Spark 2.4.x, Apache Spark 3.0.x, and Apache Spark 3.1.x. That's being said, you need to choose the right package for the right Apache Spark major release:

#### Apache Spark 3.x (3.0.x and 3.1.x - Scala 2.12)

```sh
# CPU

spark-shell --packages com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3

pyspark --packages com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3

spark-submit --packages com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3
```

The `spark-nlp` has been published to the [Maven Repository](https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp).

```sh
# GPU

spark-shell --packages com.johnsnowlabs.nlp:spark-nlp-gpu_2.12:3.2.3

pyspark --packages com.johnsnowlabs.nlp:spark-nlp-gpu_2.12:3.2.3

spark-submit --packages com.johnsnowlabs.nlp:spark-nlp-gpu_2.12:3.2.3

```

The `spark-nlp-gpu` has been published to the [Maven Repository](https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-gpu).

#### Apache Spark 2.4.x (Scala 2.11)

```sh
# CPU

spark-shell --packages com.johnsnowlabs.nlp:spark-nlp-spark24_2.11:3.2.3

pyspark --packages com.johnsnowlabs.nlp:spark-nlp-spark24_2.11:3.2.3

spark-submit --packages com.johnsnowlabs.nlp:spark-nlp-spark24_2.11:3.2.3
```

The `spark-nlp-spark24` has been published to the [Maven Repository](https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-spark24).

```sh
# GPU

spark-shell --packages com.johnsnowlabs.nlp:spark-nlp-gpu-spark24_2.11:3.2.3

pyspark --packages com.johnsnowlabs.nlp:spark-nlp-gpu-spark24_2.11:3.2.3

spark-submit --packages com.johnsnowlabs.nlp:spark-nlp-gpu-spark24_2.11:3.2.3

```

The `spark-nlp-gpu-spark24` has been published to the [Maven Repository](https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-gpu-spark24).

#### Apache Spark 2.3.x (Scala 2.11)

```sh
# CPU

spark-shell --packages com.johnsnowlabs.nlp:spark-nlp-spark23_2.11:3.2.3

pyspark --packages com.johnsnowlabs.nlp:spark-nlp-spark23_2.11:3.2.3

spark-submit --packages com.johnsnowlabs.nlp:spark-nlp-spark23_2.11:3.2.3
```

The `spark-nlp-spark23` has been published to the [Maven Repository](https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-spark23).

```sh
# GPU

spark-shell --packages com.johnsnowlabs.nlp:spark-nlp-gpu-spark23_2.11:3.2.3

pyspark --packages com.johnsnowlabs.nlp:spark-nlp-gpu-spark23_2.11:3.2.3

spark-submit --packages com.johnsnowlabs.nlp:spark-nlp-gpu-spark23_2.11:3.2.3

```

The `spark-nlp-gpu-spark23` has been published to the [Maven Repository](https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-gpu-spark23).

**NOTE**: In case you are using large pretrained models like UniversalSentenceEncoder, you need to have the following set in your SparkSession:

```sh
spark-shell \
  --driver-memory 16g \
  --conf spark.kryoserializer.buffer.max=2000M \
  --packages com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3
```

## Scala

Spark NLP supports Scala 2.11.x if you are using Apache Spark 2.3.x or 2.4.x and Scala 2.12.x if you are using Apache Spark 3.0.x or 3.1.x. Our packages are deployed to Maven central. To add any of our packages as a dependency in your application you can follow these coordinates:

### Maven

**spark-nlp** on Apache Spark 3.x:

```xml
<!-- https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp -->
<dependency>
    <groupId>com.johnsnowlabs.nlp</groupId>
    <artifactId>spark-nlp_2.12</artifactId>
    <version>3.2.3</version>
</dependency>
```

**spark-nlp-gpu:**

```xml
<!-- https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-gpu -->
<dependency>
    <groupId>com.johnsnowlabs.nlp</groupId>
    <artifactId>spark-nlp-gpu_2.12</artifactId>
    <version>3.2.3</version>
</dependency>
```

**spark-nlp** on Apache Spark 2.4.x:

```xml
<!-- https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-spark24 -->
<dependency>
    <groupId>com.johnsnowlabs.nlp</groupId>
    <artifactId>spark-nlp-spark24_2.11</artifactId>
    <version>3.2.3</version>
</dependency>
```

**spark-nlp-gpu:**

```xml
<!-- https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-gpu-spark24 -->
<dependency>
    <groupId>com.johnsnowlabs.nlp</groupId>
    <artifactId>spark-nlp-gpu_2.11</artifactId>
    <version>3.2.3</version>
</dependency>
```

**spark-nlp** on Apache Spark 2.3.x:

```xml
<!-- https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-spark23 -->
<dependency>
    <groupId>com.johnsnowlabs.nlp</groupId>
    <artifactId>spark-nlp-spark23_2.11</artifactId>
    <version>3.2.3</version>
</dependency>
```

**spark-nlp-gpu:**

```xml
<!-- https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-gpu-spark23 -->
<dependency>
    <groupId>com.johnsnowlabs.nlp</groupId>
    <artifactId>spark-nlp-gpu-spark23_2.11</artifactId>
    <version>3.2.3</version>
</dependency>
```

### SBT

**spark-nlp** on Apache Spark 3.x.x:

```sbtshell
// https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp
libraryDependencies += "com.johnsnowlabs.nlp" %% "spark-nlp" % "3.2.3"
```

**spark-nlp-gpu:**

```sbtshell
// https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-gpu
libraryDependencies += "com.johnsnowlabs.nlp" %% "spark-nlp-gpu" % "3.2.3"
```

**spark-nlp** on Apache Spark 2.4.x:

```sbtshell
// https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp
libraryDependencies += "com.johnsnowlabs.nlp" %% "spark-nlp-spark24" % "3.2.3"
```

**spark-nlp-gpu:**

```sbtshell
// https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-gpu
libraryDependencies += "com.johnsnowlabs.nlp" %% "spark-nlp-gpu-spark24" % "3.2.3"
```

**spark-nlp** on Apache Spark 2.3.x:

```sbtshell
// https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-spark23
libraryDependencies += "com.johnsnowlabs.nlp" %% "spark-nlp-spark23" % "3.2.3"
```

**spark-nlp-gpu:**

```sbtshell
// https://mvnrepository.com/artifact/com.johnsnowlabs.nlp/spark-nlp-gpu-spark23
libraryDependencies += "com.johnsnowlabs.nlp" %% "spark-nlp-gpu-spark23" % "3.2.3"
```

Maven Central: [https://mvnrepository.com/artifact/com.johnsnowlabs.nlp](https://mvnrepository.com/artifact/com.johnsnowlabs.nlp)

If you are interested, there is a simple SBT project for Spark NLP to guide you on how to use it in your projects [Spark NLP SBT Starter](https://github.com/maziyarpanahi/spark-nlp-starter)

## Python

Spark NLP supports Python 3.6.x and 3.7.x if you are using PySpark 2.3.x or 2.4.x and Python 3.8.x if you are using PySpark 3.x.

### Python without explicit Pyspark installation

### Pip/Conda

If you installed pyspark through pip/conda, you can install `spark-nlp` through the same channel.

Pip:

```bash
pip install spark-nlp==3.2.3
```

Conda:

```bash
conda install -c johnsnowlabs spark-nlp
```

PyPI [spark-nlp package](https://pypi.org/project/spark-nlp/) / Anaconda [spark-nlp package](https://anaconda.org/JohnSnowLabs/spark-nlp)

Then you'll have to create a SparkSession either from Spark NLP:

```python
import sparknlp

spark = sparknlp.start()
```

or manually:

```python
spark = SparkSession.builder \
    .appName("Spark NLP")\
    .master("local[4]")\
    .config("spark.driver.memory","16G")\
    .config("spark.driver.maxResultSize", "0") \    
    .config("spark.kryoserializer.buffer.max", "2000M")\
    .config("spark.jars.packages", "com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3")\
    .getOrCreate()
```

If using local jars, you can use `spark.jars` instead for comma-delimited jar files. For cluster setups, of course, you'll have to put the jars in a reachable location for all driver and executor nodes.

**Quick example:**

```python
import sparknlp
from sparknlp.pretrained import PretrainedPipeline

#create or get Spark Session

spark = sparknlp.start()

sparknlp.version()
spark.version

#download, load and annotate a text by pre-trained pipeline

pipeline = PretrainedPipeline('recognize_entities_dl', 'en')
result = pipeline.annotate('The Mona Lisa is a 16th century oil painting created by Leonardo')
```

## Compiled JARs

### Build from source

#### spark-nlp

- FAT-JAR for CPU on Apache Spark 3.x.x

```bash
sbt assembly
```

- FAT-JAR for GPU on Apache Spark 3.x.x

```bash
sbt -Dis_gpu=true assembly
```

- FAT-JAR for CPU on Apache Spark 2.4.x

```bash
sbt -Dis_spark24=true assembly
```

- FAT-JAR for GPU on Apache Spark 2.4.x

```bash
sbt -Dis_gpu=true -Dis_spark24=true assembly
```

- FAT-JAR for CPU on Apache Spark 2.3.x

```bash
sbt -Dis_spark23=true assembly
```

- FAT-JAR for GPU on Apache Spark 2.3.x

```bash
sbt -Dis_gpu=true -Dis_spark23=true assembly
```

### Using the jar manually

If for some reason you need to use the JAR, you can either download the Fat JARs provided here or download it from [Maven Central](https://mvnrepository.com/artifact/com.johnsnowlabs.nlp).

To add JARs to spark programs use the `--jars` option:

```sh
spark-shell --jars spark-nlp.jar
```

The preferred way to use the library when running spark programs is using the `--packages` option as specified in the `spark-packages` section.

## Apache Zeppelin

Use either one of the following options

- Add the following Maven Coordinates to the interpreter's library list

```bash
com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3
```

- Add a path to pre-built jar from [here](#compiled-jars) in the interpreter's library list making sure the jar is available to driver path

### Python in Zeppelin

Apart from the previous step, install the python module through pip

```bash
pip install spark-nlp==3.2.3
```

Or you can install `spark-nlp` from inside Zeppelin by using Conda:

```bash
python.conda install -c johnsnowlabs spark-nlp
```

Configure Zeppelin properly, use cells with %spark.pyspark or any interpreter name you chose.

Finally, in Zeppelin interpreter settings, make sure you set properly zeppelin.python to the python you want to use and install the pip library with (e.g. `python3`).

An alternative option would be to set `SPARK_SUBMIT_OPTIONS` (zeppelin-env.sh) and make sure `--packages` is there as shown earlier since it includes both scala and python side installation.

## Jupyter Notebook (Python)

**Recomended:**

The easiest way to get this done on Linux and macOS is to simply install `spark-nlp` and `pyspark` PyPI packages and launch the Jupyter from the same Python environment:

```sh
$ conda create -n sparknlp python=3.7 -y
$ conda activate sparknlp
# spark-nlp by default is based on pyspark 3.x
$ pip install spark-nlp==3.2.3 pyspark jupyter
$ jupyter notebook
```

The you can use `python3` kernel to run your code with creating SparkSession via `spark = sparknlp.start()`.

**Optional:**

If you are in different operating systems and require to make Jupyter Notebook run by using pyspark, you can follow these steps:

```bash
export SPARK_HOME=/path/to/your/spark/folder
export PYSPARK_PYTHON=python3
export PYSPARK_DRIVER_PYTHON=jupyter
export PYSPARK_DRIVER_PYTHON_OPTS=notebook

pyspark --packages com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3
```

Alternatively, you can mix in using `--jars` option for pyspark + `pip install spark-nlp`

If not using pyspark at all, you'll have to run the instructions pointed [here](#python-without-explicit-Pyspark-installation)

## Google Colab Notebook

Google Colab is perhaps the easiest way to get started with spark-nlp. It requires no installation or setup other than having a Google account.

Run the following code in Google Colab notebook and start using spark-nlp right away.

```sh
# This is only to setup PySpark and Spark NLP on Colab
!wget http://setup.johnsnowlabs.com/colab.sh -O - | bash
```

This script comes with the two options to define `pyspark` and `spark-nlp` versions via options:

```sh
# -p is for pyspark
# -s is for spark-nlp
# by default they are set to the latest
!wget http://setup.johnsnowlabs.com/colab.sh -O - | bash /dev/stdin -p 3.1.2 -s 3.1.3
```

[Spark NLP quick start on Google Colab](https://colab.research.google.com/github/JohnSnowLabs/spark-nlp-workshop/blob/master/jupyter/quick_start_google_colab.ipynb) is a live demo on Google Colab that performs named entity recognitions and sentiment analysis by using Spark NLP pretrained pipelines.

## Kaggle Kernel

Run the following code in Kaggle Kernel and start using spark-nlp right away.

```sh
# Let's setup Kaggle for Spark NLP and PySpark
!wget http://setup.johnsnowlabs.com/kaggle.sh -O - | bash
```

[Spark NLP quick start on Kaggle Kernel](https://www.kaggle.com/mozzie/spark-nlp-named-entity-recognition) is a live demo on Kaggle Kernel that performs named entity recognitions by using Spark NLP pretrained pipeline.

## Databricks Cluster

1. Create a cluster if you don't have one already

2. On a new cluster or existing one you need to add the following to the `Advanced Options -> Spark` tab:

    ```bash
    spark.kryoserializer.buffer.max 2000M
    spark.serializer org.apache.spark.serializer.KryoSerializer
    ```

3. In `Libraries` tab inside your cluster you need to follow these steps:

    3.1. Install New -> PyPI -> `spark-nlp==3.2.3` -> Install

    3.2. Install New -> Maven -> Coordinates -> `com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3` -> Install

4. Now you can attach your notebook to the cluster and use Spark NLP!

NOTE: If you are launching a Databricks runtime that is not based on Apache Spark 3.x please choose a compatible [Spark NLP package](#spark-packages)

## EMR Cluster

To launch EMR cluster with Apache Spark/PySpark and Spark NLP correctly you need to have bootstrap and software configuration.

A sample of your bootstrap script

```.sh
#!/bin/bash
set -x -e

echo -e 'export PYSPARK_PYTHON=/usr/bin/python3 
export HADOOP_CONF_DIR=/etc/hadoop/conf 
export SPARK_JARS_DIR=/usr/lib/spark/jars 
export SPARK_HOME=/usr/lib/spark' >> $HOME/.bashrc && source $HOME/.bashrc

sudo python3 -m pip install awscli boto spark-nlp

set +x
exit 0

```

A sample of your software configuration in JSON on S3 (must be public access):

```.json
[{
  "Classification": "spark-env",
  "Configurations": [{
    "Classification": "export",
    "Properties": {
      "PYSPARK_PYTHON": "/usr/bin/python3"
    }
  }]
},
{
  "Classification": "spark-defaults",
    "Properties": {
      "spark.yarn.stagingDir": "hdfs:///tmp",
      "spark.yarn.preserve.staging.files": "true",
      "spark.kryoserializer.buffer.max": "2000M",
      "spark.serializer": "org.apache.spark.serializer.KryoSerializer",
      "spark.driver.maxResultSize": "0",
      "spark.jars.packages": "com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3"
    }
}
]
```

A sample of AWS CLI to launch EMR cluster:

```.sh
aws emr create-cluster \
--name "Spark NLP 3.2.3" \
--release-label emr-6.2.0 \
--applications Name=Hadoop Name=Spark Name=Hive \
--instance-type m4.4xlarge \
--instance-count 3 \
--use-default-roles \
--log-uri "s3://<S3_BUCKET>/" \
--bootstrap-actions Path=s3://<S3_BUCKET>/emr-bootstrap.sh,Name=custome \
--configurations "https://<public_access>/sparknlp-config.json" \
--ec2-attributes KeyName=<your_ssh_key>,EmrManagedMasterSecurityGroup=<security_group_with_ssh>,EmrManagedSlaveSecurityGroup=<security_group_with_ssh> \
--profile <aws_profile_credentials>
```

## GCP Dataproc

1. Create a cluster if you don't have one already as follows.

At gcloud shell:

```bash
gcloud services enable dataproc.googleapis.com \
  compute.googleapis.com \
  storage-component.googleapis.com \
  bigquery.googleapis.com \
  bigquerystorage.googleapis.com
```

```bash
REGION=<region>
```

```bash
BUCKET_NAME=<bucket_name>
gsutil mb -c standard -l ${REGION} gs://${BUCKET_NAME}
```

```bash
REGION=<region>
ZONE=<zone>
CLUSTER_NAME=<cluster_name>
BUCKET_NAME=<bucket_name>
```

You can set image-version, master-machine-type, worker-machine-type,
master-boot-disk-size, worker-boot-disk-size, num-workers as your needs.
If you use the previous image-version from 2.0, you should also add ANACONDA to optional-components.
And, you should enable gateway.

```bash
gcloud dataproc clusters create ${CLUSTER_NAME} \
  --region=${REGION} \
  --zone=${ZONE} \
  --image-version=2.0 \
  --master-machine-type=n1-standard-4 \
  --worker-machine-type=n1-standard-2 \
  --master-boot-disk-size=128GB \
  --worker-boot-disk-size=128GB \
  --num-workers=2 \
  --bucket=${BUCKET_NAME} \
  --optional-components=JUPYTER \
  --enable-component-gateway \
  --metadata 'PIP_PACKAGES=spark-nlp spark-nlp-display google-cloud-bigquery google-cloud-storage' \
  --initialization-actions gs://goog-dataproc-initialization-actions-${REGION}/python/pip-install.sh
```

2. On an existing one, you need to install spark-nlp and spark-nlp-display packages from PyPI.

3. Now, you can attach your notebook to the cluster and use the Spark NLP!

## Spark NLP Configuration

You can change the following Spark NLP configurations via Spark Configuration:

| Property Name   |   Default  | Meaning | Since Version |
|-----------------|------------|---------|---------------|
|`spark.jsl.settings.pretrained.cache_folder`| `~/cache_pretrained`| The location to download and exctract pretrained `Models` and `Pipelines`. By default, it will be in User's Home directory under `cache_pretrained` directory|3.2.0
|`spark.jsl.settings.storage.cluster_tmp_dir` | `hadoop.tmp.dir`| The location to use on a cluster for temporarily files such as unpacking indexes for WordEmbeddings. By default, this locations is the location of `hadoop.tmp.dir` set via Hadoop configuration for Apache Spark. NOTE: `S3` is not supported and it must be local, HDFS, or DBFS|3.2.0
|`spark.jsl.settings.annotator.log_folder`| `~/annotator_logs` | The location to save logs from annotators during training such as `NerDLApproach`, `ClassifierDLApproach`, `SentimentDLApproach`, `MultiClassifierDLApproach`, etc. By default, it will be in User's Home directory under `annotator_logs` directory|3.2.0
|`spark.jsl.settings.aws.credentials.access_key_id`| `None` | Your AWS access key to use your S3 bucket to store log files of training models or access tensorflow graphs used in `NerDLApproach`|3.2.3
|`spark.jsl.settings.aws.credentials.secret_access_key`| `None` | Your AWS secret access key to use your S3 bucket to store log files of training models or access tensorflow graphs used in `NerDLApproach`|3.2.3
|`spark.jsl.settings.aws.credentials.session_token`| `None` | Your AWS MFA session token to use your S3 bucket to store log files of training models or access tensorflow graphs used in `NerDLApproach`|3.2.3
|`spark.jsl.settings.aws.s3_bucket`| `None` | Your AWS S3 bucket to store log files of training models or access tensorflow graphs used in `NerDLApproach`|3.2.3
|`spark.jsl.settings.aws.region`| `None` | Your AWS region to use your S3 bucket to store log files of training models or access tensorflow graphs used in `NerDLApproach`|3.2.3

### How to set Spark NLP Configuration

**SparkSession:**

You can use `.config()` during SparkSession creation to set Spark NLP configurations.

```python
from pyspark.sql import SparkSession

spark = SparkSession.builder \
        .master("local[*]") \        
        .config("spark.driver.memory", "16G") \
        .config("spark.driver.maxResultSize", "0") \
        .config("spark.serializer", "org.apache.spark.serializer.KryoSerializer") \
        .config("spark.kryoserializer.buffer.max", "2000m") \
        .config("spark.jsl.settings.pretrained.cache_folder", "sample_data/pretrained") \
        .config("spark.jsl.settings.storage.cluster_tmp_dir", "sample_data/storage") \
        .config("spark.jars.packages", "com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3") \
        .getOrCreate()
```

**spark-shell:**

```sh
spark-shell \
  --driver-memory 16g \
  --conf spark.driver.maxResultSize=0 \
  --conf spark.serializer=org.apache.spark.serializer.KryoSerializer
  --conf spark.kryoserializer.buffer.max=2000M \
  --conf spark.jsl.settings.pretrained.cache_folder="sample_data/pretrained" \
  --conf spark.jsl.settings.storage.cluster_tmp_dir="sample_data/storage" \
  --packages com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3
```

**pyspark:**

```sh
pyspark \
  --driver-memory 16g \
  --conf spark.driver.maxResultSize=0 \
  --conf spark.serializer=org.apache.spark.serializer.KryoSerializer
  --conf spark.kryoserializer.buffer.max=2000M \
  --conf spark.jsl.settings.pretrained.cache_folder="sample_data/pretrained" \
  --conf spark.jsl.settings.storage.cluster_tmp_dir="sample_data/storage" \
  --packages com.johnsnowlabs.nlp:spark-nlp_2.12:3.2.3
```

**Databricks:**

On a new cluster or existing one you need to add the following to the `Advanced Options -> Spark` tab:

```bash
spark.kryoserializer.buffer.max 2000M
spark.serializer org.apache.spark.serializer.KryoSerializer
spark.jsl.settings.pretrained.cache_folder dbfs:/PATH_TO_CACHE
spark.jsl.settings.storage.cluster_tmp_dir dbfs:/PATH_TO_STORAGE
spark.jsl.settings.annotator.log_folder dbfs:/PATH_TO_LOGS
```

NOTE: If this is an existing cluster, after adding new configs or changing existing properties you need to restart it.

### S3 Integration

In Spark NLP we can define S3 locations to:
- Export log files of training models
- Store tensorflow graphs used in `NerDLApproach`

**Logging:**

To configure S3 path for logging while training models. We need to set up AWS credentials as well as an S3 path

```bash
spark.conf.set("spark.jsl.settings.annotator.log_folder", "s3://my/s3/path/logs")
spark.conf.set("spark.jsl.settings.aws.credentials.access_key_id", "MY_KEY_ID")
spark.conf.set("spark.jsl.settings.aws.credentials.secret_access_key", "MY_SECRET_ACCESS_KEY")
spark.conf.set("spark.jsl.settings.aws.s3_bucket", "my.bucket")
spark.conf.set("spark.jsl.settings.aws.region", "my-region")
```

Now you can check the log on your S3 path defined in *spark.jsl.settings.annotator.log_folder* property.
Make sure to use the prefix *s3://*, otherwise it will use the default configuration.

**Tensorflow Graphs:**

To reference S3 location for downloading graphs. We need to set up AWS credentials

```bash
spark.conf.set("spark.jsl.settings.aws.credentials.access_key_id", "MY_KEY_ID")
spark.conf.set("spark.jsl.settings.aws.credentials.secret_access_key", "MY_SECRET_ACCESS_KEY")
spark.conf.set("spark.jsl.settings.aws.region", "my-region")
```

**MFA Configuration:**

In case your AWS account is configured with MFA. You will need first to get temporal credentials and add session token to the configuration as shown in the examples below
For logging:

```bash
spark.conf.set("spark.jsl.settings.aws.credentials.session_token", "MY_TOKEN")
```

An example of a bash script that gets temporal AWS credentials can be found [here](https://github.com/JohnSnowLabs/spark-nlp/blob/master/scripts/aws_tmp_credentials.sh)
This script requires three arguments:

```bash
./aws_tmp_credentials.sh iam_user duration serial_number
```

## Pipelines and Models

### Pipelines

**Quick example:**

```scala
import com.johnsnowlabs.nlp.pretrained.PretrainedPipeline
import com.johnsnowlabs.nlp.SparkNLP

SparkNLP.version()

val testData = spark.createDataFrame(Seq(
(1, "Google has announced the release of a beta version of the popular TensorFlow machine learning library"),
(2, "Donald John Trump (born June 14, 1946) is the 45th and current president of the United States")
)).toDF("id", "text")

val pipeline = PretrainedPipeline("explain_document_dl", lang="en")

val annotation = pipeline.transform(testData)

annotation.show()
/*
import com.johnsnowlabs.nlp.pretrained.PretrainedPipeline
import com.johnsnowlabs.nlp.SparkNLP
2.5.0
testData: org.apache.spark.sql.DataFrame = [id: int, text: string]
pipeline: com.johnsnowlabs.nlp.pretrained.PretrainedPipeline = PretrainedPipeline(explain_document_dl,en,public/models)
annotation: org.apache.spark.sql.DataFrame = [id: int, text: string ... 10 more fields]
+---+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+
| id|                text|            document|               token|            sentence|             checked|               lemma|                stem|                 pos|          embeddings|                 ner|            entities|
+---+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+
|  1|Google has announ...|[[document, 0, 10...|[[token, 0, 5, Go...|[[document, 0, 10...|[[token, 0, 5, Go...|[[token, 0, 5, Go...|[[token, 0, 5, go...|[[pos, 0, 5, NNP,...|[[word_embeddings...|[[named_entity, 0...|[[chunk, 0, 5, Go...|
|  2|The Paris metro w...|[[document, 0, 11...|[[token, 0, 2, Th...|[[document, 0, 11...|[[token, 0, 2, Th...|[[token, 0, 2, Th...|[[token, 0, 2, th...|[[pos, 0, 2, DT, ...|[[word_embeddings...|[[named_entity, 0...|[[chunk, 4, 8, Pa...|
+---+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+--------------------+
*/

annotation.select("entities.result").show(false)

/*
+----------------------------------+
|result                            |
+----------------------------------+
|[Google, TensorFlow]              |
|[Donald John Trump, United States]|
+----------------------------------+
*/
```

#### Please check out our Models Hub for the full list of [pre-trained pipelines](https://nlp.johnsnowlabs.com/models) with examples, demos, benchmarks, and more

### Models

**Some selected languages:** `Afrikaans, Arabic, Armenian, Basque, Bengali, Breton, Bulgarian, Catalan, Czech, Dutch, English, Esperanto, Finnish, French, Galician, German, Greek, Hausa, Hebrew, Hindi, Hungarian, Indonesian, Irish, Italian, Japanese, Latin, Latvian, Marathi, Norwegian, Persian, Polish, Portuguese, Romanian, Russian, Slovak, Slovenian, Somali, Southern Sotho, Spanish, Swahili, Swedish, Tswana, Turkish, Ukrainian, Zulu`

**Quick online example:**

```python
# load NER model trained by deep learning approach and GloVe word embeddings
ner_dl = NerDLModel.pretrained('ner_dl')
# load NER model trained by deep learning approach and BERT word embeddings
ner_bert = NerDLModel.pretrained('ner_dl_bert')
```

```scala
// load French POS tagger model trained by Universal Dependencies
val french_pos = PerceptronModel.pretrained("pos_ud_gsd", lang="fr")
// load Italain LemmatizerModel
val italian_lemma = LemmatizerModel.pretrained("lemma_dxc", lang="it")
````

**Quick offline example:**

- Loading `PerceptronModel` annotator model inside Spark NLP Pipeline

```scala
val french_pos = PerceptronModel.load("/tmp/pos_ud_gsd_fr_2.0.2_2.4_1556531457346/")
      .setInputCols("document", "token")
      .setOutputCol("pos")
```

#### Please check out our Models Hub for the full list of [pre-trained models](https://nlp.johnsnowlabs.com/models) with examples, demo, benchmark, and more

## Offline

Spark NLP library and all the pre-trained models/pipelines can be used entirely offline with no access to the Internet. If you are behind a proxy or a firewall with no access to the Maven repository (to download packages) or/and no access to S3 (to automatically download models and pipelines), you can simply follow the instructions to have Spark NLP without any limitations offline:

- Instead of using the Maven package, you need to load our Fat JAR
- Instead of using PretrainedPipeline for pretrained pipelines or the `.pretrained()` function to download pretrained models, you will need to manually download your pipeline/model from [Models Hub](https://nlp.johnsnowlabs.com/models), extract it, and load it.

Example of `SparkSession` with Fat JAR to have Spark NLP offline:

```python
spark = SparkSession.builder \
    .appName("Spark NLP")\
    .master("local[*]")\
    .config("spark.driver.memory","16G")\
    .config("spark.driver.maxResultSize", "0") \    
    .config("spark.kryoserializer.buffer.max", "2000M")\
    .config("spark.jars", "/tmp/spark-nlp-assembly-3.2.3.jar")\
    .getOrCreate()
```

- You can download provided Fat JARs from each [release notes](https://github.com/JohnSnowLabs/spark-nlp/releases), please pay attention to pick the one that suits your environment depending on the device (CPU/GPU) and Apache Spark version (2.3.x, 2.4.x, and 3.x)
- If you are local, you can load the Fat JAR from your local FileSystem, however, if you are in a cluster setup you need to put the Fat JAR on a distributed FileSystem such as HDFS, DBFS, S3, etc. (i.e., `hdfs:///tmp/spark-nlp-assembly-3.2.3.jar`)

Example of using pretrained Models and Pipelines in offline:

```python
# instead of using pretrained() for online:
# french_pos = PerceptronModel.pretrained("pos_ud_gsd", lang="fr")
# you download this model, extract it, and use .load
french_pos = PerceptronModel.load("/tmp/pos_ud_gsd_fr_2.0.2_2.4_1556531457346/")\
      .setInputCols("document", "token")\
      .setOutputCol("pos")

# example for pipelines
# instead of using PretrainedPipeline
# pipeline = PretrainedPipeline('explain_document_dl', lang='en')
# you download this pipeline, extract it, and use PipelineModel
PipelineModel.load("/tmp/explain_document_dl_en_2.0.2_2.4_1556530585689/")
```

- Since you are downloading and loading models/pipelines manually, this means Spark NLP is not downloading the most recent and compatible models/pipelines for you. Choosing the right model/pipeline is on you
- If you are local, you can load the model/pipeline from your local FileSystem, however, if you are in a cluster setup you need to put the model/pipeline on a distributed FileSystem such as HDFS, DBFS, S3, etc. (i.e., `hdfs:///tmp/explain_document_dl_en_2.0.2_2.4_1556530585689/`)

## Examples

Need more **examples**? Check out our dedicated [Spark NLP Showcase](https://github.com/JohnSnowLabs/spark-nlp-workshop) repository to showcase all Spark NLP use cases!

Also, don't forget to check [Spark NLP in Action](https://nlp.johnsnowlabs.com/demo) built by Streamlit.

### All examples: [spark-nlp-workshop](https://github.com/JohnSnowLabs/spark-nlp-workshop)

## FAQ

[Check our Articles and Videos page here](https://nlp.johnsnowlabs.com/learn)

## Citation

We have published a [paper](https://www.sciencedirect.com/science/article/pii/S2665963.2.100063) that you can cite for the Spark NLP library:

```bibtex
@article{KOCAMAN2021100058,
    title = {Spark NLP: Natural language understanding at scale},
    journal = {Software Impacts},
    pages = {100058},
    year = {2021},
    issn = {2665-9638},
    doi = {https://doi.org/10.1016/j.simpa.2021.100058},
    url = {https://www.sciencedirect.com/science/article/pii/S2665963.2.100063},
    author = {Veysel Kocaman and David Talby},
    keywords = {Spark, Natural language processing, Deep learning, Tensorflow, Cluster},
    abstract = {Spark NLP is a Natural Language Processing (NLP) library built on top of Apache Spark ML. It provides simple, performant & accurate NLP annotations for machine learning pipelines that can scale easily in a distributed environment. Spark NLP comes with 1100+ pretrained pipelines and models in more than 192+ languages. It supports nearly all the NLP tasks and modules that can be used seamlessly in a cluster. Downloaded more than 2.7 million times and experiencing 9x growth since January 2020, Spark NLP is used by 54% of healthcare organizations as the world’s most widely used NLP library in the enterprise.}
    }
}
```

## Contributing

We appreciate any sort of contributions:

- ideas
- feedback
- documentation
- bug reports
- NLP training and testing corpora
- Development and testing

Clone the repo and submit your pull-requests! Or directly create issues in this repo.

## Contact

nlp@johnsnowlabs.com

## John Snow Labs

[http://johnsnowlabs.com](http://johnsnowlabs.com)
