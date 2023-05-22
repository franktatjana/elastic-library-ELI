# Resources about OpenAI and Elastic Intergation

## Summary
A collection of blogs around OpenAI and ChatGPT. Blogs describe how to build own Q&A system on the basis of information indexed into elasticsearch, create own plugin with example of elasticsearch documentation, apply capabilities to generate code, analyze security incidents and opentelemetry data. 

[Elastic Machine Learning](https://www.elastic.co/what-is/elasticsearch-machine-learning)

---

## Referenced Blogs
19.04.2023 Jeff Vestal [ChatGPT Elasticsearch: Enabling OpenAI to Work with Private Data](https://www.elastic.co/de/blog/chatgpt-elasticsearch-openai-meets-private-data) | [Summary](##ChatGPT-Elasticsearch:-Enabling-OpenAI-to-Work-with-Private-Data)

15.05.2023 Baha Azarmi [ChatGPT and Elasticsearch: a plugin to use ChatGPT with your Elastic data](https://www.elastic.co/blog/chatgpt-elasticsearch-plugin-elastic-data) | [Summary]

16.05.2023 Enrico Zimuel [How to use Elasticsearch to prompt ChatGPT with natural language](https://www.elastic.co/blog/elasticsearch-prompt-chatgpt-natural-language) | [Summary]

15.03.2023 Mika Ayenson (Security) [Exploring Applications of ChatGPT to Improve Detection, Response, and Understanding in Security](https://www.elastic.co/security-labs/exploring-applications-of-chatgpt-to-improve-detection-response-and-understanding) | [Summary](##Exploring-Applications-of-ChatGPT-to-Improve-Detection,-Response,-and-Understanding-in-Security)

04.04.2023 David Hope (Observability) [Monitoring OpenAI API GPT Models with OpenTelemetry and Elastic](https://www.elastic.co/blog/monitor-openai-api-gpt-models-opentelemetry-elastic) | [Summary](##Monitoring-OpenAI-API-GPT-Models-with-OpenTelemetry-and-Elastic)

----

## Repositories
[Elasticsearch ChatGPT for PHP](https://github.com/elastic/elasticsearch-chatgpt-php)

[ElasticGPT_Plugin](https://github.com/elastic/ElasticGPT_Plugin/) 

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
3. Google Colab, a cloud-based Jupyter notebook environment, allows to edit and run a specified notebook. To download and deploy the ML model change parameter hf_model_id='sentence-transformers/all-distilroberta-v1'(copy model name from Hugging Face) and enter cloud ID and credentials.
    * [python notebook](https://github.com/jeffvestal/ElasticDocs_GPT/blob/main/load_embedding_model.ipynb)
    * [Eland](https://github.com/elastic/eland#readme)  
3. Ingest content with a web crawler (example with elasticsearch guides) and use an ingest pipeline to generate vectors for the doc titles to run kNN search on the title field vectors. 
4. Create account in https://platform.openai.com, get an API key.
5. Install required python libraries, set authentification and connection env variables, run the streamlit programm streamlit run elasticdocs_gpt.py
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

1. **Introduction to ChatGPT in Security**: The blog introduces the concept of applying ChatGPT in the field of security and emphasizes its potential to enhance various aspects of security operations.

2. **Improving Threat Detection**: It discusses how ChatGPT can be utilized to enhance threat detection capabilities by analyzing and processing large volumes of security logs, identifying patterns, and providing insights into potential security incidents.

3. **Enhancing Incident Response**: The blog highlights the role of ChatGPT in improving incident response by providing real-time guidance and recommendations to security analysts, helping them analyze and prioritize security events more effectively.

4. **Natural Language Understanding of Security Data**: ChatGPT's natural language processing capabilities can assist in better understanding security-related text data, such as threat intelligence reports, vulnerability assessments, and security advisories.

5. **Human-Machine Collaboration**: The blog emphasizes the importance of human-machine collaboration in security operations, where ChatGPT serves as a valuable tool for security analysts, enhancing their expertise and decision-making process.

6. **Considerations and Challenges**: The post acknowledges the challenges and considerations when implementing ChatGPT in security, such as model biases, data privacy, and the need for continuous training and monitoring.

7. **Future Directions**: The blog concludes by highlighting the potential for further advancements in utilizing ChatGPT for security purposes, including the integration with existing security tools and frameworks.

In summary, the blog explores the potential applications of ChatGPT in the security domain, showcasing its benefits in threat detection, incident response, and natural language understanding of security data. It emphasizes the importance of human-machine collaboration and discusses future directions for leveraging ChatGPT to improve security operations.

---

## Monitoring OpenAI API GPT Models with OpenTelemetry and Elastic
The [blog post](https://www.elastic.co/de/blog/monitor-openai-api-gpt-models-opentelemetry-elastic) discusses the importance of monitoring OpenAI API GPT models and introduces the integration of OpenTelemetry and Elastic for effective monitoring. It highlights the benefits of using OpenTelemetry to collect and visualize model telemetry data and explains how to leverage Elastic Stack for storing, analyzing, and alerting on the collected metrics.

1. **Introduction to Model Monitoring**: The blog emphasizes the significance of monitoring OpenAI API GPT models to ensure their performance, reliability, and adherence to predefined metrics and thresholds.

2. **Introducing OpenTelemetry**: It introduces OpenTelemetry as a powerful tool for collecting telemetry data from GPT models. OpenTelemetry provides a standardized approach to instrumenting models and capturing relevant metrics.

3. **Benefits of OpenTelemetry and Elastic Integration**: The blog highlights the advantages of integrating OpenTelemetry with Elastic Stack. OpenTelemetry offers flexible instrumentation and the ability to collect data from various sources, while Elastic Stack provides a robust platform for storing, analyzing, and visualizing the collected metrics.

4. **Collecting Model Telemetry Data**: The post explains how to instrument GPT models using OpenTelemetry and collect relevant telemetry data such as request latency, response time, and model usage statistics.

5. **Storing and Analyzing Metrics with Elastic**: It describes how to leverage Elastic Stack to store the collected telemetry data in Elasticsearch, visualize it with Kibana, and perform advanced analytics to gain insights into model performance and behavior.

6. **Alerting and Anomaly Detection**: The blog discusses the capability of Elastic Stack to set up alerts and anomaly detection based on predefined thresholds or machine learning algorithms, enabling proactive monitoring and early detection of issues.

7. **Future Directions and Best Practices**: The post concludes by highlighting the potential for further advancements in model monitoring and provides best practices for effective monitoring of OpenAI API GPT models using OpenTelemetry and Elastic.

In conclusion, the integration of OpenTelemetry and Elastic Stack enables efficient monitoring of OpenAI API GPT models, ensuring performance and reliability. The blog showcases the benefits of using OpenTelemetry for collecting model telemetry data and leveraging Elastic Stack for storing, analyzing, and alerting on the metrics, thereby enhancing the monitoring capabilities of GPT models.
