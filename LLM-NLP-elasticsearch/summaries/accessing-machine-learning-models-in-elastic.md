
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

--- 
