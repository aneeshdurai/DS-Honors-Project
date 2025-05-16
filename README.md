# Accelerating Retrieval with Spectral-Semantic Randomized Embedding Compression

This repository contains code and experiments for the project conducted as part of **UC Berkeley's Data Science Honors Program**.

**Advisor:** Prof. James Demmel

## Project Overview

Retrieval-Augmented Generation (RAG) pipelines typically rely on storing high-dimensional embeddings (e.g., 768-dimensional vectors from transformer-based models) for millions of documents. This presents challenges related to memory usage and retrieval latency.

This project explores embedding compression using Randomized Numerical Linear Algebra (RandNLA) techniques, specifically randomized low-rank factorizations. The aim is to reduce memory and speed up retrieval while preserving spectral and semantic structure to avoid harming retrieval accuracy.


## Repository Structure

Each experiment is encapsulated in an individual ipynb notebook, with a shared setup for dataset downloading, embedding generation using the MPNET model, and evaluation using retrieval metrics.

## Setup Instructions

To replicate, please do the following.

Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

All notebooks will automatically download the required datasets from BEIR.

   ```python
   DATASET_URLS = {
       "scifact": "https://public.ukp.informatik.tu-darmstadt.de/thakur/BEIR/datasets/scifact.zip",
       "scidocs": "https://public.ukp.informatik.tu-darmstadt.de/thakur/BEIR/datasets/scidocs.zip",
       "fiqa": "https://public.ukp.informatik.tu-darmstadt.de/thakur/BEIR/datasets/fiqa.zip",
       "nfcorpus": "https://public.ukp.informatik.tu-darmstadt.de/thakur/BEIR/datasets/nfcorpus.zip"
   }
   ```

To add another dataset, simply add the dataset's name and URL to `DATASET_URLS`, and include it in the `DATASET_LIST` variable in the corresponding cell.

We use MPNET (768-dimensional encoder) for all experiments to ensure consistency. You may modify the `EMBED_MODELS` dictionary to use a different embedding model, although this may affect comparability.

## Running the Experiments

Each notebook is executable end-to-end. We recommend using Kaggle Notebooks with a **P100 GPU** for best performance.

## Contact

For questions or collaborations, feel free to reach out: aneesh.durai@berkeley.edu.

