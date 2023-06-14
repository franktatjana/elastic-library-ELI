# ChatGPT Elasticsearch: Enabling OpenAI to Work with Private Data in Elasticsearch

The [blog post](https://www.elastic.co/de/blog/chatgpt-elasticsearch-openai-meets-private-data) explains how to connect OpenAI's ChatGPT with proprietary data store for Q&A exemplified with Elasticsearch documentation.  The key idea is to illustrate how to use Elastic with OpenAI’s GPT model to build a response and return context-relevant content to users.

---

**What is ChatGPT and its limitations?** 
Generative Pre-trained Transformer (**GPT**) is a type of large language model (**LLM**) and a prominent framework for generative artificial intelligence (**GAI**). The concept and model were introduced in 2018 by  OpenAI. LLM are pre-trained on vast amounts of data and are capable of understanding context, generating relevant responses.

- ChatGPT is trained on data up to September 2021 and is unaware of recent events.
- ChatGPT can  hallucinate in responses with overconfidence, which results in incorrect answers or misleading information, needs cross-checking.
- ChatGPT lacks knowledge about domain - a user's unique knowledge base.

---
**Why Elasticsearch?**
- Elasticsearch as a search engine delivers relevant document retrieval, supports traditional keyword and text-based search (BM25),  an AI-ready vector search with exact match and approximate kNN (k-Nearest Neighbor) or hybrid search (BM25 + kNN).
   * *BM25 [Similarity Module](https://www.elastic.co/guide/en/elasticsearch/reference/current/index-modules-similarity.html)*
   * *A k-nearest neighbor (kNN) search finds the k nearest vectors to a query vector, as measured by a similarity metric. To run a kNN search, you must be able to convert your data into meaningful vector values. Elasticsearch supports Exact, brute-force kNN using a script_score query with a vector function and Approximate kNN using the knn search option. Approximate kNN offers lower latency at the cost of slower indexing and imperfect accuracy. Exact, brute-force kNN guarantees accurate results but doesn’t scale well with large datasets. [K-nearest neighbor (kNN)](https://www.elastic.co/guide/en/elasticsearch/reference/current/knn-search.html)*


- Elasticsearch has robust API for integration with other services, third-party tools and platforms to create customized search solutions.


- Elasticsearch provides domain-relevant specific documents for ChatGPT to use in its response to ensure factual, contextually relevant, and up-to-date answers.
---

**How to build a Q&A with python backend?**
1. Python interface accepts user questions.
2. Search request is sent to Elasticsearch combining BM25 and kNN search on indexed Elasticsearch Docs. 
3. Documentation body and original url are returned to python.
4. API call is made to OpenAI ChatCompletion: **Prompt: "answer this question <question> using only this document <body_content from top search result>"** to ensure the ChatGPT model only uses information from the body.
5. Generated response is returned to python.
6. Python adds on original documentation source url to generated response and prints it to the screen for the user.

---
**Technical setup**
1. Elasticsearch cluster with ML activated to load an embedding model into Elasticsearch to generate vectors for blog titles (docs) and for  user’s search questions (incoming requests),  all-distilroberta-v1 model trained by SentenceTransformers and hosted on the Hugging Face model hub 
2. Eland python library used as a bridge to load the model into Elasticsearch from the Hugging Face model hub so it can be deployed on machine learning nodes for inference use;
3. Google Colab, a cloud-based Jupyter notebook environment, allows editING and running a specified notebook. To download and deploy the ML model change parameter hf_model_id='sentence-transformers/all-distilroberta-v1'(copy model name from Hugging Face) and enter cloud ID and credentials.
   * [python notebook](https://github.com/jeffvestal/ElasticDocs_GPT/blob/main/load_embedding_model.ipynb)
   * [Eland](https://github.com/elastic/eland#readme) 
3. Ingest content with a web crawler (example with elasticsearch guides) and use an ingest pipeline to generate vectors for the doc titles to run kNN search on the title field vectors.
4. Create account in https://platform.openai.com, get an API key.
5. Install required python libraries, set authentication and connection env variables, run the streamlit program run elasticdocs_gpt.py
6. Samples for queries:
   - Show me the API call for an inference processor
   - How do I add a new integration to elastic agent
   - How how to build a boat (info not available)
---