# Semantic NLP Filtering for Deep Learning Papers in Virology/Epidemiology

## Overview
This project filters and classifies academic papers from PubMed that apply **deep learning** techniques within the fields of **virology** and **epidemiology**. The solution processes an initial dataset of **11,450 records** to identify papers using neural network-based methods, helping researchers streamline their review process by isolating relevant studies.

The solution leverages **DistilBERT**, a lightweight transformer-based NLP model, to perform semantic filtering, ensuring efficient processing on a Google Colab where I have been actually used.

## Task Components

The solution consists of three main components:

- **Semantic Filtering**: Identifies papers relevant to deep learning in virology or epidemiology.
- **Classification**: Categorizes each filtered paper based on method type: `text mining`, `computer vision`, `both`, or `other`.
- **Method Extraction**: Extracts specific deep learning techniques used in each relevant paper.

## Solution Details

### 1. **Semantic NLP Filtering**

   - **Approach**: The core of the filtering process uses `DistilBERT` embeddings to semantically understand each paper’s abstract and title. By encoding abstracts, I have determined if the paper aligns with target fields (virology/epidemiology) and methods (deep learning/neural networks).
   - **Effectiveness**: This approach surpasses basic keyword matching by capturing the **context** of terms. For instance, it recognizes "neural network-based virus classification" as relevant to deep learning in virology even if "deep learning" or "virology" is not explicitly mentioned. This improves precision by reducing false positives and negatives commonly encountered with simple keyword filtering.

### 2. **Classification by Method Type**

   - **Methodology**: For each filtered paper, I classified its approach based on specific keywords found within the abstract:
     - **Text Mining**: Papers mentioning terms like “text mining” or “natural language processing.”
     - **Computer Vision**: Papers with keywords such as “image processing” or “computer vision.”
     - **Both**: Papers mentioning both text mining and computer vision.
     - **Other**: Papers not falling clearly into either category.

   - **Outcome**: This classification enables users to focus on studies most relevant to their specific needs within virology and epidemiology.

### 3. **Method Extraction**

   - **Process**: I have performed additional semantic analysis to identify specific deep learning techniques used, such as "CNN," "LSTM," or "transformer models." This extraction provides a concise reference to methodologies in each study, expediting the review of potential approaches.

## Resulting Dataset Statistics

After processing, the dataset statistics are as follows:

- **Total Papers Initially**: 11,450
- **Filtered Papers**: *307* (papers that meet criteria for virology/epidemiology and deep learning)
- **Classification Distribution**:
  - **Text Mining**: *7*
  - **Computer Vision**: *2*
  - **Transformer/Generative**: *9*
  - **Both**: *1*
  - **Other**: *288*

These results show the effectiveness of this approach in narrowing down the dataset to highly relevant papers.
