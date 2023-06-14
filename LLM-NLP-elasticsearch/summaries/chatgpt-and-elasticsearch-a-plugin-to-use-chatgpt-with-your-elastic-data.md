
# ChatGPT and Elasticsearch: A plugin to use ChatGPT with your Elastic data

This [blog post](https://www.elastic.co/blog/chatgpt-elasticsearch-plugin-elastic-data) introduces the ChatGPT Elasticsearch Plugin based on ChatGPT plugin framework and explains how to implement the plugin and extend the use of ChatGPT to any content indexed in Elasticsearch, using the Elastic documentation.

---
**What is a ChatGPT plugin?**
Extensions that assist the model in completing its knowledge or executing actions, e.g. Expedia assist in planning travel, making ChatGPT a trip-planning assistant

---
**How to build a Q&A plugin?**
1. ChatGPT makes a call to the `/search` endpoint of the plugin. This decision is based on the plugin “rules” `description_for_human` (see plugin-manifest).
2. The plugin code creates a search request that is sent to Elasticsearch.
3. Documentation body and original url are returned to Python.
4. The plugin returns the document body and url, in text form to ChatGPT.
5. ChatGPT uses the information from the plugin to craft its response.
---
**How the plugin is implemented?**
[repository](https://github.com/elastic/ElasticGPT_Plugin/)
- _python code_
   - /logo.png: retrieve the plugin logo
   - /.well-known/ai-plugin.json: fetches the plugin manifest
   - /openapi.yaml: fetches the plugin OpenAPI description
   - /search is the only one here exposed to ChatGPT that runs the search in Elasticsearch
- _plugin manifest_
   - description_for_human - This is what the human sees when installing the plugin in the ChatGPT web UI.
   - description_for_model - Instructions for the  model to understand when to use the plugin.
- _OpenAPI definition_
   - We take the ChatGPT prompt content and pass it as a query to our Elasticsearch cluster.
   - Some placeholders such as PLUGIN_HOSTNAME are replaced in the Python code.
---
**How to  deploy the Elastic plugin?**

Plugin can be deployed using a diff cloud provider, the blog describes GCP.
- permissions to build and deploy a container in GCP IAM
- build the container image using Cloud Build and push it to the Google Container Registry (replace PROJECT_ID and container name)
- export the environment required by the Python code to create the Elasticsearch client
- deploy the container image to Cloud Run
- you can activate the continuous integration so that any commit in your GitHub repository will trigger a redeploy
---
**How to install the plugin in ChatGPT?**
- open https://chat.openai.com/ and go in the plugin store
- choose to do “Develop your own plugin”
- paste the URL of  a publicly accessible endpoint, copied from the Google Cloud Run page
- ensure the plugin is found and valid
- follow the installation instructions until you see your plugin available in the list
- test the plugin
---
