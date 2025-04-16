# Project 2: Launch a Node.js Application on AWS Elastic Beanstalk

![](./images/Screenshot%202025-04-15%20144135.png)

## Overview

This project demonstrates how to deploy a simple Node.js application using **AWS Elastic Beanstalk** through the AWS Console.

---

## 🚀 Steps to Deploy

### 1. Create a New Elastic Beanstalk Application
- Go to the [Elastic Beanstalk Console](https://console.aws.amazon.com/elasticbeanstalk).
- Click **“Create Application”**.
- Environment type: **Web server environment**
- Name your app (e.g., ` Sample-node-app`).
![](./images/Screenshot%202025-04-15%20144225.png)
- It will automatically give an environment name and create a domain name too.
- Select **Node.js** as the platform and choose the latest available version.
![](./images/Screenshot%202025-04-15%20144241.png)
- Under "Application code", select **Sample Application** and Presets as **Single-Application**.

---

### 2. Configure service access 
*Instance Profile (IAM Role) — Important!*
If this is your **first time using Elastic Beanstalk**, AWS will usually **auto-create** the required roles.

> ⚠️ However, if you've used Beanstalk before, or if AWS doesn't auto-create the role, you'll need to create it manually.

#### To create the EC2 instance profile manually:
1. Go to **IAM > Roles** and click **Create role**.
2. Select **Trusted entity: EC2**.
3. Attach the following policy: `AWSElasticBeanstalkWebTier`
4. Name the role: `aws-elasticbeanstalk-ec2-role`
5. Refresh the instance profile dropdown and select this role.
6. Choose your already present key-pair.
 
![](./images/Screenshot%202025-04-15%20144929.png)

---
### 4. Set up networking, database and tags
- Select default VPC.
- In instance settings select two or more subnets.
- Keep other settings as they are and skip to review page.

![](./images/Screenshot%202025-04-15%20145202.png) 

### 5. Launch the Environment
- Click submit on review page and wait for resources to be provisioned.
- This may take a few minutes.

---

### ✅ Done!
Once the environment is green and healthy, open the provided Beanstalk URL to view your Node.js app running live.

![](./images/Screenshot%202025-04-15%20145629.png) 

---

## 📝 Notes
- This project uses the default AWS sample Node.js app.
- You can later deploy your own code using the **EB CLI** or AWS Console.
- Beanstalk handles provisioning, monitoring, and scaling for you.

