# Production Grade MySQL Architecture on AWS

## Overview
This project demonstrates a production grade cloud architecture where a web application connects to a MySQL database hosted on AWS RDS.  
The setup focuses on high availability, fault tolerance, and real world DevOps practices using Multi AZ deployment, failover handling, and caching recommendations.

The goal is to show how databases actually work behind real applications in production environments.

---

## Architecture Components

### 1. Web Application Layer
- Ubuntu EC2 instance acting as the application server  
- Python based application retrieves data from MySQL  
- Communicates with the database using the RDS endpoint  

### 2. Database Layer
- AWS RDS MySQL with Multi AZ enabled  
- Primary and secondary database instances across different availability zones  
- Automatic failover handled by AWS through the RDS endpoint  
- Ensures high availability and minimal downtime  

### 3. Administration Layer
- Windows EC2 instance used for MySQL Workbench  
- Used for database administration, schema creation, and data insertion  
- Securely connects to RDS using endpoint and credentials  

### 4. Networking
- VPC with multiple availability zones  
- Public subnets for application and admin access  
- Security groups controlling access between EC2 and RDS  

### 5. Caching Recommendation
- In memory caching suggested to handle temporary backend issues  
- Helps reduce downtime during database failover events  
- Improves application performance and user experience  

---

## Key Concepts Demonstrated
- Structured databases using MySQL  
- Multi AZ architecture for high availability  
- RDS endpoints for seamless traffic routing  
- Real time data retrieval from application to database  
- Failover and failback behavior in production  
- DevOps responsibility in communicating backend issues to application teams  

---

## Failover Scenario
- Primary database is intentionally rebooted  
- Traffic is automatically redirected to the secondary database  
- Application continues to retrieve data with minimal interruption  
- Endpoint IP changes but application configuration remains unchanged  

---

## Why This Architecture
- Mimics real production environments  
- Reduces single points of failure  
- Scales easily with application growth  
- Aligns with enterprise DevOps and cloud best practices  

---

## Tools and Technologies
- AWS EC2 (Windows and Ubuntu)
- AWS RDS MySQL
- Python
- MySQL Workbench
- AWS VPC
- Security Groups

---

## Future Enhancements
- Add in memory caching using Redis or ElastiCache  
- Integrate Secrets Manager for credential security  
- Add monitoring and alerts using CloudWatch  
- Extend architecture with API Gateway and Lambda  

---

## Conclusion
This project is designed to bridge the gap between theory and real world cloud implementations.  
It provides hands on experience with production grade database architecture, failover handling, and DevOps driven decision making.

