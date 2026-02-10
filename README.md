# Text-to-Audio-Conveerter
## Project Architecture

**Text-to-Speech Conversion using AWS Serverless Services**

## 🔹 Architecture Overview

This project follows an **event-driven serverless architecture** using AWS managed services to automatically convert text files into speech (MP3 format).


## 🔹 Architecture Flow (Step-by-Step)

User / System
   ↓
S3 Source Bucket
(text2talk-source-transcript-bucket)
   ↓  (S3 Event Notification)
AWS Lambda Function (text2talk)
   ↓
Amazon Polly (Text → Speech)
   ↓
S3 Target Bucket
(text2talk-target-audio-bucket)


## 🔹 Component-wise Explanation

### 1️⃣ Amazon S3 – Source Bucket

**Bucket Name:** `text2talk-source-transcript-bucket`

* Stores input text transcript files (`.txt`)
* Acts as the entry point of the workflow
* Configured with **S3 Event Notifications**

---

### 2️⃣ S3 Event Notification

* Triggered on **ObjectCreated events**
* Filters only `.txt` files
* Automatically invokes the Lambda function

✔️ Enables **automation without manual intervention**

---

### 3️⃣ AWS Lambda – Processing Layer

**Function Name:** `text2talk`
**Runtime:** Python 3.11

Responsibilities:

* Reads the uploaded text file from the source S3 bucket
* Extracts text content using `boto3`
* Sends text data to **Amazon Polly**
* Receives synthesized speech (MP3 format)
* Uploads the generated audio file to the target S3 bucket

✔️ Fully serverless
✔️ No infrastructure management required

---

### 4️⃣ Amazon Polly – Text-to-Speech Engine

* Converts plain text into natural-sounding speech
* Uses predefined voice IDs (e.g., *Salli*)
* Returns audio stream in MP3 format

✔️ Managed AI service
✔️ Scalable and cost-efficient

---

### 5️⃣ Amazon S3 – Target Bucket

**Bucket Name:** `text2talk-target-audio-bucket`

* Stores the generated MP3 audio files
* Acts as the final output storage
* Audio files can be accessed or downloaded as required

---

### 6️⃣ IAM Role & Security

* Lambda execution role with permissions:

  * `AmazonS3FullAccess`
  * `AmazonPollyReadOnlyAccess`
* Ensures secure interaction between AWS services following **least privilege principle**

---

## 🔹 Architecture Characteristics

* **Event-Driven**
* **Fully Serverless**
* **Highly Scalable**
* **Low Operational Overhead**
* **Cost-Optimized (pay-per-use)**


## 🔹 Architecture Summary (One-liner)

> Designed an event-driven serverless architecture where text files uploaded to Amazon S3 automatically trigger an AWS Lambda function that uses Amazon Polly to generate MP3 audio files and stores them in a target S3 bucket.
>
> <img width="908" height="482" alt="image" src="https://github.com/user-attachments/assets/118ffc70-dd7d-408c-957e-332dce064b3e" />



