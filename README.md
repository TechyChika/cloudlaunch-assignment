# CloudLaunch Assignment

##  Project Overview
This project demonstrates:
1. **Task 1: Static Website Hosting (S3 + IAM)**
   - Hosted a static website on Amazon S3.
   - Configured public access for the site bucket.
   - Created IAM user with restricted access policies.
  

2. **Task 2: VPC Design**
   - Designed and configured a VPC with public, app, and DB subnets.
   - Configured route tables and an internet gateway.
   - Applied security groups for controlled communication.
   - Attached VPC Read-Only IAM policy.

---

##  Static Website
- **S3 Website URL:** http://cloudlaunch-site-bucket-chika.s3-website-eu-west-1.amazonaws.com/

---

**Files**

The sites created for this project are located in the [`site/`](./site) folder.


## 👤 IAM User
- **Username:** `cloudlaunch-user`  
- **Account Alias/ID:** *396371354530*  
- **Console URL:** *https://396371354530.signin.aws.amazon.com/console*  
**Credentials:** Submitted separately (with enforced password reset).  

---

##  IAM Policies
The IAM policies created for this assignment are located in the [`policies/`](./policies) folder.

- [s3-policy-cloudlaunch-user-chika.json](./policies/s3-policy-cloudlaunch-user-chika.json)  
- [vpc-readonly-policy-chika.json](./policies/vpc-readonly-policy-chika.json)  

---

##  VPC Layout
- **VPC Name:** `cloudlaunch-vpc` (CIDR: `10.0.0.0/16`)  
- **Subnets:**  
  - Public Subnet → `10.0.1.0/24`  
  - App Subnet → `10.0.2.0/24`  
  - DB Subnet → `10.0.3.0/28`  
- **Internet Gateway:** `cloudlaunch-igw`  
- **Route Tables:**  
  - Public Route Table → `cloudlaunch-public-rt` (0.0.0.0/0 → IGW)  
  - Private Route Tables → `cloudlaunch-app-rt`, `cloudlaunch-db-rt` (no internet routes)  
- **Security Groups:**  
  - `cloudlaunch-app-sg` → Allow HTTP (80) from `10.0.0.0/16`  
  - `cloudlaunch-db-sg` → Allow MySQL (3306) from App Subnet only  

---



 


