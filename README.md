# Azure OpenAI Insights
The 'Azure OpenAI Insights' workbook offers deep insights into Azure OpenAI usage, helping you manage costs, optimize performance, and make strategic decisions for a robust AI infrastructure.

![image](https://github.com/dolevshor/Azure-OpenAI-Insights/assets/69309933/d3ed1aaa-5c10-40fb-89b7-d40b487d69a3)


## Introduction

In the ever-evolving world of Artificial Intelligence, organizations and entities across various sectors are on a quest to leverage advanced technologies efficiently. Azure OpenAI opens a realm of possibilities, offering both challenges and excitement, particularly for those at the early stages of AI adoption.

Read more in depth in this Tech Community blog: [Azure OpenAI Insights: Monitoring AI with Confidence](https://techcommunity.microsoft.com/t5/fasttrack-for-azure/azure-openai-insights-monitoring-ai-with-confidence/ba-p/4026850)

This workbook offers deep insights into Azure OpenAI resources and usage (Platform Metrics and Logs) and can be powerful tool in analyzing & monitoring your AI initiatives.

## Structure and Views 

### Structure

This workbook contains 3 main parts:
- **Overview** - Holistic view of Azure OpenAI resources
- **Monitor** - Holistic view of Azure OpenAI resources Metrics
- **Insights** - Holistic view of Azure OpenAI resources Logs
  - Requires by enabling Diagnostic Settings to Log Analytics Workspace.

### Views

Types of views this workbook provides:

- **Overview**
  - Azure OpenAI Resources by
    - SubscriptionId
    - Resource Group
    - Location
    - Kind
    - Public Network Access
    - Private Network Access
  - All Azure OpenAI Resources

> The information displayed uses [KQL](https://learn.microsoft.com/en-us/azure/data-explorer/kusto/query/) queries to query the [Azure Resource Graph](https://learn.microsoft.com/en-us/azure/governance/resource-graph/overview).

- **Monitor**
  - Overview
    - Requests
    - Processed Inference Tokens
    - Processed Prompt Tokens
    - Generated Completions Tokens
    - Processed FineTuned Training Hours
    - Provisioned-managed Utilization
    - Active Tokens
    - Prompt Token Cache Match Rate
    - Time to Response
  - HTTP Requests
    - Requests
      - by Model Name
      - by Model Version
      - by Model Deployment Name
      - by Status Code
      - by StreamType
      - by Operation Name
      - by API Name
      - by Region
    - Time to Response
      - by Model Name
      - by Model Deployment Name
    - Prompt Token Cache Match Rate
      - by Model Name
      - by Model Deployment Name
  - Token-Based Usage
    - Processed Inference Tokens
      - by Model Name
      - by Model Deployment Name
    - Processed Prompt Tokens
      - by Model Name
      - by Model Deployment Name
    - Generate Completion Tokens
      - by Model Name
      - by Model Deployment Name
    - Active Tokens
      - by Model Name
      - by Model Deployment Name
  - PTU Utilization
    - Provisioned-managed Utilization
      - by Model Name
      - Model Version
      - by Model Deployment Name
      - by StreamType
      - by Region
  - Fine-tuning
    - Processed FineTuned Training Hours
      - by Model Name
      - by Model Deployment Name

> The information displayed uses Azure OpenAI Platform Metrics and presented by multiple dimensions.

- **Insights**
  - Overview
    - Requests
      - by Resource
      - by Location
      - by StreamType
      - by Api Version
      - by Model Deployment Name + Operation Name
      - by Model Deployment Name
      - by Model Name + Operation Name
      - by Model Name
      - by Operation Name
      - by Avg Duration (ms)
      - by Avg Request Length (bytes)
      - by Avg Response Length (bytes)
  - By CallerIP
    - Requests
    - Operation Name
    - Model Deployment Name + Operation Name
    - Model Name + Operation Name
    - Avg Duration (ms)
    - Avg Request Length (bytes)
    - Avg Response Length (bytes)
  - All Logs
    - Successful requests
  - Failures
    - Failed requests
      - by Resources
      - by Api Version
      - by Operation name
      - by Stream Type

#### Filters

![image](https://github.com/dolevshor/Azure-OpenAI-Insights/assets/69309933/88233144-bc7f-4ced-bdc8-a6fdc5b73ea8)


This workbook support to filter all the logs by several fields:
- Model Deployment Name
- Model Name
- Model Version
- Api Version
- Operation Name
- Stream Type
- Location

All the filters are related to each other to allow a granular view and simplify the tracking of the logs.

> The information displayed uses [KQL](https://learn.microsoft.com/en-us/azure/data-explorer/kusto/query/) queries to query the Log Analytics Workspace that store the logs.
>> Note: The Logs will be available on resources that enabled Diagnostic Settings to Log Analytics Workspace.

<ins>Average Duration (ms)</ins>
![image](https://github.com/dolevshor/Azure-OpenAI-Insights/assets/69309933/f9eb0778-3a70-4f93-8688-0a028aad71bd)

<ins>Average Request / Response Length (bytes)</ins>
![image](https://github.com/dolevshor/Azure-OpenAI-Insights/assets/69309933/a4b3cd14-1fc3-46b5-a56e-7a64a977b69b)



## How to use it?
Importing this Workbook to your Azure environment is quite simple.

Follow this steps to use the Workbook:

- Login to [Azure Portal](https://portal.azure.com/) <img src="https://user-images.githubusercontent.com/69309933/172941966-9e030031-6ccb-4ebf-bd2b-04bb623e5ff7.png" width="20" height="20">
- Go to _'Azure Workbooks'_

<img src="https://user-images.githubusercontent.com/69309933/172806635-14051976-328e-4623-96ab-0dd6a7bc7817.png" width="350">

- Click on _'+ Create'_

<img src="https://user-images.githubusercontent.com/69309933/172807465-cced3466-0669-423b-87b3-8fa70fdbf1d1.png" width="350">

- Click on _'+ New'_

<img src="https://user-images.githubusercontent.com/69309933/172807547-52d790ce-7852-4b4b-a81f-81e8b7fac26e.png" width="350"> 

- Open the Advanced Editor using the _'</>'_ button on the toolbar

<img src="https://user-images.githubusercontent.com/69309933/172807673-dfc63741-0c40-47c0-ab58-d39309b06e69.png" width="700"> 

- Select the _'Gallery Template'_ (step 1)
- Replace the JSON code with this JSON code [Azure OpenAI Insights JSON](https://raw.githubusercontent.com/dolevshor/Azure-OpenAI-Insights/main/Workbook/Azure%20OpenAI%20Insights.workbook) (step 2)
  - We use the _Gallery Templaty type_ (step 1), so we need to use the _'Azure OpenAI Insights.workbook'_ and not the _'Azure OpenAI Insights.json'_.
- Click _'Apply'_ (step 3)

<img src="https://user-images.githubusercontent.com/69309933/172807762-17aec6f9-4a81-4d5b-9017-673a0ab6b26e.png" width="700"> 

- Click in the ‘Save’ button on the toolbar

![image](https://github.com/dolevshor/Azure-OpenAI-Insights/assets/69309933/1aa875d8-0303-49a1-8a0d-74e83949e386)

- Select a name and where to save the Workbook:
  - Title: _'Azure OpenAI Insights'_
  - Subscription: <_Subscription Name_>
  - Resource group: <_Resource Group Name_>
  - Location: <_Region_>
- Click _'Save'_
  
The Workbook is ready to use!
- Click on _'Workbooks'_
- Click on _'Azure OpenAI Insights'_ Workbook.

Start using the Workbook and analyze your Azure OpenAI resources.<br/>

> (Optional) You can filter by specific subscription/s or resource/s.
