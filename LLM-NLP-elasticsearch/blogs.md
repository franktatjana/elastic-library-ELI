# Resources about OpenAI and Elastic Intergation


## Summary
A collection of blogs around OpenAI and ChatGPT. Blogs describe how to build own Q&A system on the basis of information indexed into elasticsearch, create own plugin with example of elasticsearch documentation, apply capabilities to generate code, analyze security incidents and opentelemetry data.


---


## Elastic Stack Capabilities
* [Elastic Machine Learning](https://www.elastic.co/what-is/elasticsearch-machine-learning) to identify unusually slow response times directly from the APM service map, to discover unusual behavior and proactively address security threats, to customize anomaly detection for any type of data with easy-to-use wizard-based workflows, to enhance search experiences by enriching the ingested data with predictions, etc.


* [Elastic NLP](https://www.elastic.co/guide/en/machine-learning/current/ml-nlp.html) to analyze natural language data and make predictions


* [Vector Search](https://www.elastic.co/what-is/vector-search) to find similar data using approximate nearest neighbor (ANN) algorithms


* [Enterprise Search with ML](https://www.elastic.co/enterprise-search/machine-learning) to integrate with Generative AI and power semantic and image search, personalization, and question answering to measurably improve search experiences


* [Elasticsearch Relevance Engine™ (ESRE)](https://www.elastic.co/enterprise-search/generative-ai) to apply semantic search with superior relevance out of the box (without domain adaptation), integrate with external large language models (LLMs), implement hybrid search, and use third-party or your own transformer models.


* [Semantic Search with ELSER](https://www.elastic.co/guide/en/elasticsearch/reference/current/semantic-search-elser.html) Elastic Learned Sparse EncodeR - or ELSER - is an NLP model trained by Elastic that enables you to perform semantic search by using sparse vector representation. Instead of literal matching on search terms, semantic search retrieves results based on the intent and the contextual meaning of a search query.


* [Generative AI connector](https://www.elastic.co/guide/en/kibana/master/gen-ai-action-type.html) uses axios to send a POST request to an OpenAI provider, either OpenAI or Azure OpenAI. The connector uses the run connector API to send the request.


---
## Referenced Blogs


### ChatGPT Integration
* 19.04.2023  [ChatGPT Elasticsearch: Enabling OpenAI to Work with Private Data](https://www.elastic.co/de/blog/chatgpt-elasticsearch-openai-meets-private-data), Jeff Vestal | [Summary](#chatgpt-elasticsearch-enabling-openai-to-work-with-private-data-in-elasticsearch)


* 15.05.2023 [ChatGPT and Elasticsearch: a plugin to use ChatGPT with your Elastic data](https://www.elastic.co/blog/chatgpt-elasticsearch-plugin-elastic-data), Baha Azarmi | [Summary](#chatgpt-and-elasticsearch-a-plugin-to-use-chatgpt-with-your-elastic-data)


* 16.05.2023 [How to use Elasticsearch to prompt ChatGPT with natural language](https://www.elastic.co/blog/elasticsearch-prompt-chatgpt-natural-language), Enrico Zimuel | [Summary](#how-to-use-elasticsearch-to-prompt-chatgpt-with-natural-language)


* 18.05.2023 [Privacy-first AI search using LangChain and Elasticsearch](https://www.elastic.co/blog/privacy-first-ai-search-langchain-elasticsearch), Dave Erickson | [Summary](#privacy-first-ai-search-using-langchain-and-elasticsearch)


* 23.05.2023 [Accessing machine learning models in Elastic](https://www.elastic.co/blog/may-2023-launch-machine-learning-models), Bernhard Suhm, Josh Devins  | [Summary](#accessing-machine-learning-models-in-elastic)


* 23.05.2023 [Introducing Elasticsearch Relevance Engine™ — Advanced search for the AI revolution](https://www.elastic.co/blog/may-2023-launch-announcement), Matt Riley  | [Summary](#introducing-elasticsearch-relevance-engine-advanced-search-for-the-ai-revolution)


* 23.05.2023  [Improving information retrieval in the Elastic Stack: Introducing Elastic Learned Sparse Encoder, our new retrieval model](https://www.elastic.co/blog/may-2023-launch-information-retrieval-elasticsearch-ai-model), Thomas Veasey, Quentin Herreros  | [Summary](#introducing-elasticsearch-relevance-engine-advanced-search-for-the-ai-revolution)


* 31.05.2023  [ChatGPT and Elasticsearch: Faceting, filtering, and more context](https://www.elastic.co/blog/chatgpt-elasticsearch-faceting-filtering-more-context), Luca Wintergerst  | [Summary](#chatgpt-and-elasticsearch-faceting-filtering-and-more-context)


* 31.05.2023 [Unlocking the potential of large language models: Elastic's first code contribution to LangChain](https://www.elastic.co/blog/large-language-models-elastic-code-langchain), Jeff Vestal  | [Summary](#unlocking-the-potential-of-large-language-models-elastics-first-code-contribution-to-langchain)


### ChatGPT and Elastic Solutions
**Security**
* 15.03.2023 [Exploring Applications of ChatGPT to Improve Detection, Response, and Understanding in Security](https://www.elastic.co/security-labs/exploring-applications-of-chatgpt-to-improve-detection-response-and-understanding), Mika Ayenson | [Summary](#exploring-applications-of-chatgpt-to-improve-detection-response-and-understanding-in-security)


**Observability**
* 04.04.2023 [Monitoring OpenAI API GPT Models with OpenTelemetry and Elastic](https://www.elastic.co/blog/monitor-openai-api-gpt-models-opentelemetry-elastic), David Hope | [Summary](#monitoring-openai-api-gpt-models-with-opentelemetry-and-elastic)


* 18.05.2023  [Gain insights into Kubernetes errors with Elastic Observability logs and OpenAI](https://www.elastic.co/blog/kubernetes-errors-elastic-observability-logs-openai), Bahubali Shetti | [Summary](#gain-insights-into-kubernetes-errors-with-elastic-observability-logs-and-openai)


### Industy Specific Use Cases
* 24.05.2023  [The power of generative AI for public sector](https://www.elastic.co/blog/generative-ai-public-sector), Leanne Link, Dave Erickson | [Summary](#the-power-of-generative-ai-for-public-sector)


### NLP Foundations
* 27.08.2019  [Text similarity search with vector fields](https://www.elastic.co/blog/text-similarity-search-with-vectors-in-elasticsearch) Julie Tibshirani  | [Summary](#text-similarity-search-with-vector-fields)


* 10.02.2022 [Introduction to modern natural language processing with PyTorch in Elasticsearch](https://www.elastic.co/blog/introduction-to-nlp-with-pytorch-models) Tom Grabowski, Josh Devins  | [Summary](#introduction-to-modern-natural-language-processing-with-pytorch-in-elasticsearch)


* 20.05.2022  [How to deploy NLP: Text Embeddings and Vector Search](https://www.elastic.co/blog/how-to-deploy-nlp-text-embeddings-and-vector-search) Mayya Sharipova  | [Summary](#how-to-deploy-nlp-text-embeddings-and-vector-search)


* 23.05.2023 [Introducing Elastic Learned Sparse Encoder: Elastic’s AI model for semantic search](https://www.elastic.co/blog/may-2023-launch-sparse-encoder-ai-model) Aris Papadopoulos, Gilad Gal | [Summary](#improving-information-retrieval-in-the-elastic-stack-introducing-elastic-learned-sparse-encoder-our-new-retrieval-model)


----


## Repositories
[Elasticsearch ChatGPT for PHP](https://github.com/elastic/elasticsearch-chatgpt-php)


[ElasticGPT_Plugin](https://github.com/elastic/ElasticGPT_Plugin/)


[LangChain ElasticsearchEmbeddings class for generating embeddings using Elasticsearch models](https://github.com/hwchase17/langchain/pull/3401)


----


## ChatGPT Elasticsearch: Enabling OpenAI to Work with Private Data in Elasticsearch
The [blog post](https://www.elastic.co/de/blog/chatgpt-elasticsearch-openai-meets-private-data) explains how to connect OpenAI's ChatGPT with proprietary data store for Q&A exemplified with Elasticsearch documentation.  The key idea is to illustrate how to use Elastic with OpenAI’s GPT model to build a response and return context-relevant content to users.


**What is ChatGPT and its limitations?** 
Generative Pre-trained Transformer (**GPT**) is a type of large language model (**LLM**) and a prominent framework for generative artificial intelligence (**GAI**). The concept and model were introduced in 2018 by  OpenAI. LLM are pre-trained on vast amounts of data and are capable of understanding context, generating relevant responses.


- ChatGPT is trained on data up to September 2021 and is unaware of recent events.
- ChatGPT can  hallucinate in responses with overconfidence, which results in incorrect answers or misleading information, needs cross-checking.
- ChatGPT lacks knowledge about domain - a user's unique knowledge base.


**Why Elasticsearch?**
- Elasticsearch as a search engine delivers relevant document retrieval, supports traditional keyword and text-based search (BM25),  an AI-ready vector search with exact match and approximate kNN (k-Nearest Neighbor) or hybrid search (BM25 + kNN).
   * *BM25 [Similarity Module](https://www.elastic.co/guide/en/elasticsearch/reference/current/index-modules-similarity.html)*
   * *A k-nearest neighbor (kNN) search finds the k nearest vectors to a query vector, as measured by a similarity metric. To run a kNN search, you must be able to convert your data into meaningful vector values. Elasticsearch supports Exact, brute-force kNN using a script_score query with a vector function and Approximate kNN using the knn search option. Approximate kNN offers lower latency at the cost of slower indexing and imperfect accuracy. Exact, brute-force kNN guarantees accurate results but doesn’t scale well with large datasets. [K-nearest neighbor (kNN)](https://www.elastic.co/guide/en/elasticsearch/reference/current/knn-search.html)*


- Elasticsearch has robust API for integration with other services, third-party tools and platforms to create customized search solutions.


- Elasticsearch provides domain-relevant specific documents for ChatGPT to use in its response to ensure factual, contextually relevant, and up-to-date answers.


**How to build a Q&A with python backend?**
1. Python interface accepts user questions.
2. Search request is sent to Elasticsearch combining BM25 and kNN search on indexed Elasticsearch Docs. 
3. Documentation body and original url are returned to python.
4. API call is made to OpenAI ChatCompletion: **Prompt: "answer this question <question> using only this document <body_content from top search result>"** to ensure the ChatGPT model only uses information from the body.
5. Generated response is returned to python.
6. Python adds on original documentation source url to generated response and prints it to the screen for the user.


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
## ChatGPT and Elasticsearch: A plugin to use ChatGPT with your Elastic data
This [blog post](https://www.elastic.co/blog/chatgpt-elasticsearch-plugin-elastic-data) introduces the ChatGPT Elasticsearch Plugin based on ChatGPT plugin framework and explains how to implement the plugin and extend the use of ChatGPT to any content indexed in Elasticsearch, using the Elastic documentation.


**What is a ChatGPT plugin?**
ChatGPT plugins are extensions that are developed to assist the model in completing its knowledge or executing actions, e.g. Expedia assist in planning travel, making ChatGPT a trip-planning assistant


**How to build a Q&A plugin?**
1. ChatGPT makes a call to the `/search` endpoint of the plugin. This decision is based on the plugin “rules” `description_for_human` (see plugin-manifest).
2. The plugin code creates a search request that is sent to Elasticsearch.
3. Documentation body and original url are returned to Python.
4. The plugin returns the document body and url, in text form to ChatGPT.
5. ChatGPT uses the information from the plugin to craft its response.


**How the plugin is implemented?**
[repository](https://github.com/elastic/ElasticGPT_Plugin/)
- python code
   - /logo.png: retrieve the plugin logo
   - /.well-known/ai-plugin.json: fetches the plugin manifest
   - /openapi.yaml: fetches the plugin OpenAPI description
   - /search is the only one here exposed to ChatGPT that runs the search in Elasticsearch
- plugin manifest
   - description_for_human - This is what the human sees when installing the plugin in the ChatGPT web UI.
   - description_for_model - Instructions for the  model to understand when to use the plugin.
- OpenAPI definition
   - We take the ChatGPT prompt content and pass it as a query to our Elasticsearch cluster.
   - Some placeholders such as PLUGIN_HOSTNAME are replaced in the Python code.




**How to  deploy the Elastic plugin?**
Plugin can be deployed using a diff cloud provider, the blog describes GCP.
- permissions to build and deploy a container in GCP IAM
- build the container image using Cloud Build and push it to the Google Container Registry (replace PROJECT_ID and container name)
- export the environment required by the Python code to create the Elasticsearch client
- deploy the container image to Cloud Run
- you can activate the continuous integration so that any commit in your GitHub repository will trigger a redeploy




**How to install the plugin in ChatGPT?**
- open https://chat.openai.com/ and go in the plugin store
- choose to do “Develop your own plugin”
- paste the URL of  a publicly accessible endpoint, copied from the Google Cloud Run page
- ensure the plugin is found and valid
- follow the installation instructions until you see your plugin available in the list
- test the plugin
---


## How to use Elasticsearch to prompt ChatGPT with natural language
The [blog post](https://www.elastic.co/blog/elasticsearch-prompt-chatgpt-natural-language) describes how ability to generate code can be applied to generate Elasticsearch DSL queries. The goal is to search in Elasticsearch® with sentences like “Give me the first 10 documents of 2017 from the stocks index.”


**How to generate Elasticsearch DSL with ChatGPT?**
- use the GET /stocks/_mapping API to retrieve the mapping from Elasticsearch.
- prompt ```Given the mapping delimited by triple backticks ```{mapping}``` translate the text delimited by triple quotes in a valid Elasticsearch DSL query """{query}""". Give me only the json code part of the answer. Compress the json output removing spaces.```
   - replace {mapping}  with string returned by GET /stocks/_mapping
   - replace {query}  with a question expressed in human language (for example: Return the first 10 documents of 2017)
- iterate to avoid general or ambiguous replies
- test with https://www.dsltranslate.com/


**How to put all together?**
- [repository](https://github.com/elastic/elasticsearch-chatgpt-php), the inputs are index and prompt, the result is a mapping in JSON that is used to build the query string to send to ChatGPT
- to query Elasticsearch the official elastic/elasticsearch-php client is utilized
- to optimize response time and reduce the cost of using the ChatGPT API use
a simple caching system based on files
   - store the mapping JSON returned by Elasticsearch: file named after the index;
   - store the Elasticsearch DSL generated by ChatGPT: the cache file using the hash (MD5) of the prompt used
   - getLastQuery() function


**How to run an experiment with financial data?**
- ingest data from https://github.com/elastic/elasticsearch-php-examples/blob/main/data/all_stocks_5yr.csv
- set environment variables: openai api key, elastic cloud endpoint, elastic cloud api key
- run a simple PHP script for testing some query expressed in English https://github.com/elastic/elasticsearch-chatgpt-php/blob/main/examples/test.php
- test with the following requests:
   - Query: Return the first 30 names of all the different stock names
   - Query: Return the first 10 documents of 2017
   - Query: Return the max value of the field "high" for each stock in 2015
   - Query: Return the average value of the field "high" for each stock in 2015
   - Query: Return the max value of the field "high" for all the documents with name MON in 2014
   - Query: Return the documents that have the difference between close and open fields > 20
- test with diff languages:
   - $result = $chatGPT->search('stocks', 'Return the first 10 documents of 2017');
   - $result = $chatGPT->search('stocks', 'Senden Sie die ersten 10 Dokumente des Jahres 2017 zurück');


**What are the limitations and how to solve them?**
- LLMs are not capable of verifying the correctness of the answer --> use  using an external plugin, like the Wolfram Plugin of ChatGPT (https://www.wolfram.com/wolfram-plugin-chatgpt/).
-  lacking ability to translate a human sentence in an Elasticsearch DSL query --> rephrase the sentence using more specific information, removing the apparent ambiguity about the date format


---


## Exploring Applications of ChatGPT to Improve Detection, Response, and Understanding in Security
The [blog post](https://www.elastic.co/de/security-labs/exploring-applications-of-chatgpt-to-improve-detection-response-and-understanding) explores the applications of ChatGPT in the field of security, specifically focusing on improving detection, response, and understanding of security incidents. It discusses the potential of using ChatGPT to enhance security operations and highlights its benefits in the context of threat detection and incident response.


OpenAI announced APIs to integrate ChatGPT and Whisper models into apps to experiment with LLMs, e.g. to assist with security use cases.
* *Whisper is a general-purpose speech recognition model. It is trained on a large dataset of diverse audio and is also a multitasking model that can perform multilingual speech recognition, speech translation, and language identification.* https://github.com/openai/whisper


**How to put all together?**
[sample_chatgpt_security_use_case.py](https://gist.github.com/Mikaayenson/9efff700e5d799c672c6b17338d2de6a)
1. choose a number of relevant fields (more fields, more context)
2. Simple use case: ELI5 simply queries the detection engine for alerts with predefined prompts
   - Explain this  event like I'm five
   - Explain this event to my kids
   - Explain this event to my boss
   - Explain this event to the new graduate
   - Explain what happened in this event
   - Explain this event to the CISO
   - What are next investigative steps to take based on this event
3. Summarize all of the alerts for the week into a single summary for reporting
4. Alert prioritization (alert fatigue, high volume of alerts, lack of training, constrained resources, etc.)
   - Which one of these alerts should I prioritize? (in case of generic answers add the new fields to the original events, feeding more context to ChatGPT can always help get a better answer)
   - How risk scores impact the decisions and make an appropriate recommendation.


**Why it matters?**
*you can  prioritize alerts using a rules-based strategy (e.g. sort alerts by highest severity) but other factors can impact the response (volume of alerts, the similarity of alerts, etc.), where at the end of the day the recommendation may be ultimately based on a timestamp or another field provided that is not as obvious to the responder.*


**What are future directions?**
   - *Contextualizing alerts*: past alerts provide relevant insights to the analyst.
   - *Training new models*: applying transfer-learning techniques to train new predictive models that are tailored to an organization's specific dataset and security needs. This training would cover large sets of historical reports, logs, ELT-prepped network traffic, responses, etc.
   - *Automating all the things*: automating the mundane tasks away, sounds simple, but will challenge our ability to trust in automation.
   - *Threat modeling*: Create highly representative threat models and attacks that adversaries may exploit to reinforce and improve an organization's security posture.


**What are the potential applications for improving security operations?**
   - *Chatbot-assisted Incident Response* to identify and respond to security incidents in real-time, to analyze the incident and provide an appropriate and configurable response (e.g. execute response actions, recommend new queries, etc.).
   - *Threat information* to analyze threat data and generate reports for your security product to improve the mean-time to respond.
   - *Security policy chatbot** to answer security-related questions while investigating threats, provide accurate and relevant answers to questions about security policies, best practices, summarizing information, and more.
   - *Alert prioritization* to group and prioritize the most relevant information to the analyst for an expedited response.


**Summary**
1. **Introduction to ChatGPT in Security**: The blog introduces the concept of applying ChatGPT in the field of security and emphasizes its potential to enhance various aspects of security operations.
2. **Improving Threat Detection**: It discusses how ChatGPT can be utilized to enhance threat detection capabilities by analyzing and processing large volumes of security logs, identifying patterns, and providing insights into potential security incidents.
3. **Enhancing Incident Response**: The blog highlights the role of ChatGPT in improving incident response by providing real-time guidance and recommendations to security analysts, helping them analyze and prioritize security events more effectively.
4. **Natural Language Understanding of Security Data**: ChatGPT's natural language processing capabilities can assist in better understanding security-related text data, such as threat intelligence reports, vulnerability assessments, and security advisories.
5. **Human-Machine Collaboration**: The blog emphasizes the importance of human-machine collaboration in security operations, where ChatGPT serves as a valuable tool for security analysts, enhancing their expertise and decision-making process.
6. **Considerations and Challenges**: The post acknowledges the challenges and considerations when implementing ChatGPT in security, such as model biases, data privacy, and the need for continuous training and monitoring.
7. **Future Directions**: The blog concludes by highlighting the potential for further advancements in utilizing ChatGPT for security purposes, including the integration with existing security tools and frameworks.


---


## Monitoring OpenAI API GPT Models with OpenTelemetry and Elastic
The [blog post](https://www.elastic.co/de/blog/monitor-openai-api-gpt-models-opentelemetry-elastic) discusses the importance of monitoring OpenAI API GPT models and introduces the integration of OpenTelemetry and Elastic for effective monitoring. It highlights the benefits of using OpenTelemetry to collect and visualize model telemetry data and explains how to leverage Elastic Stack for storing, analyzing, and alerting on the collected metrics.


**Summary**
1. **Introduction to Model Monitoring**: The blog emphasizes the significance of monitoring OpenAI API GPT models to ensure their performance, reliability, and adherence to predefined metrics and thresholds.
2. **Introducing OpenTelemetry**: It introduces OpenTelemetry as a powerful tool for collecting telemetry data from GPT models. OpenTelemetry provides a standardized approach to instrumenting models and capturing relevant metrics.
3. **Benefits of OpenTelemetry and Elastic Integration**: The blog highlights the advantages of integrating OpenTelemetry with Elastic Stack. OpenTelemetry offers flexible instrumentation and the ability to collect data from various sources, while Elastic Stack provides a robust platform for storing, analyzing, and visualizing the collected metrics.
4. **Collecting Model Telemetry Data**: The post explains how to instrument GPT models using OpenTelemetry and collect relevant telemetry data such as request latency, response time, and model usage statistics.
5. **Storing and Analyzing Metrics with Elastic**: It describes how to leverage Elastic Stack to store the collected telemetry data in Elasticsearch, visualize it with Kibana, and perform advanced analytics to gain insights into model performance and behavior.
6. **Alerting and Anomaly Detection**: The blog discusses the capability of Elastic Stack to set up alerts and anomaly detection based on predefined thresholds or machine learning algorithms, enabling proactive monitoring and early detection of issues.
7. **Future Directions and Best Practices**: The post concludes by highlighting the potential for further advancements in model monitoring and provides best practices for effective monitoring of OpenAI API GPT models using OpenTelemetry and Elastic.


In conclusion, the integration of OpenTelemetry and Elastic Stack enables efficient monitoring of OpenAI API GPT models, ensuring performance and reliability. The blog showcases the benefits of using OpenTelemetry for collecting model telemetry data and leveraging Elastic Stack for storing, analyzing, and alerting on the metrics, thereby enhancing the monitoring capabilities of GPT models.


---


## Privacy-first AI search using LangChain and Elasticsearch
The [blog post](https://www.elastic.co/blog/privacy-first-ai-search-langchain-elasticsearch)


What is LangChain? LangChain is a Python and JavaScript framework for developing applications powered by large language models. LangChain will work with OpenAI’s APIs, but it also excels at abstracting away the differences between databases and AI tools.


semantic search to retrieve our private knowledge and then inject that context with a question to our private LLM.


**How it works?**
1. identify data set 




## Accessing machine learning models in Elastic
The [blog post](https://www.elastic.co/blog/may-2023-launch-machine-learning-models)  discusses Elastic's machine learning capabilities and the options available for applying machine learning in different scenarios. It highlights the ability to leverage built-in models, access third-party PyTorch models, and load self-trained models, particularly focusing on NLP transformers. The article also mentions the scalability of model management across multiple nodes and the use of dedicated nodes for computationally intensive model inference, enabling efficient ingestion, data analysis, and search within Elasticsearch.






1. Elastic provides support for machine learning (ML) models, allowing you to apply ML appropriate for your use case and level of expertise.
2. You can leverage built-in models for specific security threats and system issues, use Elastic's proprietary model, access third-party PyTorch models, or load your own trained models.
3. Elastic's model management is scalable across multiple nodes, ensuring good inference performance for high throughput and low latency workloads.
4. The Eland library allows you to load ML models into Elasticsearch, particularly those trained using PyTorch.
5. There are three options for using Eland: command-line, Docker, or within your own Python code.
6. Kibana's ML Model Management interface enables model management on an Elasticsearch cluster.
7. Elastic supports transformer models and popular supervised learning libraries.
8. Generative AI models can be used with Elastic's API for passing queries and processing results.
9. Detailed steps are provided for loading and using NLP models in Elastic, including specifying identifiers, authentication, and deployment.
10. Inference can be performed using the deployed model, such as extracting named entities.
11. Additional resources are available for using models in inference pipelines, tuning deployment, and applying semantic search.


## Unlocking the potential of large language models: Elastic's first code contribution to LangChain
The [blog post](https://www.elastic.co/blog/large-language-models-elastic-code-langchain)  discusses synergy between LangChain and Elastic to generate embeddings using Elasticsearch models.


**LanChain**
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


---


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




## Improving information retrieval in the Elastic Stack: Introducing Elastic Learned Sparse Encoder, our new retrieval model

