# CST8916 Assignment 2
## Elizabeth Kaganovsky (040956895)

### 1. Executive Summary 
The following document will provide a high-level comparison of roughly equivalent services in Microsoft Azure, Amazon Web Services and Google Cloud Platform in the areas of RESTful APIs, GraphQL services, WebSocket services, data streaming services, and stream analytics services. Each CSP offers competitive options which often are very close to functionality with one another, leading for ecosystem integration to become one of the main guiding tenets for organizations seeking to reap the benefits of the cloud. A key finding from this assingment is that each CSP offers such a wealth of options that often times multiple similar services can be used to achieve more or less the same result.

### 2. Introduction
Cloud computing is most often provided by one of three cloud service providers (CSPs). Amazon Web Services, launched in 2006, remains the market leader with a massive variety of services for countless industries. Since 2010 Microsoft has offered Azure, which brings with it a unique integration with Microsoft products and sovereignty options for governments. Google Cloud Platform caught up in 2011, offering customers a variety of tools for data analytics and machine learning, with robust support for containerized workloads. There is a myriad of additional cloud providers (IBM, Oracle, and Tencent among them), but to limit the scope of this document, only the three largest CSPs will be studied. The purpose of this comparison is to gain a deeper understanding of the services offered by the three major CSPs--while the services are considered rough equivalents, there are intricacies in each offering that can completely derail development if unaccounted for in the development process.

### 3.1. RESTful API Services
#### 3.1.1. Microsoft Azure
Microsoft offers Azure API Management (APIM) as a comprehensive API management PaaS solution that supports the entire API lifecycle--designing, publishing, securing, monitoring, and developing. APIM also supports self-hosted managed gateways, where an API gateway is deployed into the same environment as that which hosts the APIs, which is ideal for hybrid and multi-cloud setups since users will reap all the benefits of a PaaS solution while also complying with local rules and regulations on data and operational sovereignty. APIM also has the benefit of policies, small collections of statements that modify the behaviour of an API without requiring changes to the backend--among the 75 provided include policies for enforcing authentication or format transformation (such as changing incoming JSON to XML), but user-defined policies can also be created [1]. On the financial side, Azure API Management uses two pricing models--tiered and consumption. Each tier (Developer, Basic, Standard, and Premium) requires a monthly base cost per unit, with additional charges for API requests above a certain threshold. Comparatively, the consumption tier incurs no fixed costs, with billing being based on the number of API requests to the service. This pricing model makes APIM a better choice for large, constant API loads with good predictability [2].


#### 3.1.2. Amazon Web Services
For RESTful API services, AWS offers Amazon API Gateway. This service is exclusively serverless, unlike APIM which also offers the option of a managed service approach, a significant drawback for companies that require on-prem options for regulational compliance [3]. It also lacks policies like those of APIM, instead requiring Lambda functions to fill the gap, which can become expensive as Lambda functions require a fee per execution [4]. AWS API Gateway uses a pay-per-use model, in which API calls are charged per sets of one million requests, with additional fees for the amount of data transferred, making it preferrable for variable API loads that experience the bulk of their traffic through usage spikes [5].


#### 3.1.3. Google Cloud Platform
Google Cloud Platform offers multiple services for RESTful APIs depending on the scale of the application. For smaller projects and local testing, Google Cloud Endpoints (GCE) makes for a good solution, a user-managed service that allows the management of APIs in the GCP ecosystem with basic security and inexpensive pricing options. GCE is most beneficial to developers seeking to host the gateway on their own runtime, but also desire the control plane features that come with API Gateway but without the higher price tag. GCE pricing is based on the number of calls made to the API.

API Gateway works similarly to GCE, but is fully managed and and simplifies the management of APIs for other GCP services such as Cloud Functions and App Engine. API Gateway is ideal for medium scale use cases, where consistent governance and third-party API management are not yet issues. Similar to AWS API Gateway, GCP API Gateway is billed based on the number of requests and amount of data transferred.

For an enterprise-grade alternative, GCP provides Apigee API Management, a fully managed solution designed to deal with large volumes of traffic while maintaining high uptime. Apigee allows for more advanced features such as detailed analytics, security and monetization. Like APIM, Apigee can operate in hybrid/multi-cloud environments, and is recommended by GCP for applications expected to become complex or highly scaled, to avoid having to later change to another platform. Apigee offers three billing options--pay-as-you-go (based on call volume, proxy deployments and add-ons like analytics), tiered subscription based (standard, enterprise, and enterprise plus), and evaluation (try for free over 60 days) [6] [7].


### 3.2. GraphQL Services
#### 3.2.1. Microsoft Azure
GraphQL is supported by a multitude of Azure services, the choice of which to use depends on the needs of the application. For existing GraphQL apps, Azure App Services or Azure Container Apps allow for easy deployment with no/minimal changes to code. For apps that exist but do not have GraphQL functionality yet, Data API Builder can create GraphQL endpoints with little coding to add support. When building a GraphQL API layer from scratch to serve existing APIs, Azure API Management with GraphQL transformation can be used [8].  


#### 3.2.2. Amazon Web Services
AWS AppSync is a managed serverless service that provides GraphQL support to the AWS ecosystem. AppSync seamlessly integrates with and provides querying of other AWS services such as DynamoDB, Elasticsearch Service, Lambda functions, Aurora, and relational databases [9].


#### 3.2.3. Google Cloud Platform
GraphQL services are available on GCP primarily through Apigee, which provides an API management layer for REST as well [10]. However, GraphQL  can be deployed and managed using various GCP services, including running an Apollo server in containers on Cloud Run, or through Google Kubernetes Service (GKE) [11].


### 3.3. WebSocket Services
#### 3.3.1. Microsoft Azure
Azure Web PubSub is Azure's offering for building real-time WebSocket applications [12]. Web PubSub's performance is grouped into billable, scalable units, each of which can support 1,000 simultaneous connections and 3,000 outbound messages per second [13].


#### 3.3.2. Amazon Web Services
AWS API Gateway provides a WebSocket API that can interact with other AWS offerings like Lambda functions or Kinesis for backend functionality [14]. API Gateway can scale effectively to support millions of concurrent connections around the world. However, it unfortunately lacks fallback transport, meaning that in settings or on devices where websockets may be unavailable (corporate networks with proxy servers, older browsers, etc), there is no provided automatic fallback, meaning that the difficult undertaking of implementing fallback transport falls upon the developer [15].


#### 3.3.3. Google Cloud Platform
WebSockets can be implemented on the managed Cloud Run service of GCP. Like the other options, Cloud Run WebSockets scale with traffic [16].

### 3.4. Data Streaming Services
#### 3.4.1. Microsoft Azure
Azure provides Event Hubs and IoT Hub (A wrapper service for Event Hubs) for data streaming.Data can be ingested for a variety of sources, including IoT devices, logs, and social media, and funneled into storage such as Blob Storage or analysis tools such as Stream Analytics. Microsoft states that Event Hubs can ingest millions of events per second and support hundreds of thousands of simultaneous sources while maintaining low latency [17].


#### 3.4.2. Amazon Web Services
Amazon Kinesis is AWS's all-around solution to a variety of data streaming needs. Kinesis Data Streams and Video Streams are serverless data ingestion solutions, Data Firehose is used for loading data into storages such as data lakes or analytics services, and Data Analytics can process streams in real time with SQL or Apache Flink, making for a comprehensive suite of tools for data streaming and processing [18].


#### 3.4.3. Google Cloud Platform
GCP's Pub/Sub service allows for the gathering of real-time event data from multiple sources that utilizes (as the name implies) a publish/subscribe model of communication allowing for asynchronous, decoupled applications [19]. Pub/Sub provides native integration with Dataflow, another GCP service for processing of event streams [20].


### 3.5. Stream Analytics
#### 3.5.1. Microsoft Azure
Azure Provides the aptly named Stream Analytics for stream analytics, a managed service which integrates with Azure's other offerings such as those in AI and ML to process streaming data. Unlike the options from AWS and GCP, Stream Analytics uses its own unique query language, Stream Analytics Query Language (SAQL), to process streaming data in both structured and unstructured formats with sub-millisecond latency [21].


#### 3.5.2. Amazon Web Services
Stream analytics fall under the functionality of AWS' Kinesis platform, which also features tools for data streaming. In addition to more traditional methods of stream analytics, clients can also install Kinesis Agents into their servers for collecting, monitoring and analyzing log data at the source [22].


#### 3.5.3. Google Cloud Platform
GCP's main offering for stream analytics is Dataflow 


### 4. Use Case Analysis
### 4.1. Use Case 1: Credit Card Fraud Detection
Fraud is best detected right when it happens to minimize the impact it has on organizations and individuals who may be victimized. As such, real-time analytics must be used to detect these issues as soon as they occur. AWS once provided the managed service Amazon Fraud Detector but has since stopped allowing new clients for the service, but otherwise has expansive service offerings which can be combined by clients into robust detection solutions, however this may be expensive. GCP may be preferrable for newer companies who lack access to Amazon Fraud Detector since its closure of new clients since GCP provides advanced analytics and machine learning which can intercept fraud on the fly



### 4.2. Use Case 2: Environmental safety monitoring
Some environments require constant monitoring and immediate feedback on sudden dangerous changes in condition, such as mines which may experience build ups of gas or experience geologic activity as a prelude to collapses. To detect these before they endanger lives or property, IoT sensors can be used to monitor the environment, and data analytics tools to understand when data indicates a strong chance of impending disaster well in advance. The assumption is made that the enterprise currently uses non-networked detection or some other form of non-IoT safety features, but does use Windows technologies for the organization's computing and logistics needs. In this situation, Microsoft Azure is the preferable choice for building an IoT real-time safety system. Performance, in this situation, is not a significant component of CSP choice since all three options are roughly equivalent in latency. While AWS presents a more expansive set of services, Azure has potential for much stronger integration with the existing ecosystem. GCP offers strong machine learning tools, but is ruled out due to their 2023 retirement of Google Cloud IoT Core, which suggests that their systems cannot be trusted to remain offered for extended durations of time, which is a significant risk in an environment where sensors may be difficult to retrieve and update [23]. Services like Azure IoT Hub can be used for data ingestion, while Azure Stream Analytics provides serverless data processing. Processed data can then be visualized using Power BI for management and safety officials. Azure also offers IoT Edge, a service which allows some computing to be done on containerized workloads at the "edge" of the cloud, functionally on-prem and closer to the sensors, to provide analytics even if internet connection to the cloud is lost [24].


### 5. Conclusion
Picking a CSP is a difficult choice depending on many criteria, such as team experience, cost requirements, and existing ecosystem. In some cases, such as REST API services, each CSP provides extremely similar services, leaving the decision to be more heavily weighed by developer preference or service cost. In other cases, such as streaming analytics services, the choice may be more guided by specific offerings from each CSP in the realm of ML, or ease of use of the service since some offerings are services that can integrate while others are explicitly all provided by a single platform.

### 6. References
[1] Dlepow, “Policies in Azure API management,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/api-management/api-management-howto-policies 

[2] Dlepow, “Plan and manage costs for Azure API Management,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/api-management/plan-manage-costs 

[3] J. Page, “Amazon API Gateway vs Azure API Management | APIX-Drive,” Apix-Drive, Jul. 10, 2024. https://apix-drive.com/en/blog/other/amazon-api-gateway-vs-azure-api-management 

[4] “AWS vs Azure | Looking for AWS API Management alternatives? | Gravitee.” https://www.gravitee.io/comparison/aws-vs-azure 

[5] A. Bisanovic, “Azure API Management vs. AWS API Gateway: A comparison for banks and insurance companies,” ONLU AG, Jul. 18, 2025. https://onlu.ch/en/azure-api-management-vs-aws-api-gateway-a-comparison-for-banks-and-insurance-companies/ 

[6] G. Sjurseth and V. Anand, “Choosing between Apigee, API Gateway, and Cloud Endpoints,” Google Cloud Blog, Nov. 18, 2022. https://cloud.google.com/blog/products/application-modernization/choosing-between-apigee-api-gateway-and-cloud-endpoints 

[7] “ApiGee Pricing | Google Cloud,” Google Cloud. https://cloud.google.com/apigee/pricing 

[8] Diberry, “GraphQL on Azure for JavaScript developers - JavaScript on Azure,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/developer/javascript/graphql-developer-guide 

[9] “Serverless GraphQL APIS - AWS AppSync - AWS,” Amazon Web Services, Inc. https://aws.amazon.com/appsync/ 

[10] M. Fayaz, “Introduction to AWS AppSync - Fully managed GraphQL Service,” DEV Community, Feb. 02, 2023. https://dev.to/aws-builders/introduction-to-aws-appsync-fully-managed-graphql-service-4mff 

[11] D. Allen, “Secure GraphQL APIs in minutes with Cloud Run and GRAND Stack,” Medium, Jun. 06, 2019. https://medium.com/google-cloud/secure-graphql-apis-in-minutes-with-google-cloud-run-and-grand-stack-97d050dbc744 

[12x] Bjqian, “Performance guide for Azure Web PubSub Service,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/azure-web-pubsub/concept-performance 

[13x]Vicancy, “Billing model of Azure Web PubSub service,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/azure-web-pubsub/concept-billing-model

[14] V. Kumar, “Understanding WebSocket API in Amazon API Gateway,” Medium, Aug. 29, 2023. https://kvs-vishnu23.medium.com/understanding-websocket-api-in-amazon-api-gateway-60dc930307c6 

[15] “Scaling AWS API Gateway: Challenges and considerations,” Ably Realtime. https://ably.com/topic/scaling-aws-api-gateway-websocket-apis 

[16] “Using WebSockets,” Google Cloud Documentation. https://docs.cloud.google.com/run/docs/triggering/websockets 

[17] AliciaLiMicrosoft, “Introduction to Azure Stream Analytics - Azure Stream Analytics,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/stream-analytics/stream-analytics-introduction 

[18] R. John, “Azure and Amazon Data Stream Analytics and Processing: Amazon Kinesis, Azure Stream Analytics, and Azure Event Hub,” Medium, Dec. 27, 2020. https://trojrobert.medium.com/azure-and-amazon-data-stream-analytics-and-processing-amazon-kinesis-azure-stream-analytics-and-a6b42b213eb7 

[19] “Realtime Streaming in Google Cloud Platform,” Aug. 15, 2023. https://medium.com/@iampirated/realtime-streaming-in-google-cloud-platform-99163a9719ba 

[20] “Pub/Sub for Application & Data Integration | Google Cloud,” Google Cloud. https://cloud.google.com/pubsub

[21] “amazon kinesis vs microsoft azure stream analytics: Which Tool is Better for Your Next Project?” https://www.projectpro.io/compare/amazon-kinesis-vs-microsoft-azure-stream-analytics

[22] “Working with streaming data on AWS - Build Modern Data Streaming Architectures on AWS.” https://docs.aws.amazon.com/whitepapers/latest/build-modern-data-streaming-analytics-architectures/working-with-streaming-data-on-aws.html

[23] “TOP 5 IoT Platforms for 2025” https://www.cloud.studio/top-5-iot-platforms-for-2025/ 

[24] Sethmanheim, “What is Azure IoT Edge,” Microsoft Learn. https://learn.microsoft.com/en-us/azure/iot-edge/about-iot-edge


### 7. AI Disclosure
- **Tool:** Google AI Overview
- **Purpose:** Source gathering and research guidance
- **Extent:** Used to get suggestions on services from each of the CSPs and sources to read more on them.

