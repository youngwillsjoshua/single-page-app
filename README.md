Technical Assessment: Provisioning and Securing Single Page Application Infrastructure on AWS

Objective:
Provision a secure infrastructure on AWS to host a Single Page Application consisting of an S3 bucket, CloudFront distribution, API Gateway, and a Lambda function. Additionally, provide security recommendations and logging/monitoring suggestions for each service.

Infrastructure as Code (IaC) Tool: AWS CloudFormation

Infrastructure Provisioning

I initiated the process of provisioning the infrastructure required to host a Single Page Application on Amazon Web Services (AWS). Using AWS CloudFormation, i defined the resources needed for the SPA architecture:

S3 Bucket:
Created an S3 bucket to store the static assets of the SPA.
Configured the bucket for public read access and set the index document to 'index.html' for serving the SPA.

CloudFront Distribution:
Established a CloudFront distribution to serve the SPA content globally with low latency.
Configured the CloudFront distribution to use the S3 bucket as its origin, enforcing HTTPS-only access and redirecting HTTP to HTTPS.

API Gateway:
Provisioned an API Gateway to handle RESTful API requests from the SPA.
Named the API Gateway as "MyAPI" to serve as the backend for dynamic functionality.

Lambda Function:
Created a Lambda function to execute custom backend logic required by the SPA.

Security Recommendations

S3 Bucket:
Enable bucket versioning.
Restrict public access through bucket policies.
Utilize pre-signed URLs for controlled access.

CloudFront Distribution:
Enable HTTPS to secure data in transit.

API Gateway:
Use IAM for authentication and authorization.
Implement usage plans and API keys for rate limiting.

Lambda Function:
Apply least privilege IAM roles.
Implement function-level permissions.
Secure sensitive environment variables.


Logging and Monitoring:

S3 Bucket:
Enable access logging.
Utilize CloudTrail for API activity monitoring.

CloudFront Distribution:
Enable access logs.
Utilize CloudWatch for real-time monitoring.
Use CloudFront metrics for performance analysis.

API Gateway:
Enable CloudWatch logging.
Set up CloudWatch Alarms for monitoring.
Lambda Function:
Configure CloudWatch Logs for monitoring and error tracking.



