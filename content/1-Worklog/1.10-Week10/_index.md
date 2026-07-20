
---
title: "Week 10 Worklog"
date: 2026-06-28
weight: 1
chapter: false
pre: " <b> 1.10. </b> "

---

## Week 10 Objectives

* Begin the Capstone project development phase after completing the foundational AWS modules.
* Discuss and agree on the **AI AWS Architecture Reviewer** project topic.
* Identify the real-world problem that the project aims to solve.
* Identify the target users and main use cases.
* Analyze Functional Requirements and Non-Functional Requirements.
* Build the overall system architecture diagram.
* Design the processing flow from architecture submission to assessment report delivery.
* Select suitable AWS services for each system component.
* Apply a Serverless Architecture to improve scalability and reduce operational workloads.
* Define how Amazon Bedrock will evaluate architectures based on the AWS Well-Architected Framework.
* Design mechanisms for storing architecture images, assessment results, PDF reports, and review history.
* Establish security, monitoring, and cost optimization principles for the system.
* Divide the initial project scope and responsibilities among team members.

---

## Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| 1 | - Discussed possible AWS project topics with the team <br> - Analyzed the difficulties students and Cloud Engineers face when reviewing architecture diagrams <br> - Proposed the AI AWS Architecture Reviewer idea <br> - Agreed on the initial project objectives and scope | 22/06/2026 | 22/06/2026 | |
| 2 | - Identified the system's target users <br> - Defined the main Use Cases <br> - Identified three input methods: architecture images, Draw.io files, and architecture descriptions <br> - Analyzed the expected output that users should receive | 23/06/2026 | 23/06/2026 | |
| 3 | - Built the Functional Requirements list <br> - Defined functions for identifying AWS services, analyzing connections, reviewing architectures, and estimating costs <br> - Defined requirements for generating PDF reports, storing review history, and sending email notifications | 24/06/2026 | 24/06/2026 | |
| 4 | - Analyzed Non-Functional Requirements <br> - Selected a Serverless Architecture <br> - Proposed CloudFront, S3, API Gateway, Lambda, EventBridge, Step Functions, Bedrock, DynamoDB, SNS, CloudWatch, and IAM <br> - Defined requirements for security, scalability, and cost optimization | 25/06/2026 | 25/06/2026 | |
| 5 | - Designed the overall architecture diagram <br> - Built the flow from the React interface to API Gateway and the Lambda Upload Service <br> - Designed the Amazon S3 Input Bucket and Report Bucket <br> - Selected EventBridge and Step Functions as the Workflow orchestration layer | 26/06/2026 | 26/06/2026 | |
| 6 | - Designed the Processing Layer <br> - Defined the functions of the Diagram Extractor Lambda, Cost Tool Lambda, and PDF Generator Lambda <br> - Designed the integration flow with Amazon Bedrock <br> - Defined Retry, Error Handling, and DynamoDB history storage mechanisms | 27/06/2026 | 27/06/2026 | |
| 7 | - Completed the system workflow diagram <br> - Reviewed the responsibilities of each AWS service <br> - Added IAM Least Privilege, CloudWatch Monitoring, SSE-S3 Encryption, and SNS Notifications <br> - Presented the project idea to the community and collected feedback | 28/06/2026 | 28/06/2026 | |

---

## Week 10 Outcomes

### 1. Project Topic Agreement

The team agreed to develop the following project:

## AI AWS Architecture Reviewer

AI AWS Architecture Reviewer is a system that uses artificial intelligence to automatically analyze and evaluate AWS architecture diagrams.

Users can provide architecture information through three methods:

* Upload an AWS architecture image.
* Upload a Draw.io file.
* Enter an architecture description directly as text.

The system will:

* Identify the AWS services appearing in the architecture.
* Determine the relationships and connection flows between services.
* Convert architecture data into a structured format.
* Evaluate the design according to the AWS Well-Architected Framework.
* Identify strengths and weaknesses.
* Detect design errors and potential risks.
* Recommend improvements.
* Estimate service costs.
* Generate an assessment report in PDF format.
* Store review history.
* Send an email notification when the assessment is completed.

---

### 2. Identifying the Problem to Be Solved

Reviewing an AWS architecture normally requires knowledge across several service categories, including:

* Compute.
* Storage.
* Networking.
* Database.
* Security.
* Monitoring.
* High Availability.
* Cost Optimization.
* Disaster Recovery.

Students and beginners in Cloud Computing may experience several difficulties:

* They may not identify all services in a diagram.
* They may not understand the relationships between components.
* They may not detect a Single Point of Failure.
* They may not identify Security Group or IAM issues.
* They may not know whether an architecture is scalable.
* They may not know how to apply the AWS Well-Architected Framework.
* They may find it difficult to estimate service costs.
* Manual reviews may require a significant amount of time.

The project aims to partially automate this process and provide assessment results in a more understandable format.

---

### 3. Identifying Target Users

The main target user groups are:

#### Cloud Computing Students

* Upload architecture assignments.
* Receive feedback about design issues.
* Develop a better understanding of AWS services.
* Learn how to apply the AWS Well-Architected Framework.
* Compare designs before and after improvement.

#### Cloud Engineers

* Quickly review an architecture diagram.
* Identify missing components.
* Receive cost and performance optimization recommendations.
* Generate an initial assessment report.
* Store the history of previous reviews.

#### Project Development Teams

* Evaluate architectures before implementation.
* Compare multiple design approaches.
* Share review reports with other team members.
* Track recommendations that still need to be implemented.

---

### 4. Main System Functions

#### Input Data Management

The system supports:

* Uploading PNG or JPG images.
* Uploading Draw.io files.
* Entering architecture descriptions as text.
* Validating file types.
* Validating file sizes.
* Storing input data in Amazon S3.
* Creating a Review ID for each request.

#### Architecture Diagram Analysis

The system performs the following operations:

* Identifies AWS service names.
* Identifies Nodes in the diagram.
* Identifies connections between Nodes.
* Determines the direction of data flow.
* Standardizes data into JSON.
* Detects unrecognized components.

#### Architecture Evaluation

Amazon Bedrock is used to assess architectures according to the six pillars of the AWS Well-Architected Framework:

* Operational Excellence.
* Security.
* Reliability.
* Performance Efficiency.
* Cost Optimization.
* Sustainability.

#### Cost Calculation

The system is expected to:

* Identify services that may generate costs.
* Receive estimated configurations for each service.
* Calculate estimated monthly costs.
* Provide the total estimated cost.
* Warn users about high-cost services.
* Recommend cost optimization approaches.

#### Output Generation

The output includes:

* A list of identified services.
* Connection flows between services.
* Scores for each pillar.
* Strengths.
* Weaknesses.
* Risks.
* Improvement recommendations.
* Estimated costs.
* A PDF report.
* Review status.

---

### 5. Functional Requirements

| ID | Functional Requirement |
| --- | --- |
| FR-01 | Users can access the Web Application |
| FR-02 | Users can upload architecture diagram images |
| FR-03 | Users can upload Draw.io files |
| FR-04 | Users can enter architecture descriptions |
| FR-05 | The system validates file types and sizes |
| FR-06 | The system stores input data in Amazon S3 |
| FR-07 | The system automatically starts the Review Workflow |
| FR-08 | The system identifies AWS services |
| FR-09 | The system determines relationships between services |
| FR-10 | The system converts the architecture into JSON data |
| FR-11 | The system evaluates the architecture according to the AWS Well-Architected Framework |
| FR-12 | The system detects design issues and risks |
| FR-13 | The system recommends improvements |
| FR-14 | The system estimates architecture costs |
| FR-15 | The system generates a PDF report |
| FR-16 | The system stores review history |
| FR-17 | The system sends an email notification when processing is completed |
| FR-18 | Users can view previous assessment results |
| FR-19 | Users can download PDF reports |
| FR-20 | The system records Logs for each processing step |

---

### 6. Non-Functional Requirements

#### Scalability

* Use a Serverless Architecture.
* Lambda automatically scales according to the number of Requests.
* Amazon S3 supports storing a large number of Objects.
* DynamoDB scales according to traffic.
* Step Functions manages multiple independent Workflows.

#### Availability

* Use managed AWS services.
* Avoid dependency on a single EC2 Instance.
* Design Retry and Error Handling mechanisms for the Workflow.
* Store processing status for troubleshooting when errors occur.

#### Security

* Apply IAM Least Privilege.
* Encrypt data stored in Amazon S3.
* Control API access.
* Keep the Input Bucket and Report Bucket private.
* Validate file formats before processing.
* Avoid recording sensitive information in Logs.

#### Performance

* CloudFront distributes the Web interface.
* Lambda performs asynchronous processing.
* EventBridge and Step Functions reduce dependencies between components.
* DynamoDB provides fast review history retrieval.

#### Cost

* Use a Pay-as-you-go model.
* Avoid maintaining continuously running servers.
* Use S3 Lifecycle Rules for older data.
* Limit Lambda execution time.
* Monitor Amazon Bedrock and CloudWatch Logs costs.

---

### 7. Overall System Architecture

The architecture is divided into the following layers:

```text
Presentation Layer
        ↓
API and Upload Layer
        ↓
Storage and Event Layer
        ↓
Processing and Orchestration Layer
        ↓
AI Analysis and Cost Calculation Layer
        ↓
Report and Notification Layer
        ↓
Monitoring and Security Layer
```

The selected services are:

| Component | AWS Service |
| --- | --- |
| Frontend distribution | Amazon CloudFront |
| React Frontend storage | Amazon S3 |
| REST API | Amazon API Gateway |
| Upload processing | AWS Lambda |
| Input diagram storage | Amazon S3 |
| Event publishing | Amazon EventBridge |
| Workflow orchestration | AWS Step Functions |
| Diagram extraction | AWS Lambda |
| AI analysis | Amazon Bedrock |
| Cost calculation | AWS Lambda |
| PDF generation | AWS Lambda |
| Report storage | Amazon S3 |
| Review history storage | Amazon DynamoDB |
| Email notification | Amazon SNS |
| Logging and Monitoring | Amazon CloudWatch |
| Access control | AWS IAM |

---

### 8. Overall System Workflow

```text
User
    ↓
Amazon CloudFront
    ↓
React Frontend on Amazon S3
    ↓
Amazon API Gateway
    ↓
Lambda Upload Service
    ↓
Amazon S3 Input Bucket
    ↓
Amazon EventBridge
    ↓
AWS Step Functions
    ↓
Diagram Extractor Lambda
    ↓
Amazon Bedrock
    ↓
Cost Tool Lambda
    ↓
PDF Generator Lambda
    ↓
Amazon S3 Report Bucket
    ↓
Amazon DynamoDB
    ↓
Amazon SNS
    ↓
Email Notification to the User
```

---

### 9. Detailed Processing Flow

#### Step 1 – Access the Web Application

The user accesses the application through Amazon CloudFront.

CloudFront provides:

* Content distribution through Edge Locations.
* Reduced latency.
* HTTPS support.
* Caching for React, JavaScript, and CSS files.

#### Step 2 – Distribute the React Frontend

CloudFront retrieves interface content from an S3 Static Website or S3 Origin.

The Frontend provides:

* An image upload form.
* A Draw.io upload form.
* An architecture description input field.
* A Review status tracking page.
* A result display page.

#### Step 3 – Submit the Architecture Diagram

The Frontend sends a Request to API Gateway.

The Request may contain:

* File Metadata.
* Input data type.
* User email.
* Additional descriptions.
* Configuration values used for cost estimation.

#### Step 4 – Validate the Upload Request

API Gateway forwards the Request to the Lambda Upload Service.

Lambda validates:

* File format.
* File size.
* Metadata.
* Required fields.
* Access permissions.

#### Step 5 – Store the Uploaded Architecture

The data is stored in the Amazon S3 Input Bucket.

The expected Object Key structure is:

```text
input/
└── <review-id>/
    ├── original-diagram.png
    ├── architecture.drawio
    └── metadata.json
```

#### Step 6 – Publish an Object Created Event

When an Object is created, Amazon S3 publishes an event that EventBridge receives and processes.

The Event may contain:

* Bucket Name.
* Object Key.
* Object Size.
* Event Time.
* Review ID.

#### Step 7 – Start the Review Workflow

EventBridge starts an AWS Step Functions execution.

Step Functions is responsible for:

* Orchestrating Lambda functions.
* Managing processing status.
* Retrying temporary errors.
* Catching unrecoverable errors.
* Tracking each processing step.
* Passing data between States.

#### Step 8 – Extract Services and Connections

The Diagram Extractor Lambda processes data according to the input type.

For images:

* Normalize the image.
* Send the image to a model that supports image analysis.
* Identify services and connections.

For Draw.io files:

* Read XML data.
* Identify Nodes.
* Identify Edges.
* Extract Labels and Metadata.

For text descriptions:

* Normalize the content.
* Identify service names.
* Identify processing flows.

#### Step 9 – Convert the Architecture into JSON

The architecture data is standardized:

```json
{
  "services": [
    {
      "id": "service-01",
      "name": "Amazon S3",
      "type": "Storage"
    },
    {
      "id": "service-02",
      "name": "AWS Lambda",
      "type": "Compute"
    }
  ],
  "connections": [
    {
      "source": "service-01",
      "target": "service-02",
      "relationship": "ObjectCreatedEvent"
    }
  ]
}
```

#### Step 10 – Estimate Costs

The Cost Tool Lambda receives the list of services and configurations.

An estimated result may include:

```text
Amazon S3        : 3 USD/month
AWS Lambda       : 2 USD/month
API Gateway      : 4 USD/month
Amazon Bedrock   : 15 USD/month
CloudWatch       : 2 USD/month
--------------------------------
Estimated Total  : 26 USD/month
```

The cost is only an estimate and depends on:

* Region.
* Number of Requests.
* Storage capacity.
* Data Transfer.
* Lambda execution duration.
* Amazon Bedrock model.
* Number of Tokens or amount of processed data.

#### Step 11 – Analyze the Architecture

Amazon Bedrock receives the JSON data and evaluates the architecture.

The expected Prompt instructs the AI to:

* Check the services being used.
* Analyze connection flows.
* Detect Single Points of Failure.
* Evaluate scalability.
* Analyze Security.
* Analyze Reliability.
* Analyze Performance.
* Analyze Cost.
* Analyze Sustainability.
* Recommend improvements.

#### Step 12 – Generate the Result

The assessment result is standardized into structured data:

```json
{
  "overallScore": 78,
  "strengths": [],
  "risks": [],
  "recommendations": [],
  "pillarScores": {
    "security": 75,
    "reliability": 70,
    "performance": 80,
    "costOptimization": 76
  }
}
```

#### Step 13 – Store Review History

DynamoDB stores:

* Review ID.
* User ID or Email.
* Input Type.
* Input S3 Key.
* Review Status.
* Result Summary.
* Overall Score.
* Created Time.
* Completed Time.
* Report S3 Key.
* Error Message when applicable.

#### Step 14 – Store the PDF Report

The PDF Generator Lambda creates a report and stores it in the S3 Report Bucket.

Expected structure:

```text
reports/
└── <review-id>/
    └── architecture-review-report.pdf
```

The Report Bucket uses SSE-S3 Encryption to protect data at rest.

#### Step 15 – Send a Notification

Amazon SNS sends an email notification when the Review is completed.

The notification contains:

* Review ID.
* Status.
* Overall Score.
* Completion time.
* A link back to the Web Application.

---

### 10. Processing Layer Design

The Processing Layer includes:

```text
Amazon EventBridge
        ↓
AWS Step Functions
        ↓
Diagram Extractor Lambda
        ↓
Amazon Bedrock
        ↓
Cost Tool Lambda
        ↓
PDF Generator Lambda
```

The role of Step Functions includes:

* Managing the Workflow.
* Preventing all logic from being placed in a single Lambda function.
* Supporting Retry.
* Supporting Catch.
* Storing the status of each step.
* Providing Execution History.
* Helping identify failed processing steps.

Example statuses:

```text
RECEIVED
    ↓
EXTRACTING
    ↓
ANALYZING
    ↓
CALCULATING_COST
    ↓
GENERATING_REPORT
    ↓
COMPLETED
```

Failure statuses:

```text
FAILED_EXTRACTION
FAILED_ANALYSIS
FAILED_COST_CALCULATION
FAILED_REPORT_GENERATION
```

---

### 11. Amazon DynamoDB Design

DynamoDB was selected for storing Review history because:

* No Database server management is required.
* It is scalable.
* It is suitable for JSON-formatted data.
* It supports retrieval using a Review ID.
* It is suitable for a Serverless Architecture.
* It integrates with AWS Lambda.

Initial design:

```text
Partition Key: reviewId
```

Attributes:

```text
reviewId
userId
email
inputType
inputObjectKey
status
overallScore
resultSummary
reportObjectKey
createdAt
updatedAt
completedAt
errorMessage
```

A Global Secondary Index can be added:

```text
GSI:
Partition Key: userId
Sort Key: createdAt
```

The GSI supports retrieving each user's Review history in chronological order.

---

### 12. Security Design

#### IAM Least Privilege

Each Lambda function uses a separate IAM Role.

Examples:

* The Upload Lambda can only write to the Input Bucket.
* The Diagram Extractor can only read from the Input Bucket.
* The Cost Tool can access only the required data.
* The PDF Generator can only write to the Report Bucket.
* The Notification Function can only Publish to SNS.
* Step Functions can invoke only the required Lambda functions.

#### Amazon S3 Protection

* Enable Block Public Access.
* Encrypt Objects.
* Prevent users from directly accessing Buckets.
* Use Pre-Signed URLs for Upload and Download operations when required.
* Separate the Input Bucket from the Report Bucket.
* Configure Lifecycle Rules for old data.

#### API Protection

The following approaches were considered:

* API Keys.
* Amazon Cognito.
* IAM Authorization.
* Rate Limiting.
* Request Validation.
* AWS WAF in a future development phase.

#### Data Protection

* Do not store sensitive information in Logs.
* Limit the validity period of Pre-Signed URLs.
* Validate file formats.
* Limit upload file sizes.
* Reject unsupported file types.

---

### 13. Monitoring and Logging

Amazon CloudWatch is used to monitor:

* Number of API Requests.
* API Error Rate.
* Lambda Duration.
* Lambda Errors.
* Lambda Throttles.
* Step Functions Execution Status.
* S3 Event Processing.
* Bedrock Requests.
* DynamoDB Errors.
* SNS Delivery Status.
* Total Review processing time.

Expected Log Groups:

```text
/aws/lambda/upload-service
/aws/lambda/diagram-extractor
/aws/lambda/cost-tool
/aws/lambda/pdf-generator
/aws/stepfunctions/review-workflow
```

Expected Alarms:

* Lambda Errors exceed the threshold.
* API Gateway returns too many `5xx` errors.
* A Step Functions Execution fails.
* DynamoDB Requests are throttled.
* A Review exceeds the expected processing time.
* Amazon Bedrock costs increase abnormally.

---

### 14. Cost Optimization Design

The following approaches were identified:

* Use Serverless services instead of continuously running EC2 Instances.
* Lambda generates costs only when invoked.
* Use DynamoDB On-Demand Capacity during the initial phase.
* Use S3 Lifecycle Rules to move older data to lower-cost Storage Classes.
* Delete input images after the required retention period.
* Limit upload file sizes.
* Limit Lambda execution duration.
* Select an Amazon Bedrock model appropriate for the workload.
* Avoid passing entire images repeatedly between processing steps.
* Configure CloudWatch Log Retention.
* Use CloudFront Caching for the Frontend.

---

### 15. Expected Project Outcomes

The project aims to achieve the following outcomes:

* Reduce the time required to review AWS architectures.
* Support students learning Cloud Computing.
* Help Cloud Engineers perform initial architecture reviews.
* Automatically apply the AWS Well-Architected Framework.
* Detect common architecture design issues.
* Recommend cost and performance optimizations.
* Provide structured assessment reports.
* Store review history.
* Support the comparison of multiple architecture versions.
* Create a platform that can be expanded in the future.

---

### 16. MVP Scope

The expected MVP includes:

* Uploading architecture images.
* Entering architecture descriptions.
* Storing inputs in Amazon S3.
* Automatically starting the Workflow.
* Extracting a list of services.
* Calling Amazon Bedrock for evaluation.
* Displaying scores and recommendations.
* Generating a PDF report.
* Storing history in DynamoDB.
* Sending email notifications.

Possible future features:

* Direct analysis of complex Draw.io files.
* Drag-and-drop diagram creation on the Web.
* Comparison of two architecture versions.
* Advanced integration with AWS Pricing APIs.
* Automatic generation of an optimized architecture diagram.
* Generation of CloudFormation or Terraform Templates.
* Support for multiple Cloud Providers.
* User authentication with Amazon Cognito.
* A Dashboard for Review history statistics.

---

### 17. Identified Technical Risks

#### AI Incorrectly Identifies Services

Possible causes:

* Low-resolution images.
* Unclear icons.
* Complex diagrams containing many components.
* Abbreviated service names.
* Overlapping connection lines.

Proposed solutions:

* Require a minimum image quality.
* Allow users to edit the identified service list.
* Combine OCR, XML parsing, and AI.
* Require Amazon Bedrock to return JSON using a defined Schema.

#### Inconsistent Assessment Results

Proposed solutions:

* Standardize Prompts.
* Reduce the Temperature value.
* Use an Output Schema.
* Store Prompt Versions.
* Build a fixed assessment criteria set.
* Test with multiple sample architectures.

#### Inaccurate Cost Estimates

Possible causes:

* Missing configuration information.
* Prices differ by Region.
* Actual traffic is unknown.
* Some services use complex pricing models.

Proposed solutions:

* Clearly state that the result is an estimate.
* Ask users to provide additional configurations.
* Document the assumptions used.
* Allow users to select a Region.
* Separate each cost component.

#### Workflow Exceeds the Expected Processing Time

Proposed solutions:

* Divide the process into smaller Lambda functions.
* Use Step Functions.
* Process tasks asynchronously.
* Configure appropriate Timeouts.
* Store intermediate states.
* Retry temporary errors.

---

## Skills Developed

* Problem analysis and project topic selection.
* Target user identification.
* Use Case development.
* Functional Requirements definition.
* Non-Functional Requirements definition.
* Serverless Architecture design.
* Event-Driven processing flow design.
* AWS service selection based on functional responsibilities.
* Workflow design using Step Functions.
* DynamoDB data design.
* IAM Least Privilege design.
* Monitoring design using CloudWatch.
* Technical risk identification.
* MVP scope definition.
* Presenting technical ideas to the team and community.

---

## Self-Evaluation

* The team agreed on a practical project topic that is suitable for the program.
* The project combines Cloud Computing, Serverless Architecture, and Generative AI.
* The problem, target users, and main functions were identified.
* Suitable AWS services were selected.
* The overall architecture and processing flow were designed.
* The roles of EventBridge and Step Functions in the Workflow were understood.
* A method for using Amazon Bedrock to assess architectures was identified.
* A plan for storing reports and Review history was created.
* Security, monitoring, and cost requirements were considered during the design phase.
* Team communication, analysis, and system design skills were improved.

Areas for further improvement:

* Complete the Database Schema.
* Select the exact Amazon Bedrock model.
* Build detailed assessment Prompts.
* Design the API Contract.
* Standardize input and output JSON formats.
* Determine how Draw.io files will be analyzed.
* Research cost estimation methods.
* Design the user interface.
* Build the testing plan.
* Estimate the operating cost of the project itself.

---

## Next Steps

* Create a shared Repository for the team.
* Build the Frontend and Backend folder structures.
* Design the Web interface using React.
* Deploy an S3 Bucket for the Frontend.
* Configure Amazon CloudFront.
* Build API Gateway.
* Develop the Lambda Upload Service.
* Design the Pre-Signed URL mechanism.
* Create the Input Bucket and Report Bucket.
* Create the DynamoDB Review Table.
* Build the Step Functions State Machine.
* Develop the Diagram Extractor.
* Test Amazon Bedrock.
* Build the architecture assessment Prompt.
* Assign specific responsibilities to each team member.
* Prepare to implement the first MVP version.

---

