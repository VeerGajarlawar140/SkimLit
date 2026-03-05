# SkimLit – Medical Abstract Sentence Classification

An NLP project inspired by the paper **"Neural Networks for Joint Sentence Classification in Medical Paper Abstracts"**.  
The goal of this project is to build a deep learning model capable of classifying sentences from medical research abstracts into structured categories, enabling faster reading and understanding of scientific literature.

This project implements a **multi-input neural network architecture** that combines semantic, character-level, and positional embeddings to improve sentence classification performance.

📊 **Final Accuracy:** 86.7%  
🧠 **Model Type:** Multi-input Deep Learning Model

---

## Project Overview

Medical research papers typically contain structured abstracts with sentences belonging to categories such as objectives, methods, results, and conclusions. Automatically classifying these sentences can help researchers quickly skim through large volumes of scientific literature.

The objective of this project was to build a neural network capable of classifying sentences into **five structured categories**:

- Background
- Objective
- Methods
- Results
- Conclusions

The project explores how combining multiple levels of text representation can improve classification performance.

---

## Model Architecture

The final model uses a **multi-input architecture** integrating three different representations of text:

1. **Universal Sentence Encoder (USE) embeddings**
2. **Character-level embeddings**
3. **Positional embeddings**

These inputs are processed separately and then concatenated before the final classification layer.

### Input Streams

**1. Sentence Embeddings**

- Pretrained **Universal Sentence Encoder**
- Captures semantic meaning of sentences

**2. Character Embeddings**

- Character-level tokenization
- Helps capture subword information and spelling patterns

**3. Positional Embeddings**

- Encodes the **position of a sentence within the abstract**
- Provides contextual information about document structure

The model is implemented using the **TensorFlow Functional API**, enabling flexible multi-input architecture design.

---

## Data Pipeline

The training pipeline was built using **TensorFlow's `tf.data` API** to efficiently handle multiple input streams.

Key features:

- Efficient data loading and batching
- Support for multiple embedding inputs
- Optimized preprocessing for large NLP datasets

This pipeline ensured smooth training and improved performance.

---

## Baseline Models

To evaluate the effectiveness of the deep learning model, several baseline approaches were implemented:

### TF-IDF + Naive Bayes

- Traditional NLP pipeline
- Used as a classical machine learning benchmark

### Conv1D Model

- Word embedding based neural network
- Captures local patterns in sentence sequences

These baselines provided a reference point to measure the improvement gained from the multi-input architecture.

---

## Model Performance

| Model | Accuracy |
|------|------|
| TF-IDF + Naive Bayes | Baseline |
| Conv1D Neural Network | Improved baseline |
| **Multi-input SkimLit Model** | **86.7%** |

The integration of **semantic, character-level, and positional embeddings** significantly improved classification performance.

---

## Error Analysis

Extensive error analysis was conducted to better understand model behavior.

This included:

- Identifying commonly misclassified sentence types
- Analyzing confusion between structurally similar categories
- Examining prediction confidence across different classes

These insights helped evaluate model limitations and identify possible improvements.

---

## Tech Stack

**Programming Language**

- Python

**Libraries and Frameworks**

- TensorFlow
- TensorFlow Hub
- NumPy
- Pandas
- Scikit-learn
- Matplotlib

---

## Key Learnings

- Multi-input neural networks can capture different levels of linguistic information effectively.
- Combining **sentence embeddings, character embeddings, and positional information** improves NLP model performance.
- The **TensorFlow Functional API** enables flexible architectures for complex models.
- Proper benchmarking against baseline models is crucial for evaluating improvements.
