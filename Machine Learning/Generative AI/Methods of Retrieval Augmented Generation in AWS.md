AWS offers [[Retrieval Augmented Generation]] methods with a few AWS services. These provide different levels of complexity. These are:

[[Bedrock Knowledge Bases]]: 
- You can manage a [[Vector Database]] through Bedrock Knowledge Bases. This will handle the ingestion and retrieval of data from a vector database alongside the [[Embeddings]] process with a [[Bedrock Model]]
- You can call the RetrieveAndGenerate API directly with data from [[S3]] or using the data directly as a blob in the API
- It connects to [[Aurora]], [[Opensearch Serverless]], [[Redis Cloud]], [[Pinecone]] and [[mongoDB]]

[[SageMaker Jumpstart]]:
- SageMaker Jumpstart allows you to deploy [[Large Language Models]] and [[Embeddings Models]] on [[SageMaker]] directly, making the deployment process easier for customers
- Customers must manage their own vector database

[[Kendra]]:
- Kendra acts as an [[Intelligent Search]]. Customers ingest data into Kendra which they can then retrieve and send to a [[Large Language Models]] for output