 Serverless Text-to-Speech Web Application

## 📌 Project Overview

This project is a fully serverless, cloud-native web application that converts user-provided text into speech (MP3 format) using AWS managed services.

The system is designed using an event-driven serverless architecture to ensure scalability, cost efficiency, and minimal infrastructure management.



# 🎯 Project Purpose

The main purpose of this project is to:

* Demonstrate serverless architecture using AWS
* Build a real-world cloud-integrated web application
* Implement API-driven backend communication
* Convert text to speech using AI services
* Showcase IAM-based secure service integration

This project simulates how modern SaaS applications integrate frontend interfaces with scalable cloud backends.


# 🏗 Architecture Overview

The application follows a layered serverless architecture:

User (Browser)
⬇
Frontend (Hosted in Amplify)
⬇
API Gateway (HTTP Endpoint)
⬇
Lambda Function (Business Logic)
⬇
Amazon Polly (Text-to-Speech Engine)
⬇
Amazon S3 (Audio Storage)
⬇
Audio URL returned to frontend



# 🔄 End-to-End Workflow

### 1️⃣ User Interaction

The user enters text in the web application and clicks **Convert**.

### 2️⃣ API Request

The frontend sends a **POST** request to the API Gateway endpoint:

```json
{
  "text": "Hello World"
}
```

### 3️⃣ API Gateway Routing

API Gateway receives the request and forwards it to Lambda.

### 4️⃣ Backend Processing

Lambda:

* Extracts the text
* Calls Amazon Polly
* Receives MP3 audio stream

### 5️⃣ Storage

Lambda uploads the generated MP3 file to S3.

### 6️⃣ Response

Lambda returns the S3 file URL.
The frontend loads the URL into an HTML `<audio>` player.



# ☁️ AWS Services Used and Why

## 🔹 AWS Amplify

Used for hosting and deploying the frontend.

**Why?**

* Easy frontend deployment
* Integrated CI/CD
* Automatic HTTPS
* Global CDN distribution



## 🔹 Amazon API Gateway

Used to expose a secure HTTP endpoint.

**Why?**

* Manages REST/HTTP APIs
* Handles routing
* Manages CORS configuration
* Connects frontend to backend securely



## 🔹 AWS Lambda

Used as the serverless backend compute service.

**Why?**

* No server management required
* Auto-scaling
* Pay-per-use pricing
* Executes only when triggered



## 🔹 Amazon Polly

Used for converting text into speech.

**Why?**

* High-quality neural voices
* Supports multiple languages
* Direct MP3 output
* Managed AI service



## 🔹 Amazon S3

Used to store generated MP3 files.

**Why?**

* Highly durable (11 9’s durability)
* Scalable object storage
* Secure access control
* Cost-effective storage



## 🔹 IAM (Identity and Access Management)

Used to grant permissions between services.

**Why?**

* Secure service-to-service communication
* Principle of Least Privilege
* Prevents unauthorized access



# 🏆 Advantages of This Project

✅ Fully Serverless Architecture
No infrastructure provisioning required.

✅ Automatic Scaling
Handles traffic spikes without manual scaling.

✅ Cost Efficient
Pay only for usage (Lambda execution + storage).

✅ High Availability
Uses AWS managed services with built-in redundancy.

✅ Secure
IAM-based access control and CORS protection.

✅ Production-Ready Pattern
Follows real-world SaaS architecture design.


# 🔐 Security Implementation

* IAM role attached to Lambda
* Limited S3 write permissions
* CORS configuration in API Gateway
* Stateless backend processing


# 📈 Scalability & Performance

* Lambda auto-scales based on request load
* API Gateway handles concurrent requests
* S3 provides highly durable object storage
* Polly processes requests on-demand

No manual scaling required.


# 💡 Technical Concepts Demonstrated

* Serverless computing
* REST API integration
* Event-driven architecture
* Cloud storage handling
* AI service integration
* IAM security model
* CORS handling in web applications


> <img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/0ea5dfac-c347-46a9-bb68-3a8101ff1d2d" />




