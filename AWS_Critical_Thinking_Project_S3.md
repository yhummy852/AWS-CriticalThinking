
# AWS Critical Thinking

## AWS Critical Thinking Projects and Questions

### Cloud Storage Solutions and S3

#### **Introduction to Cloud Storage**

**1. What are the different types of cloud storage services (block, file, and object storage)? Which type of storage is Amazon S3?**  
- **Block Storage:** Data is stored in fixed-size blocks. It’s suitable for databases or virtual machine disks (e.g., Amazon EBS).  
- **File Storage:** Data is stored in a hierarchical structure with folders and files (e.g., Amazon EFS).  
- **Object Storage:** Data is stored as objects with metadata and a unique ID. Ideal for unstructured data like images, videos, and backups.  
- **Amazon S3** is an **Object Storage** service.

**2. What are the key features of Amazon S3 (durability, availability, scalability, and security)?**  
- **Durability:** 99.999999999% (11 nines) durability.  
- **Availability:** Multiple availability zones to ensure high uptime.  
- **Scalability:** Automatically handles growth in data volume and request traffic.  
- **Security:** Supports encryption (SSE-S3, SSE-KMS) and fine-grained access controls via IAM and bucket policies.

**3. How does Amazon S3 differ from other cloud storage services like Google Cloud Storage and Microsoft Azure Blob?**  
- S3 offers deeper AWS service integrations (Lambda, CloudFront, etc.).  
- Broader storage classes and lifecycle policies.  
- Consistent global performance and simpler pricing structure.  

**4. What are the benefits of using Amazon S3 (cost-effectiveness, ease of use, and flexibility)?**  
- Pay-as-you-go model reduces upfront costs.  
- Easy to manage through AWS Console, CLI, or SDKs.  
- Suitable for data backups, hosting static websites, and analytics.

**5. How does Amazon S3 integrate with other AWS services (S3 bucket policies, IAM roles, EC2, CloudFront, and Lambda)?**  
- **IAM Roles:** Control access for EC2, Lambda, and other services.  
- **CloudFront:** Delivers S3 content globally with low latency.  
- **Lambda:** Triggers functions on object events (e.g., uploads).  
- **S3 Bucket Policies:** Define who can access the bucket and what actions they can perform.

**6. What are the best practices for using Amazon S3 (data encryption, access control, and data lifecycle management)?**  
- Encrypt data at rest and in transit.  
- Use IAM roles and least privilege principles.  
- Enable versioning and lifecycle rules for archiving and deletion.  
- Monitor access with AWS CloudTrail.

---

### **Storage Solution for Large E-Commerce Website Assets**

For an e-commerce website storing large images, videos, and product assets:  
- **Recommended Solution:** Use **Amazon S3** as the main storage.  
- **Enhancements:**  
  - Use **Amazon CloudFront** as a CDN for caching.  
  - Store static assets (images, videos) in S3 buckets with versioning.  
  - Configure **S3 Intelligent-Tiering** for cost optimization.  
  - Integrate with **Lambda@Edge** for dynamic content optimization.

**Benefits:**  
- Scalable and highly available.  
- Reduced load on servers.  
- Cost-efficient due to automatic tiering and caching.

---

### **Security Strategy for Object Storage**

To store 30 internal videos securely in Amazon S3:  
- **Encryption:** Enable **SSE-KMS** for encryption at rest and HTTPS for in-transit encryption.  
- **Access Control:**  
  - Use IAM policies for limited user access.  
  - Block public access at bucket level.  
  - Enable MFA Delete for versioning.  
- **Monitoring:**  
  - Enable **AWS CloudTrail** and **S3 Access Logs**.  
  - Set up **AWS Config Rules** for compliance checks.  
- **Additional:** Implement lifecycle rules to move inactive videos to Glacier Deep Archive.

---

### **Disaster Recovery Planning**

A disaster recovery (DR) plan ensures business continuity during outages:  

**1. Backup Strategy:**  
- Enable **S3 Cross-Region Replication (CRR)** to store copies of data in another AWS Region.  
- Schedule automated backups using **AWS Backup** or Lambda scripts.

**2. Redundancy:**  
- Deploy web servers across multiple Availability Zones (Multi-AZ).  
- Use **Elastic Load Balancers** to distribute traffic.

**3. Failover:**  
- Configure **Route 53 DNS failover** between primary and backup sites.  

**4. Recovery Procedures:**  
- Test backup restoration regularly.  
- Use **CloudFormation** templates for infrastructure redeployment.

---

### **Documentation**

- Document all configurations, IAM roles, and bucket policies.  
- Include screenshots of S3 setup, IAM permissions, and CloudFront distributions.  
- Upload this markdown file to a GitHub repository and submit the repository link for review.
