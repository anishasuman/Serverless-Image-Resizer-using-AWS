# 📦 Serverless Image Resizer using AWS  
### _Managing Cloud Solutions_  

## 🌈 Animated Cloud Banner  
<p align="center">
  <img src="https://media.giphy.com/media/Q7SKqn3G97xpmfSOvG/giphy.gif" width="700px">
</p>

---

# 🎨 3D Banner — Made for *Anisha Kumari*  
<p align="center">
  <img src="https://i.imgur.com/sHhhpbn.png" width="820px" />
</p>

---

# 🧊 3D AWS Icons — Tech Stack Used  

<p align="center">
  <img src="https://d1.awsstatic.com/product-marketing/ALL%20SERVICES%20Icons/S3%20icon.9e1d9f32a7f6c5d45d6c2f2efa3c7bd3a4d5907d.png" width="120" title="Amazon S3" />
  &nbsp;&nbsp;&nbsp;
  <img src="https://d1.awsstatic.com/product-marketing/Lambda/Serverless_AWSLambda_icon_64.4f3f9d33083894026fb5d3a7ed7b888d4e921d39.png" width="120" title="AWS Lambda" />
  &nbsp;&nbsp;&nbsp;
  <img src="https://d1.awsstatic.com/product-marketing/IAM/Identity-Access-Management_IAM.7c1976a531c7d1ca8e35bdfb24d3dc0fa9e1a247.png" width="120" title="IAM" />
  &nbsp;&nbsp;&nbsp;
  <img src="https://d1.awsstatic.com/product-marketing/CloudWatch/Cloudwatch_64.9b2a444ef98a32956543d4d6acdfb5a12ddf967e.png" width="120" title="Amazon CloudWatch" />
  &nbsp;&nbsp;&nbsp;
  <img src="https://d1.awsstatic.com/Product-Page-New/CloudFront/CloudFront-product-icon_64.b515cb62cae5d7b54073e5bb5a7ab38757dedc28.png" width="120" title="Amazon CloudFront" />
</p>

---

# 🚀 Project Overview  
This project implements a **Serverless Image Resizer Architecture** using AWS services.  
When a user uploads an image to **Amazon S3**, a **Lambda function automatically resizes it** and stores the optimized version into another bucket — no servers required.

The architecture is **event-driven, cost-efficient, scalable, and secure**.

---

# 🎯 Project Objectives  
- Automatically resize images on upload  
- Use AWS Lambda for serverless automation  
- Deliver optimized images for fast loading  
- Maintain security using IAM Roles  
- Ensure scalability without managing servers  
- Enable monitoring with CloudWatch  
- (Optional) Use CloudFront for low-latency delivery  

---

# 🧩 Scenario  
A website receives high-resolution images, but needs multiple optimized versions (thumbnail, medium, large).  
This architecture resizes images **automatically**, saving time and reducing manual effort.

---

# 🏗 Architecture Diagram (Animated)  
<p align="center">
  <img src="https://media.giphy.com/media/l0HlSNOxJB956qwfK/giphy.gif" width="700px">
</p>

---

# 🧠 Architecture Flow  
User Uploads Image → original-images-bucket (S3)
↓ (Event Trigger)
AWS Lambda Function
↓ (Processing)
Resizes and Stores → resized-images-bucket (S3)
↓
(Optional) CloudFront for fast delivery


---

# 🛠 Full Implementation Steps  

## 1️⃣ Create S3 Buckets  
- `original-images-bucket` → uploads  
- `resized-images-bucket` → output  
- Test by uploading a JPG/PNG image

---

## 2️⃣ Create IAM Role  
Attach:  
- AmazonS3FullAccess  
- AWSLambdaBasicExecutionRole  
- Add inline policy for S3 triggers

---

## 3️⃣ Create Lambda Function  
- Runtime: Python / Node.js  
- Install Sharp/Pillow to resize images  
- Add code to:  
  - Read image from S3  
  - Resize  
  - Save resized image to output bucket  
- Assign IAM role  

---

## 4️⃣ Connect S3 to Lambda  
In **Lambda → Triggers**  
- Add S3  
- Bucket: original-images-bucket  
- Event: PUT (file upload)  

✔ Lambda now auto-executes on uploads.

---

## 5️⃣ Test the Workflow  
- Upload sample image  
- Lambda runs automatically  
- Resized image appears in second bucket  
- Works for JPG, PNG, etc.

---

## 6️⃣ CloudWatch Monitoring  
- Check Lambda logs  
- Errors, performance, metrics  
- Set alarms (optional)

---

## 7️⃣ (Optional) CloudFront Integration  
- Create CloudFront distribution  
- Set resized-images-bucket as origin  
- Provides high-speed global delivery  

---

# 📸 Screenshots  
All screenshots are stored inside this repo.

