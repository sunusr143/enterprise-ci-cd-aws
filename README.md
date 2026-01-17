# CI/CD Architecture – enterprise-ci-cd-aws

## Overview
This repository demonstrates a production-style CI pipeline using Jenkins on AWS.
The application (Spring Boot PetClinic) is used strictly as a reference workload.

## Architecture Flow
GitHub  
→ Jenkins (EC2)  
→ Maven Build  
→ Docker Image Build  
→ Amazon ECR  

## Key Design Decisions
- Jenkins runs on an EC2 instance inside AWS
- Jenkins uses an IAM role (no static AWS credentials)
- Docker images are built inside the pipeline
- Images are pushed to Amazon ECR
- No deployment stage is included by design

## Security Considerations
- Least-privilege IAM policy for ECR access
- No secrets committed to the repository
- AWS authentication handled via instance profile

## Scope Note
This repository focuses on CI and artifact management.
Infrastructure provisioning and deployment strategies are intentionally out of scope.
