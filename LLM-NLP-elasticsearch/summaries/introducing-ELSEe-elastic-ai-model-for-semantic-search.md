
## Introducing Elastic Learned Sparse Encoder: Elastic’s AI model for semantic search
The [blog post](https://www.elastic.co/blog/may-2023-launch-sparse-encoder-ai-model)  describes semantic search OOTB with release 8.8.


* semantic search: search with the intent or meaning of the text, opposed to a lexical match or keyword query; captures relationships between words on the conceptual level, understanding the context and surfacing relevant results based on meanings, instead of simply query terms.


* approximate nearest neighbor search (aKNN):


* embeddings:  vector models


* Reciprocal Rank Fusion (RRF):


* sparse vectors:


* dense vectors:


* vector search:


* challenges with vector search:
   * annotating a number of queries within the domain in which search will be performed
   * in-domain re-training the machine learning (so called “embedding”) model to achieve domain adaptation
   * maintaining the models against drift
   * you may not want to rely on third-party models due to privacy, support, competitiveness, or licensing concerns.


* Elastic’s Learned Sparse Encoder (ELSE) is a retrieval model, sparse-vector representation; captures the semantic relationships between words in the English language, expands search queries to include relevant terms that are not present in the query.
   * better than adding synonyms with lexical scoring (BM25) because it uses this deeper language-scale knowledge to optimize for relevance.
   * context is  factored in to eliminate ambiguity from words that may have different interpretations in different sentences.
   * mitigates the vocabulary mismatch problem ( different people name the same thing or concept differently)
   * outperforms lexical search in 11 out of 12 prominent relevance benchmarks, and the combination of both using hybrid search in all 12 relevance benchmarks
   * no need to fine tune it on your data.
   * outperforms dense vector models when no domain-specific retraining is applied (just click “deploy”)
   * outperforms SPLADE (Sparse Lexical and Expansion Model)
   * licensing (platinum), support, continuity of competitiveness, extensibility ensured by Elastic
   * optimal performance due to Elasticsearch, Lucene-based inverted index
   * fewer dimensions are activated than in dense representations, and they often directly map to words, in contrast with the opaqueness of dense representations, clearly show you which words non-existing in the query triggered the results


* performance when using ELSE sparse retrieval model:
- sparse vectors compress well
- vector similarity is a less computationally intensive operation, due to inverted index optimization
- the query performance and index size require fewer resources compared to the typical dense vector index.
- vector search, sparse or dense, has a larger memory footprint and time complexity compared to lexical search universally, regardless of the platform


* hybrid search:
- the best results are obtained from a combo of different ranking methods.
- combine vector search — with or without the new retrieval model — with Elastic’s lexical search through our streamlined search APIs, linearly combining normalized scores from each method
- eliminating any search science effort toward fine tuning based on the distribution of scores, data, queries, etc
- Reciprocal Rank Fusion (RRF) eliminates any search science effort toward fine tuning based on the distribution of scores, data, queries, etc.
- RRF available with third-party models in Elastic, next integration of ELSE and lexical search
- currently in tech preview, input is limited to 512 tokens, which is approximately the first 300–400 words in each field going through an inference pipeline.
- next handling longer documents and overall optimizations to further boost performance in a future version


* how to:
- activate ML in deployment
- got to Machine Learning at the trained models view or Enterprise Search





