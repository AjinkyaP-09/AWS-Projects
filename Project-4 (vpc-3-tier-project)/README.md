# 🏗️ VPC 3-Tier Web Application on AWS

## Overview

This project showcases a basic 3-tier architecture deployed on AWS using EC2, RDS, and S3. It includes:

- A **Web Tier** with Nginx on EC2 serving a static HTML form.
- An **App Tier** with a Flask app on EC2 handling form submissions, uploading images to S3, and storing metadata in RDS.
- A **Data Layer** using Amazon S3 (for images) and RDS MySQL (for user metadata).

The setup is fully hosted within a custom VPC using only **public subnets** for simplicity—no load balancers or NAT gateways.

---

## Technologies Used

- Amazon VPC, EC2, S3, RDS (MySQL), IAM
- Nginx, Python (Flask), MySQL, HTML

---

## Features

- Image upload via a web form
- Backend processing and data storage
- End-to-end communication via Nginx proxy
- Minimal, cost-effective architecture using free-tier eligible services

---

## Deployment Instructions

> For full step-by-step setup, configuration commands, and troubleshooting tips, **please refer to the [VPC-3-tier-project.docx](./VPC-3-tier-project.docx)** included in this repository.

---

## Output

![](Screenshot%202025-04-18%20112942.png)
### Submit to view image and submission message.
![](Screenshot%202025-04-18%20113021.png)

## Author

[Ajinkya Pame](https://www.linkedin.com/in/ajinkya-pame-4a752b346)
