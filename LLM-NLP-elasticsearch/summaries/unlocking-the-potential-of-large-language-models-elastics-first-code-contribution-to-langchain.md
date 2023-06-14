
## Unlocking the potential of large language models: Elastic's first code contribution to LangChain
The [blog post](https://www.elastic.co/blog/large-language-models-elastic-code-langchain)  discusses synergy between LangChain and Elastic to generate embeddings using Elasticsearch models.


**LangChain**
A library/framework to integrate with LLMs (LLM agnostic) and combine them with other sources of computation (e.g. the ability to perform complex maths) or knowledge (e.g. real-time inventory) to create applications.
   * provides a standard interface for LLMs and facilitating their integration with other tools
   * makes developing applications that can answer questions over specific documents, power chatbots, and even create decision-making agents
   * LLM can be hosted by a third party like OpenAI, or own open-source model in hosted in own tenant


**Elasticsearch and LangChain**
1. Elasticsearch Relevance Engine™ (ESRE™) to create highly relevant AI search applications. ESRE can store, search, and analyze large volumes of data quickly and in near real-time. Hybrid scoring with BM25, approximate k-nearest neighbors (kNN), or Elastic’s Learned Sparse Encoder model, adds a layer of flexibility and precision


2. Elasticsearch prvides efficient storage and search and supplies LLMs with vital context: real-time information, proprietary data, and other knowledge sources to generate more accurate and contextually relevant responses.


3. Elasticsearch stores the chat history between users and LLMs, which is useful in applications like chatbots, where the context of previous interactions is crucial in shaping responses, making conversations more coherent and personalized over time.


**Module elasticsearch_embeddings.py**
* first contribution from Elastic to LangChain
* ElasticsearchEmbeddings class enables users to generate embeddings for documents and query texts using a model deployed in an Elasticsearch cluster
* interface to interact with Elasticsearch’s machine learning (ML) client, simplifies the process of generating embeddings, and supports custom input text field names


