# Complex Query Synthesis for Enhanced Information Retrieval

## Team Members
Daksha Ladia, Snigdha Ansu, Vasileios Vittis

## Abstract

This project introduces a novel approach that bridges the gap between user intent and document relevance using pseudo-query generation and large language models (LLMs). By chunking documents into passages to create pseudo-queries and transforming user queries into detailed, multifaceted queries with LLMs, we compare them on a per-document basis to rank and retrieve the most relevant results.

## System Overview

Here is an overview of the system pipeline used in our project:
![System Pipeline](docs/system_pipeline.png)

## Problem Statement

Current information retrieval systems often fail to capture implicit context necessary for producing relevant documents, due to limitations of short, ambiguous queries. This project addresses these complexities by generating long, context-rich queries to improve retrieval accuracy.

## Approach

The project's methodology includes:

- **Pseudo-Query Generation:** Segmenting documents into chunks to generate contextually rich pseudo-queries using generative models.
- **Training:** Using autoregressive models to train on generated pseudo-queries and corresponding documents.
- **Inference and Retrieval:** Utilizing trained models to generate queries and retrieve relevant documents.

### Detailed Steps

1. **Document Segmentation:** Documents are segmented into chunks.
2. **Generative Modeling:** A pretrained model (e.g., FLAN-T5-Large) generates pseudo-queries from document chunks.
3. **Diversity Filtering:** Redundant queries are filtered out to maintain query quality.
4. **Model Training:** An autoregressive model maps queries to the best matching pseudo-queries.
5. **Document Retrieval:** The system retrieves documents based on query-pseudo-query relevance scores.

## Experiments

The project was evaluated using two datasets:

- **NFCorpus:** Focuses on medical information retrieval.[Link](https://huggingface.co/datasets/BeIR/nfcorpus)
- **SciFact:** Tailored for scientific document retrieval.[Link](https://huggingface.co/datasets/BeIR/scifact)

### Evaluation Metrics

We employed metrics such as Precision, Recall, and NDCG to assess the performance of our retrieval system.

## Results

Our approach has shown significant improvements over traditional retrieval methods, particularly in aligning complex queries with relevant document content.

## Code and Resources

Below are links to the project resources, organized by dataset and methodology:

## NFCorpus Dataset

- [T5-CPQG + GPT 4o-mini (WordNet + Pretrained LLM)](https://colab.research.google.com/drive/1Vk8GkSuac6HlrY2_W_d4ikQ6Xuu-lQaw#scrollTo=TMJDDTG57UPA)
- T5-CPQG + GPT 2.0 Fine Tuned

  - [Model Fine Tuned:](https://colab.research.google.com/drive/1NLgZDXeqPnpQy2ipCKW0uLfcD0H2awzj?usp=sharing)
  - [T5-CPQG + GPT 2.0 Fine Tuned +Ranking:](https://colab.research.google.com/drive/1pL0_aK8dUptPMA9TOiVy02MR_CEQygw7#scrollTo=qkusKjh2OEw1)

- [T5-CPQG + Cross Encoder Fine Tuned]
  - [Cross Encoder Fine-Tuned](https://colab.research.google.com/drive/1bSoaOT0wccUJYCVbKfM9GvqVGKNMkkbp)
  - [T5-CPQG + Cross Encoder Fine Tuned + Ranking:](https://colab.research.google.com/drive/1X-VIqsA9dbOteNlDECIXEnoLPWiDJGDk)
- [T5-CPQG + T5-small Fine Tuned](https://colab.research.google.com/drive/1h93vjO2kAHgOP4xvp-T4aufkzs2Jt9d2#scrollTo=2RLl47RBzTLf)

### SciFact Dataset

- [T5-CPQG + GPT 4o-mini (WordNet + Pretrained LLM)](https://colab.research.google.com/drive/12ai6XCKMS7wTzO-Gcy9KCE3B-K5V302X#scrollTo=w5ghpZV5Hhas)
- T5-CPQG + Cross Encoder Fine Tuned
  - [Model Fine Tuning](https://colab.research.google.com/drive/1zDOG-6qS_0-E_7OoSeJ_eiw9aJGjdUME?usp=sharing)
  - [T5-CPQG + Cross Encoder Fine Tuned + Ranking: ](https://colab.research.google.com/drive/1Z6_9Qsm8AbcK9KoYJdNrbw-H3JKGLYVf)
- T5-CPQG + GPT 2.0 Fine Tuned
  - [GPT 2.0 Fine Tuned](https://colab.research.google.com/drive/1DGgQTvS_uzl0fnqSKsryhobW3v1ZrGcP?usp=sharing)
  - [T5-CPQG + GPT 2.0 Fine Tuned + Ranking ](https://colab.research.google.com/drive/1l3NHGRGCk6tiOX7x770KP3n3d9jOSEh-)
- [T5-CPQG + T5-small Fine Tuned](https://colab.research.google.com/drive/14Bxt2JI1Og46m8_8fRytwC631iIViKkM#scrollTo=zjZwwZ_CcHeR)

### Baselines

- [BM25, Dense Retrieval, QOQA + BM25, QOQA + Dense Retrieval baseline implementation on NFCorpus DataSet](https://colab.research.google.com/drive/1O7w5PHXLUYObvlbr6oYue-lcNG0lBbVD?usp=sharing)
- [BM25, Dense Retrieval, QOQA + BM25, QOQA + Dense Retrieval baseline implementation on SciFact DataSet](https://colab.research.google.com/drive/1s0vHwXiw9W9cNTZid3MS2VbIhgHZv3gk?usp=sharing)

Data files used for experimenation can be found in this folder :
https://drive.google.com/drive/folders/191D9QMsCVku2V1aCE0ZlkWvDqCzXlWQ3
