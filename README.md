# Assignment  week 11

AUTHOR BY:
 ABDULLAH HASSAN
SDA1017
## :pushpin: Overview
Deploy a MERN stack blog application on AWS using Terraform and Ansible. The backend runs on an EC2 instance, the frontend is hosted via S3, and MongoDB Atlas serves as the database.
## :building_construction: Architecture
- **Backend**: EC2 instance (Ubuntu 22.04, t3.micro)
- **Frontend**: S3 static website hosting
- **Database**: MongoDB Atlas
- **Media Uploads**: Dedicated S3 bucket
## :wrench: Tasks Summary
### 1. Security Configuration
- IAM policy for S3 media uploads.
- Security group allowing SSH (22), HTTP (80), and app port (5000).
### 2. MongoDB Atlas Setup
- Create a free-tier cluster.
- Whitelist EC2 IP and configure connection string in `.env`.
### 3. S3 Buckets
- **Frontend Bucket**: Static website hosting with public read access.
- **Media Bucket**: Programmatic access with CORS policy.
### 4. Backend Deployment
- **Terraform**: Launch template for EC2 (Ubuntu 22.04, t3.micro).
- **Ansible**: Playbook to:
  - Clone the repo.
  - Configure `.env` (MongoDB, S3 credentials).
  - Start backend with PM2.
### 5. Frontend Deployment
- Build and deploy to S3 using AWS CLI.
## :white_check_mark: Success Criteria
- Functional MERN app accessible via S3 frontend.
- MongoDB connected, media uploads working.
- Screenshots provided: PM2, MongoDB cluster, S3 frontend, media upload.
## :broom: Cleanup
- Run `terraform destroy`.
- Remove `.env` files and revoke IAM credentials.
- Delete MongoDB Atlas rules.
## :hammer_and_wrench: Helpers
- **User Data Script**: Installs Node.js, PM2, AWS CLI.
- **Ansible Snippets**: Backend and frontend deployment scripts.
