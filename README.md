# Efficient Query Execution for RAG using Factorized Embeddings

Retrieval Augmented Generation (RAG) pipelines often store high-dimensional embeddings (768D from transformer-based models) for millions of documents, which can lead to memory bottlenecks and slow retrieval times. By factorizing these embeddings into low-rank matrices, we aim to reduce memory and speed up search. However, naive compression can destroy semantic relationships. We aim to systematically tests factorization methods to see which preserve retrieval and generation quality the best.

To replicate this code, please obtain the necessary documents and queries by running our data download script, which fetches a dataset from BEIR (SciFact is the default one provded) and any additional data required for generation using MTEB or USEB. After that, please use the main experiment notebook which loads the documents and queries with their respective ground-truth relevance judgments. The notebook encodes the document and quaries into high-dimensional vectors and applies the factorization methods to reduce the dimension, and indexes the factorized embeddings in FAISS for nearest-neighbor retrieval. 

After each method is evaluated, performance metrics, such as recall and query latency, are sent to the results folder.

# Status
**In Progress**: The code is still being refined.

For any questions, please contact aneesh.durai@berkeley.edu.
