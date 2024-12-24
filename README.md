![Alt text](/

# Dynamic Website Deployment on AWS - DevOps Project

This repository contains the resources, scripts, and architecture for deploying a dynamic website on AWS. The setup ensures scalability, security, and high availability, following cloud best practices.

---

## **Architecture Overview**

The project is built on AWS services and utilizes a custom VPC design with a multi-tier architecture. The reference architecture diagram included in this repository provides a detailed visualization of the deployment.

---

## **Problem Statement**

The objective of this project was to host a dynamic website using a cloud-based solution that:  
- Ensures high availability and fault tolerance.  
- Provides secure access to resources.  
- Scales dynamically based on traffic.  
- Sends notifications for critical events.  

Achieving these goals required leveraging AWS services effectively while addressing challenges related to configuration, security, and automation.

---

## **Challenges Faced and Solutions**

### **1. Ensuring High Availability Across Regions**  
**Problem:** Achieving high availability required configuring resources to span multiple Availability Zones.  
**Solution:** Deployed resources in two Availability Zones and used an Application Load Balancer (ALB) to distribute traffic across instances in different zones. This setup minimizes downtime and ensures fault tolerance.

---

### **2. Securely Connecting to Resources in Private Subnets**  
**Problem:** Direct access to EC2 instances in private subnets posed a security risk.  
**Solution:** Implemented EC2 Instance Connect Endpoint to enable secure connections without exposing resources to the internet. Configured Security Groups to restrict access further.

---

### **3. Automating EC2 Instance Scaling**  
**Problem:** Manual scaling of EC2 instances for varying traffic loads was inefficient.  
**Solution:** Set up an Auto Scaling Group (ASG) to dynamically add or remove instances based on load metrics. This ensured the system adapted to traffic surges or declines automatically.

---

### **4. Securing Application Communications**  
**Problem:** Ensuring secure communication between users and the application required SSL/TLS certificates.  
**Solution:** Used AWS Certificate Manager (ACM) to provision and manage certificates, securing the website with HTTPS.

---

### **5. Configuring Notifications for Key Events**  
**Problem:** Lack of visibility into Auto Scaling activities hindered real-time monitoring.  
**Solution:** Configured Simple Notification Service (SNS) to send alerts about critical activities in the ASG, such as instance launches or terminations.

---

### **6. Simplifying Domain Management**  
**Problem:** Registering and managing a domain externally was cumbersome.  
**Solution:** Registered the domain directly via Route 53 and configured DNS records to route traffic efficiently.

---

### **7. Storing and Deploying Application Code**  
**Problem:** Managing application code across instances was error-prone.  
**Solution:** Utilized S3 to store application code and configured EC2 instances to fetch the latest version during deployment.

---

## **AWS Resources Used**

### **Networking and Security**
- **Virtual Private Cloud (VPC):** Custom VPC with public and private subnets in two Availability Zones.  
- **Internet Gateway:** Enabled internet connectivity for public subnet resources.  
- **NAT Gateway:** Allowed instances in private subnets to access the internet securely.  
- **Security Groups:** Configured as firewalls to control inbound and outbound traffic.  

### **Compute and Scaling**
- **EC2 Instances:** Hosted the dynamic website.  
- **Auto Scaling Group:** Managed the dynamic addition/removal of instances.  
- **Application Load Balancer (ALB):** Distributed traffic across EC2 instances.  

### **Storage and Code Management**
- **S3:** Stored application code and deployment artifacts.

### **Monitoring and Notifications**
- **Simple Notification Service (SNS):** Sent alerts for ASG activities.  

### **Domain and SSL**
- **Route 53:** Managed domain registration and DNS records.  
- **Certificate Manager (ACM):** Secured application communications with SSL/TLS certificates.

---

## **Deployment Steps**

### **Prerequisites**
- AWS account.
- Basic knowledge of AWS services and cloud architecture.
- Clone this repository for deployment scripts and reference diagrams.

### **Steps to Deploy**
1. Clone the repository and review the reference architecture diagram.  
2. Deploy infrastructure using the provided scripts.  
3. Upload the application code to the S3 bucket and configure EC2 instances to retrieve and serve the application.  
4. Test the deployment by accessing the domain name registered in Route 53.

---

## **Repository Contents**

- **`/diagrams/`**: Reference architecture diagram.  
- **`/scripts/`**: Deployment and configuration scripts.  
- **`README.md`**: Project documentation.  

---

## **Conclusion**

This project demonstrates how AWS services can be utilized to build a secure, scalable, and highly available infrastructure for hosting dynamic websites. The challenges faced during the deployment were resolved with best practices, ensuring a robust solution.

---

Feel free to raise issues, contribute, or suggest improvements to the repository.

--- 
