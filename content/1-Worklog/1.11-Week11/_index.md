---

title: "Week 11 Worklog"
date: 2026-07-05
weight: 1
chapter: false
pre: " <b> 1.11. </b> "

---

## Week 11 Objectives

* Continue developing the AI AWS Architecture Reviewer project after completing the frontend foundation.
* Deploy the React frontend application to AWS.
* Configure Amazon S3 to host the React application.
* Configure Amazon CloudFront to distribute the frontend application.
* Implement API integration between the frontend and backend.
* Configure Amazon API Gateway.
* Deploy the AWS Lambda Upload Service.
* Store uploaded architecture diagrams in the Amazon S3 Input Bucket.
* Store review metadata in Amazon DynamoDB.
* Implement review-related APIs.
* Configure CORS between the frontend and backend.
* Test the upload flow from the frontend to the AWS backend services.
* Research an AI processing workflow using EventBridge, Step Functions, Lambda Diagram Extractor, and Amazon Bedrock.
* Research the AWS Well-Architected Framework for AI-based architecture evaluation.
* Prepare the implementation plan for Week 12.

---

## Tasks for This Week

| Day | Task | Start Date | Completion Date | Reference |
| --- | --- | --- | --- | --- |
| 1 | Review Week 10 progress and plan the AWS backend integration | 06/29/2026 | 06/29/2026 | |
| 2 | Deploy the React application to Amazon S3 and Amazon CloudFront | 06/30/2026 | 06/30/2026 | https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html |
| 3 | Configure Amazon API Gateway and CORS | 07/01/2026 | 07/01/2026 | https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-cors.html |
| 4 | Deploy the Lambda Upload Service and connect it to the S3 Input Bucket | 07/02/2026 | 07/02/2026 | https://docs.aws.amazon.com/lambda/latest/dg/welcome.html |
| 5 | Create a DynamoDB table and store review metadata | 07/03/2026 | 07/03/2026 | https://docs.aws.amazon.com/dynamodb/ |
| 6 | Implement the Review APIs and test the end-to-end upload flow | 07/04/2026 | 07/04/2026 | |
| 7 | Research EventBridge, Step Functions, Lambda Diagram Extractor, and Amazon Bedrock | 07/05/2026 | 07/05/2026 | https://docs.aws.amazon.com/bedrock/ |

---

## Results Achieved in Week 11

### 1. Frontend Deployment to AWS

* Reviewed the frontend implementation completed in Week 10.
* Built the React application for production deployment.
* Deployed the production build to Amazon S3.
* Configured Amazon CloudFront to distribute the frontend application.
* Understood the frontend redeployment process for future updates:
  * Build the React application.
  * Upload the build files to Amazon S3.
  * Create a CloudFront invalidation.
* Confirmed that the frontend application is accessible through CloudFront.

S3 bucket used to host the frontend:

```text
ai-aws-reviewer-frontend-tiersteam
```

CloudFront domain:

```text
https://d9353ayez9zar.cloudfront.net
```

CloudFront Distribution ID:

```text
E2JHD76RIC6AML
```

Deployment commands used:

```bash
npm run build

aws s3 sync dist s3://ai-aws-reviewer-frontend-tiersteam --delete

aws cloudfront create-invalidation --distribution-id E2JHD76RIC6AML --paths "/*"
```

---

### 2. Amazon API Gateway Configuration

* Configured Amazon API Gateway to enable communication between the frontend and backend.
* Created REST API routes for the upload and review features.
* Configured CORS so that the frontend can call the APIs.
* Connected the frontend application to API Gateway.

API Gateway endpoint:

```text
https://031hqksomd.execute-api.ap-southeast-1.amazonaws.com
```

Implemented API routes:

```text
POST /upload
GET /reviews
GET /reviews/{reviewId}
GET /reviews/{reviewId}/status
```

CORS configuration:

Allowed origins:

```text
http://localhost:5173
https://d9353ayez9zar.cloudfront.net
```

Allowed methods:

```text
GET
POST
OPTIONS
```

Allowed headers:

```text
content-type
authorization
```

---

### 3. AWS Lambda Upload Service

* Deployed the AWS Lambda Upload Service.
* Connected API Gateway to the Lambda function.
* Implemented uploaded-file validation.
* Generated a unique review ID for each upload.
* Uploaded architecture diagrams to the Amazon S3 Input Bucket.
* Stored review metadata in DynamoDB.
* Returned the upload response to the frontend.

Lambda function:

```text
ai-aws-reviewer-upload-service
```

Environment variables:

```text
INPUT_BUCKET = ai-aws-reviewer-input-bucket-tiersteam
TABLE_NAME = AIArchitectureReviews
MAX_FILE_SIZE_MB = 5
ALLOWED_ORIGINS = http://localhost:5173,https://d9353ayez9zar.cloudfront.net
```

Review ID format:

```text
REV-XXXXXXXX
```

Example:

```text
REV-C6A0D048
```

---

### 4. Amazon S3 Input Bucket

* Configured an Amazon S3 Input Bucket to store uploaded architecture diagrams.
* Stored uploaded files using a clear folder structure.
* Confirmed successful uploads from the frontend through Lambda.

Input bucket:

```text
ai-aws-reviewer-input-bucket-tiersteam
```

Key pattern:

```text
uploads/{reviewId}/{fileName}
```

Example:

```text
uploads/REV-C6A0D048/architecture-2.jpg
```

---

### 5. DynamoDB Review Metadata

* Created a DynamoDB table to store review metadata.
* Stored metadata after each successful upload.
* Prepared the metadata for the AI processing stage in the next phase.

Table name:

```text
AIArchitectureReviews
```

Partition key:

```text
reviewId
```

Stored data fields:

```text
reviewId
fileName
fileType
fileSize
s3InputBucket
s3InputKey
status
architectureType
uploadDate
updatedAt
```

Initial status:

```text
uploaded
```

---

### 6. Review API Development

* Implemented APIs for retrieving review information.
* Supported frontend pages such as Review History, Review Progress, and Report Detail.
* Confirmed that review records can be retrieved successfully.

Implemented APIs:

```text
GET /reviews
GET /reviews/{reviewId}
GET /reviews/{reviewId}/status
```

Prepared review status lifecycle:

```text
uploaded
→ processing
→ analyzed
```

Error status lifecycle:

```text
uploaded
→ processing
→ failed
```

Planned complete lifecycle:

```text
uploaded
→ processing
→ analyzed
→ report_generated
→ completed
```

---

### 7. Frontend and Backend Integration

* Connected the React frontend to API Gateway.
* Successfully uploaded architecture diagrams from the frontend.
* Tested the complete upload flow.
* Resolved CORS-related issues.
* Confirmed that uploaded files are stored in Amazon S3.
* Confirmed that metadata is stored in DynamoDB.

Completed flow:

```text
React Frontend
→ CloudFront
→ API Gateway
→ Lambda Upload Service
→ S3 Input Bucket
→ DynamoDB
```

---

### 8. AI Processing Workflow Research

* Researched the next implementation phase of the project.
* Studied how uploaded diagrams can be processed automatically.
* Designed a future AI processing workflow.

Proposed workflow:

```text
S3 Input Bucket
→ EventBridge
→ Step Functions
→ Lambda Diagram Extractor
→ Amazon Bedrock
→ DynamoDB Review Result
```

Researched the responsibilities of each AWS service:

**Amazon EventBridge**

* Detects Amazon S3 Object Created events.
* Automatically triggers the review workflow.

**AWS Step Functions**

* Orchestrates the review workflow.
* Manages the execution order of processing steps.
* Supports retries and error handling.

**AWS Lambda Diagram Extractor**

* Reads architecture diagrams from Amazon S3.
* Extracts architecture information.
* Prepares prompts for AI analysis.
* Calls Amazon Bedrock.
* Stores AI review results in DynamoDB.

**Amazon Bedrock**

* Analyzes AWS architecture diagrams.
* Evaluates architectures based on the AWS Well-Architected Framework.
* Generates structured AI evaluation results.

---

### 9. AWS Well-Architected Framework Research

* Researched the AWS Well-Architected Framework.
* Prepared the evaluation criteria to be used by Amazon Bedrock.

The AI review will evaluate the architecture based on the following criteria:

```text
Security
Reliability
Performance Efficiency
Cost Optimization
Operational Excellence
Sustainability
```

The expected AI review output includes:

```text
Architecture Summary
Detected AWS Services
Detected Connections
Security Assessment
Reliability Assessment
Performance Efficiency Assessment
Cost Optimization Assessment
Operational Excellence Assessment
Sustainability Assessment
Overall Score
Risk Level
Recommendations
Priority Actions
```

---

### 10. Architecture Review Planning

* Reviewed the current AWS architecture of the project.
* Confirmed the completed implementation:

```text
User
→ CloudFront
→ S3 React App
→ API Gateway
→ Lambda Upload Service
→ S3 Input Bucket
→ DynamoDB Metadata
```

* Identified the remaining components to be implemented:

```text
S3 Input Bucket
→ EventBridge
→ Step Functions
→ Lambda Diagram Extractor
→ Amazon Bedrock
→ DynamoDB Review Result
```

* Planned the future implementation:

```text
Lambda PDF Generator
→ S3 Report Bucket
→ SNS Email Notification
```

---

## Self-Assessment

* Improved my understanding of deploying React applications to AWS.
* Gained a better understanding of using Amazon S3 and CloudFront for frontend deployment.
* Gained a better understanding of API Gateway configuration.
* Gained a better understanding of AWS Lambda deployment.
* Gained a better understanding of metadata design in Amazon DynamoDB.
* Gained a better understanding of frontend and backend integration.
* Improved my ability to troubleshoot CORS issues.
* Gained a better understanding of serverless event-driven architecture.
* Gained a better understanding of EventBridge and Step Functions for workflow orchestration.
* Gained a better understanding of how Amazon Bedrock can analyze architectures.
* Gained a better understanding of the AWS Well-Architected Framework.

I am now able to:

* Deploy a React application to AWS.
* Configure Amazon CloudFront.
* Configure API Gateway.
* Deploy a Lambda Upload Service.
* Store uploaded diagrams in Amazon S3.
* Store metadata in DynamoDB.
* Develop upload and review APIs.
* Integrate the frontend with backend services.
* Design an AI processing workflow.
* Explain the roles of EventBridge, Step Functions, Lambda Diagram Extractor, and Amazon Bedrock.

---

## Next Steps

* Deploy Amazon EventBridge.
* Configure an EventBridge rule for Amazon S3 Object Created events.
* Create an AWS Step Functions Review Workflow.
* Deploy the Lambda Diagram Extractor.
* Configure IAM permissions for the Lambda Diagram Extractor.
* Enable model access in Amazon Bedrock.
* Connect the Lambda Diagram Extractor to Amazon Bedrock.
* Design a Bedrock prompt for analysis based on the AWS Well-Architected Framework.
* Store AI review results in DynamoDB.
* Automatically update review statuses.
* Test the complete AI workflow:

```text
Upload Diagram
→ S3 Input Bucket
→ EventBridge
→ Step Functions
→ Lambda Diagram Extractor
→ Amazon Bedrock
→ DynamoDB
```

* Update the Review Progress page with real-time processing statuses.
* Display AI-generated review results on the Report Detail page.
* Continue implementing:

```text
Lambda PDF Generator
→ S3 Report Bucket
→ SNS Email Notification
```

* Continue end-to-end testing and validate the complete serverless architecture.
---