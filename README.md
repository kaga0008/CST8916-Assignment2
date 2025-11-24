# CST8916 Assignment 2
## Elizabeth Kaganovsky (040956895)

### 1. Executive Summary 
The following document will provide a high-level comparison of roughly equivalent services in Microsoft Azure, Amazon Web Services and Google Cloud Platform

### 2. Introduction
Cloud computing is most often provided by one of three cloud service providers (CSPs). Amazon Web Services, launched in 2006, remains the market leader with a massive variety of services for countless industries. Since 2010 Microsoft has offered Azure, which brings with it a unique integration with Microsoft products and sovereignty options for governments. Google Cloud Platform caught up in 2011, offering customers a variety of tools for data analytics and machine learning, with robust support for containerized workloads. There is a myriad of additional cloud providers (IBM, Oracle, and Tencent among them), but to limit the scope of this document, only the three largest CSPs will be studied. The purpose of this comparison is to gain a deeper understanding of the services offered by the three major CSPs--while the services are considered rough equivalents, there are intricacies in each offering that can completely derail development if unaccounted for in the development process.

### 3.1. RESTful API Services
#### 3.1.1. Microsoft Azure
Microsoft offers Azure API Management (APIM) as a comprehensive API management PaaS solution that supports the entire API lifecycle--designing, publishing, securing, monitoring, and developing. APIM also supports self-hosted managed gateways, where an API gateway is deployed into the same environment as that which hosts the APIs, which is ideal for hybrid and multi-cloud setups since users will reap all the benefits of a PaaS solution while also complying with local rules and regulations on data and operational sovereignty. APIM also has the benefit of policies, small collections of statements that modify the behaviour of an API without requiring changes to the backend--among the 75 provided include policies for enforcing authentication or format transformation (such as changing incoming JSON to XML), but user-defined policies can also be created. On the financial side, Azure API Management uses two pricing models--tiered and consumption. Each tier (Developer, Basic, Standard, and Premium) requires a monthly base cost per unit, with additional charges for API requests above a certain threshold. Comparatively, the consumption tier incurs no fixed costs, with billing being based on the number of API requests to the service. This pricing model makes APIM a better choice for large, constant API loads with good predictability.
- https://learn.microsoft.com/en-us/azure/api-management/api-management-howto-policies
- https://learn.microsoft.com/en-us/azure/api-management/plan-manage-costs 

#### 3.1.2. Amazon Web Services
For RESTful API services, AWS offers Amazon API Gateway. This service is exclusively serverless, unlike APIM which also offers the option of a managed service approach, a significant drawback for companies that require on-prem options for regulational compliance. It also lacks policies like those of APIM, instead requiring Lambda functions to fill the gap, which can become expensive as Lambda functions require a fee per execution. AWS API Gateway uses a pay-per-use model, in which API calls are charged per sets of one million requests, with additional fees for the amount of data transferred, making it preferrable for variable API loads that experience the bulk of their traffic through usage spikes.

- https://apix-drive.com/en/blog/other/amazon-api-gateway-vs-azure-api-management
- https://www.gravitee.io/comparison/aws-vs-azure 
- https://onlu.ch/en/azure-api-management-vs-aws-api-gateway-a-comparison-for-banks-and-insurance-companies/

#### 3.1.3. Google Cloud Platform
Google Cloud Platform offers multiple services for RESTful APIs depending on the scale of the application. For smaller projects and local testing, Google Cloud Endpoints (GCE) makes for a good solution, a user-managed service that allows the management of APIs in the GCP ecosystem with basic security and inexpensive pricing options. GCE is most beneficial to developers seeking to host the gateway on their own runtime, but also desire the control plane features that come with API Gateway but without the higher price tag. GCE pricing is based on the number of calls made to the API.

API Gateway works similarly to GCE, but is fully managed and and simplifies the management of APIs for other GCP services such as Cloud Functions and App Engine. API Gateway is ideal for medium scale use cases, where consistent governance and third-party API management are not yet issues. Similar to AWS API Gateway, GCP API Gateway is billed based on the number of requests and amount of data transferred.

For an enterprise-grade alternative, GCP provides Apigee API Management, a fully managed solution designed to deal with large volumes of traffic while maintaining high uptime. Apigee allows for more advanced features such as detailed analytics, security and monetization. Like APIM, Apigee can operate in hybrid/multi-cloud environments, and is recommended by GCP for applications expected to become complex or highly scaled, to avoid having to later change to another platform. Apigee offers three billing options--pay-as-you-go (based on call volume, proxy deployments and add-ons like analytics), tiered subscription based (standard, enterprise, and enterprise plus), and evaluation (try for free over 60 days).

- https://cloud.google.com/blog/products/application-modernization/choosing-between-apigee-api-gateway-and-cloud-endpoints 
- https://cloud.google.com/apigee/pricing 

### 3.2. GraphQL Services
#### 3.2.1. Microsoft Azure
GraphQL is supported by a multitude of Azure services, the choice of which to use depends on the needs of the application. For existing GraphQL apps, Azure App Services or Azure Container Apps allow for easy deployment with no/minimal changes to code. For apps that exist but do not have GraphQL functionality yet, Data API Builder can create GraphQL endpoints with little coding to add support. When building a GraphQL API layer from scratch to serve existing APIs, Azure API Management with GraphQL transformation can be used. APIM 

- https://learn.microsoft.com/en-us/azure/developer/javascript/graphql-developer-guide 

#### 3.2.2. Amazon Web Services
AWS AppSync is a managed serverless service that provides GraphQL support to the AWS ecosystem. Unlike 

#### 3.2.3. Google Cloud Platform

### 3.3. WebSocket Services

### 3.4. Data Streaming Services

### 3.5. Stream Analytics

### 4. Use Case Analysis

### 4.1. Use Case 1: Credit Card Fraud Detection
Fraud is best detected right when it happens to minimize the impact it has on organizations and individuals who may be victimized

### 4.2. Use Case 2: Multiplayer gaming

### 5. Conclusion

### 6. References

