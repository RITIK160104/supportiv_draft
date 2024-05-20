
# Medical Domain-Specific Question Answering System

## Overview
This repository contains the implementation of a medical domain-specific question answering system, tailored for a non-contextual dataset. The goal of this project is to develop an efficient solution for accurately answering questions based on the provided dataset.

## Approach Towards the Problem Statement
Initially, the objective was to implement an Information Retrieval system using the DPR and BM25 technique, utilizing the "question" and "answer" columns of the dataset. However, due to computational constraints, this approach was abandoned.

An alternative strategy was adopted, involving initial data preprocessing using NLTK for stopwords removal, lemmatization, and normalization. The dataset was then split into train and test sets and tokenized using BERT, with an option to utilize BioBERT for domain-specific tasks. Subsequently, a tensor dataset was constructed, comprising various input features for training. A DataLoader for batch training was established.

The code loads a pre-trained BERT-based question-answering (QA) model and defines an AdamW optimizer with a specific learning rate. It enters a training loop for a specified number of epochs, performing forward and backward passes through the model to update the loss using gradient descent optimization.

## Metrics Used
- **F1 Score**: Chosen for its ability to balance precision and recall, which is crucial for tasks like question answering where both false positives and false negatives need to be considered.
- **Exact Match (EM)**: Selected to measure the percentage of predictions that exactly match the ground truth answers, essential for assessing the model's precision in providing correct answers without deviations.

## For Example Interactions
Example interactions with the system can be found at the bottom of the implementation file.

## Model Performance
Due to limited computational resources, the model could not be trained on a higher number of examples. However, the outlined approach towards the solution can still be considered and further optimized.

## Potential Enhancements
A potential two-step enhancement process could be implemented. Firstly, the named entity recognition (NER) could be applied to the question column. Subsequently, the pre-trained language model (LLM) could process the identified entities to generate an output. Secondly, both the true and predicted outputs could be fine-tuned to further minimize losses, ultimately leading to better performance of metrics.
