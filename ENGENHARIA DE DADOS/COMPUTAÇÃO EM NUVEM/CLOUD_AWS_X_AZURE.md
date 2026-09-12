Lista de Serviços AWS e seu correspondente na Azure.

```
                 AWS                         AZURE
────────────────────────────────────────────────────────
Data Lake       S3                    →     ADLS Gen2
Data Warehouse  Redshift              →     Synapse
SQL Data Lake   Athena                →     Synapse Serverless
ETL             Glue                  →     Data Factory
Spark           EMR                   →     Databricks
Streaming       Kinesis               →     Event Hubs
Kafka           MSK                   →     Event Hubs / Confluent
Governance      Lake Formation        →     Purview
Catalog         Glue Catalog          →     Purview
Serverless      Lambda                →     Functions
Containers      ECS/Fargate           →     Container Apps
Kubernetes      EKS                   →     AKS
NoSQL           DynamoDB              →     Cosmos DB
Relational      RDS                   →     Azure SQL
Cache           ElastiCache           →     Azure Cache for Redis
Messaging       SQS/SNS               →     Service Bus/Event Grid
Orchestration   Step Functions        →     Logic Apps/Durable Functions
Airflow         MWAA                  →     Managed Airflow
IAM             IAM                   →     Entra ID/RBAC
Secrets         Secrets Manager       →     Key Vault
Monitoring      CloudWatch             →     Azure Monitor
API             API Gateway            →     API Management
IaC             CloudFormation         →     Bicep
CI/CD           CodePipeline           →     Azure DevOps
ML              SageMaker              →     Azure ML
GenAI           Bedrock                →     Azure AI Foundry/OpenAI
BI              QuickSight             →     Power BI
```

**AWS:**
`S3 → Glue → EMR → Redshift/Athena → Lake Formation`

**Azure:**
`ADLS Gen2 → Data Factory → Databricks → Synapse → Purview`


>[!Nota]
>**S3 ≈ ADLS Gen2** → equivalência bastante direta.
>
>**Redshift ≈ Synapse Dedicated SQL Pool** → ambos são Data Warehouse, embora tenham arquiteturas diferentes.
> 
> **Glue ≈ Data Factory** → para integração/orquestração. Porém, o Glue também possui recursos de catálogo e execução Spark, então **ADF não cobre 100% do Glue**.
>
> **Athena ≈ Synapse Serverless SQL** → essa é uma das equivalências mais diretas: SQL diretamente sobre dados no Data Lake, sem precisar manter um DW provisionado.
>
>**EMR ≈ Databricks/Synapse Spark** → se a empresa usa Spark fortemente, **Azure Databricks é normalmente a comparação mais adequada**.
>
>**Lambda ≈ Azure Functions** → equivalência direta para funções serverless.
>
>**Lake Formation ≠ Purview 1:1** → aqui eu teria cuidado. O Azure distribui essa responsabilidade entre **Purview, RBAC, ACLs do ADLS e recursos de governança**.
