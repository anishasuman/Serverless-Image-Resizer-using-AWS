# 📦 Serverless Image Resizer using AWS  
### _Managing Cloud Solutions_  

<p align="center">
  <img src="https://raw.githubusercontent.com/aniketmaurya/christmas-lights/master/assets/santa.gif" width="260">
</p>

---

# 🚀 Project Overview  
This project implements a **Serverless Image Resizer Architecture** using AWS services.

Whenever a user uploads an image to an S3 bucket, a Lambda function automatically resizes it and stores the optimized version in another S3 bucket — without managing any servers.

The solution is:  
✔ Serverless  
✔ Scalable  
✔ Cost-efficient  
✔ Secure  
✔ Event-driven  

---

# 🎯 Objectives  
- Automatically resize images on upload  
- Use AWS Lambda for serverless execution  
- Store optimized images efficiently  
- Ensure secure access with IAM  
- Monitor activity using CloudWatch  
- Enable fast global delivery using CloudFront (optional)  

---

# 🧊 AWS Services Used  
These icons ALWAYS load, GitHub-safe:

![S3](https://img.shields.io/badge/Amazon%20S3-569A31?style=for-the-badge&logo=amazon-s3&logoColor=white)
![Lambda](https://img.shields.io/badge/AWS%20Lambda-FF9900?style=for-the-badge&logo=awslambda&logoColor=white)
![IAM](https://img.shields.io/badge/AWS%20IAM-DD344C?style=for-the-badge&logo=amazonaws&logoColor=white)
![CloudWatch](https://img.shields.io/badge/Amazon%20CloudWatch-FF4F8B?style=for-the-badge&logo=amazoncloudwatch&logoColor=white)
![CloudFront](https://img.shields.io/badge/Amazon%20CloudFront-8C4FFF?style=for-the-badge&logo=amazonaws&logoColor=white)

---

# 🧩 Scenario  
A website receives large high-resolution images.  
The site needs smaller versions (thumbnail, medium, large) for fast performance.

This architecture **automatically resizes images** and stores them in an optimized format.

---

# 🏗 Architecture Animation (GitHub-Safe)
<p align="center">
  <img src="https://raw.githubusercontent.com/Azure-Samples/media/master/media/architecture-diagrams/serverless.gif" width="550">
</p>

---

# 🧠 Architecture Flow


✨ **User Uploads Image**  
  ⬇️  
🪣 **S3 (Original Bucket)**  
  ⬇️ 🚨 *Event Trigger*  
⚡ **Lambda Function**  
🎨 *Resizes / Optimizes Image*  
  ⬇️  
🪣 **S3 (Resized Bucket)**  
  ⬇️  
🚀 **CloudFront CDN (Optional)**  
🌍 *Delivers images globally at high speed*


---

# 🛠 Full Implementation Steps  

## 1️⃣ Create S3 Buckets  
- **original-images-bucket** → upload folder  
- **resized-images-bucket** → output folder  
- Upload sample JPG/PNG

---

## 2️⃣ Create IAM Execution Role  
Attach Policies:  
- AmazonS3FullAccess  
- AWSLambdaBasicExecutionRole  

Add inline policy for S3 trigger permissions.

---

## 3️⃣ Create AWS Lambda Function  
- Runtime: Python / Node.js  
- Install Sharp / Pillow for image resizing  
- Write code to:  
  ➝ Read from S3  
  ➝ Resize  
  ➝ Write resized image to another bucket  
- Assign IAM role  
- Increase memory & timeout  

---

## 4️⃣ Connect S3 to Lambda  
In Lambda → Add Trigger → S3  
- Bucket: original-images-bucket  
- Event: PUT  
- Destination: resized-images-bucket  

Lambda now runs automatically on image upload.

---

## 5️⃣ Test Full Flow  
- Upload an image  
- Lambda resizes automatically  
- Check resized bucket  
- Works for JPG/PNG  

---

## 6️⃣ CloudWatch Monitoring  
- Open CloudWatch Logs  
- View Lambda execution logs  
- Track errors & performance  

---

## 7️⃣ Optional: CloudFront Setup  
- Create CloudFront distribution  
- Use resized bucket as origin  
- Enables **fast global delivery** of images  

---

# 📸 Screenshots  
All screenshots are available in this repo:

