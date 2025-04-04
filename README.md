**AI Image Description Generator**

A serverless web application that generates AI-powered descriptions for uploaded images using AWS and Claude 3 Haiku (Amazon Bedrock).
🚀 Features

✅ Image Upload Interface – Users can upload images via a web interface hosted on AWS Fargate.

✅ AI-Powered Descriptions – Amazon Bedrock (Claude 3 Haiku) generates captions for uploaded images.

✅ Dynamic Gallery – View all uploaded images with their AI-generated descriptions.

✅ Automated CI/CD – GitHub Actions automates Docker builds and ECS Fargate deployments.

✅ Serverless Backend – Uses AWS Lambda, S3, and DynamoDB for scalability.

🛠️ Architecture Overview

The app follows a serverless microservices approach with:

    Frontend: Hosted on ECS Fargate (Docker) behind an Application Load Balancer (ALB).

    Backend:

        Lambda Functions (Upload, Process, Fetch, AI Description).

        S3 Buckets (Upload storage & processed assets).

        DynamoDB (Stores image metadata & AI descriptions).

    AI Integration: Amazon Bedrock (Claude 3 Haiku) for image analysis.

    CI/CD: GitHub Actions for automated deployments.

⚙️ Setup & Deployment
Prerequisites

    AWS Account with Admin permissions (or use AWS CloudShell).

    Domain name in Route 53 (for ALB).

    Docker installed (or use CloudShell).

    GitHub Account (for CI/CD).

    Amazon Bedrock Access (Request Claude 3 Haiku model access).

Deployment Steps

    Set Up AWS Resources

        Create S3 buckets (upload & assets).

        Set up DynamoDB (ImageMetadata table).

        Configure Lambda functions (upload, process, fetch, AI).

        Enable Bedrock model access (Claude 3 Haiku).

    Deploy Frontend (ECS Fargate)

        Build Docker image & push to Amazon ECR.

        Configure VPC, ALB, and ECS service.

    Set Up CI/CD (GitHub Actions)

        Configure OIDC authentication (AWS ↔ GitHub).

        Automate Docker builds & ECS deployments.

🔍 How It Works

    User Uploads an Image → Stored in S3, metadata saved in DynamoDB.

    Lambda Processes Image → Moves it to the assets bucket.

    AI Description Triggered → Lambda calls Bedrock, updates DynamoDB.

    Frontend Displays Images → Fetches metadata from DynamoDB.


📜 License

MIT License – Free for personal and commercial use.
💡 Future Improvements

    Add user authentication (Amazon Cognito).

    Support multiple AI models (e.g., Claude 3 Sonnet).

    Implement auto-tagging with AWS Rekognition.

🌟 Enjoy building! Contributions welcome.
For a detailed architecture diagram, check the project docs.
