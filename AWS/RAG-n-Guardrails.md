# RAG on AWS Bedrock
<img width="884" height="452" alt="image" src="https://github.com/user-attachments/assets/8022cdb6-08b0-45e0-a0ae-02c715aaf7c4" />

#### Best practise for RAG 
- Evaluation : Measure result quality, understand issues, and iterate faster
- Guardrails : Add online checks to detect and intercept common failure modes
- Optimization : Optimize content, indexing, and generation for best answer quality

#### when RAG wrong 
- Content/scope issues : Our knowledge base doesn’t quite address this question
- Retrieval issues : The search engine didn’t find the documents (snippets) it should have
- Generation issues : The LLM gave an irrelevant, incorrect, or otherwise poor answer

#### LLM-judged RAG evaluation
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/20a99bdd-1cbd-41e4-91fa-4422d23cdb67" />

#### Automated RAG evaluation 
- Ragas : [ragas](https://github.com/explodinggradients/ragas)
- Amazon Bedrock knowledge base evaluation

# Bedrock knowledge base evaluation

Step 1: Upload documents in S3

Step 2: Open Bedrock 
Check if access to atleast 2 models are present, Embedding model & Language model  
AWS Bedrock --> Bedrock Configuration (Model Access) --> Embedding (Titan Text Embedding V2) &  Text gen model (Nova Pro)

Step 3: Knowldge Bases 
AWS Bedrock --> Builder tools --> Knowldge Bases --> Create (Knowldge base with vector store)

Step 4: Knowldge base 
IAM : Create & use new service role
Query Engine: chose S3
Next 
give a name for S3 data source  (bcos KB can combine multiple data sources)
Copy S3 Uri from (s3 service ) to s3 source 
Next 
Choose embedding model 
Vector store : select "Quick create new vector store" and "Amazon OpenSearch Serverless" 
Next 
Review and "Create Knowldge base" 

Step 5: Sync the KB 
to sync and index the data sources 
Knowldge base --> Data Source --> Sync (Time consuming mins to hours ) 

Step 6: manually Evaluate 
Knowldge base --> Data Source --> " Test knowldge Base" 

Step 7: Auto Evaluations 
Prepare a Json file with Quesions and expected answers and store on S3 
AWS Bedrock --> Evaluations --> RAG --> Create 
Name 
Evaluator model: Claude sonnet 3
Inference source: Bedrock KB
choose KB drop down 
Evaluation type: "Retrival and response generation" 
Generator model: Amazon Nova Pro
Metrics: select 
Responsible AI: select 
Dataset and evaluation results S3 location. input and output folders 
create 

Step 8: Review the summary report 

# AWS Bedrock Guardrails 
Evaluate prompts and model responses for agents, knowledge bases, FMs in Amazon Bedrock, and self-managed or third-party FMs.
Pay for only those features you use 

AWS Bedrock --> Guardrails --> Create Guardrails 
Name 
Next 
Configure Content filters 
Next 
Denied topics 
Next 
Next
Grounding checks: Threshould 0.75 and Relevance 0.75
Review and create 
Test 





