# **AWS Costing Documentation for Platform & Lakehouse Accounts**

**Version**: 1.0

---

## **Executive Summary**

This documentation provides a comprehensive breakdown of the estimated monthly AWS costs for the **Platform Account** and **Lakehouse Account**. As part of our cloud infrastructure management, understanding and optimizing cloud costs are crucial for maintaining a sustainable and efficient cloud environment. The following report highlights the key services in use, associated costs, and offers insights for cost optimization.

---

## **1. Overview of Services and Costs**

### **Platform Account Services Overview**

1. **EC2 Instances (EKS)**
   Amazon EC2 instances are provisioned for the Elastic Kubernetes Service (EKS), with various instance types and capacities optimized for our workloads.

   * **m5.Xlarge**: 2 instances
   * **t3.medium**: 5 instances

2. **RDS (Relational Database Service)**
   Used for managed database operations, primarily for running PostgreSQL or MySQL databases.

   * **db.t3.medium**: 1 instance
   * **db.m5.Xlarge**: 1 instance

3. **DocumentDB**
   Managed NoSQL database service for handling JSON data at scale.

   * **db.t3.medium**: 2 instances

4. **Ingress Load Balancer (ALB/NLB)**
   Handling traffic routing for EKS services, ensuring high availability and scalability.

5. **IAM Roles and IPs**
   Managed IAM roles and IPs are integral for security and network configuration, though the direct costs are minimal.

---

### **Lakehouse Account Services Overview**

1. **EC2 Instances**
   Used for various processing and compute tasks within the Lakehouse environment.

   * **m5.Xlarge**: 1 instance
   * **t3.medium**: 1 instance

2. **RDS (Relational Database Service)**
   Used for managed database operations in the Lakehouse environment.

   * **db.r5.medium**: 2 instances
   * **db.m5.Xlarge**: 1 instance

3. **S3 Storage**
   Storage for data assets in the Lakehouse environment.

4. **Ingress Load Balancer (ALB/NLB)**
   For handling traffic for applications running on EKS.

5. **IAM Roles and IPs**
   Like the Platform Account, these are integral for the operational environment, though direct costs are minimal.

---

## **2. Detailed Monthly Cost Breakdown**

### **Platform Account**

1. **EC2 Instances**
   The EC2 instances used for EKS workloads are as follows:

   * **m5.Xlarge**:

     * Monthly Cost: $140.16
     * Quantity: 2
     * **Total**: $280.32

   * **t3.medium**:

     * Monthly Cost: $30.36
     * Quantity: 5
     * **Total**: $151.80

   **Total EC2 Cost**: **$432.12**

2. **RDS Instances**
   For managed relational databases, we use:

   * **db.t3.medium**:

     * Monthly Cost: $52.56
     * Quantity: 1
     * **Total**: $52.56

   * **db.m5.Xlarge**:

     * Monthly Cost: $259.88
     * Quantity: 1
     * **Total**: $259.88

   **Total RDS Cost**: **$312.44**

3. **DocumentDB Instances**

   * **db.t3.medium**:

     * Monthly Cost: $52.56
     * Quantity: 2
     * **Total**: $105.12

   **Total DocumentDB Cost**: **$105.12**

4. **Ingress Load Balancer (ALB/NLB)**

   * Monthly Cost per Load Balancer: $17.00 (including data processing)
     **Total Load Balancer Cost**: **$17.00**

5. **IAM Roles and IPs**
   Estimated for operational costs such as security configurations and network management:
   **Total IAM & IP Costs**: **$10.00**

---

### **Lakehouse Account**

1. **EC2 Instances**
   The EC2 instances used are:

   * **m5.Xlarge**:

     * Monthly Cost: $140.16
     * Quantity: 1
     * **Total**: $140.16

   * **t3.medium**:

     * Monthly Cost: $30.36
     * Quantity: 1
     * **Total**: $30.36

   **Total EC2 Cost**: **$170.52**

2. **RDS Instances**
   For managed relational databases, we use:

   * **db.r5.medium**:

     * Monthly Cost: $365.00
     * Quantity: 2
     * **Total**: $730.00

   * **db.m5.Xlarge**:

     * Monthly Cost: $259.88
     * Quantity: 1
     * **Total**: $259.88

   **Total RDS Cost**: **$989.88**

3. **S3 Storage**
   Estimated monthly cost for 50GB of storage:

   * Monthly Storage Cost: $1.15

   **Total S3 Storage Cost**: **$1.15**

4. **Ingress Load Balancer (ALB/NLB)**

   * Monthly Cost per Load Balancer: $17.00 (including data processing)
     **Total Load Balancer Cost**: **$17.00**

5. **IAM Roles and IPs**
   Similar to the Platform Account, the estimated operational costs:
   **Total IAM & IP Costs**: **$10.00**

---

## **3. Total Monthly Estimated Costs**

### **Platform Account:**

* **EC2 Instances**: $432.12
* **RDS**: $312.44
* **DocumentDB**: $105.12
* **Ingress Load Balancer**: $17.00
* **IAM & IPs**: $10.00
* **Total Monthly Cost for Platform Account**: **$876.68**

### **Lakehouse Account:**

* **EC2 Instances**: $170.52
* **RDS**: $989.88
* **S3 Storage**: $1.15
* **Ingress Load Balancer**: $17.00
* **IAM & IPs**: $10.00
* **Total Monthly Cost for Lakehouse Account**: **$1,188.55**

---

## **4. Recommendations for Cost Optimization**

While the estimated costs above provide an accurate breakdown of the current setup, there are several steps we can take to optimize costs:

1. **Rightsize EC2 Instances**:
   Assess whether the current instance sizes (e.g., m5.Xlarge and t3.medium) are optimal for the workloads running on EKS. Consider using **Auto Scaling** to adjust instance sizes based on demand.

2. **Use Reserved Instances (RDS & EC2)**:
   If the workloads are predictable, consider using **Reserved Instances** for both EC2 and RDS services. This can reduce the cost significantly (up to 75%) compared to On-Demand pricing.

3. **Optimize Load Balancer Costs**:
   Review the **traffic patterns** on the Ingress Load Balancer. If the load balancer is used for low traffic applications, switching to **Network Load Balancer** may reduce costs, as they are generally cheaper for high-throughput traffic.

4. **Implement S3 Lifecycle Policies**:
   Consider implementing **S3 lifecycle policies** to archive older data or delete data that is no longer needed. This will help lower storage costs, especially for infrequently accessed data.

5. **Monitoring and Alerts**:
   Utilize **AWS Budgets** and **Cost Explorer** to set up alerts for any unexpected spikes in costs. Ensure that all usage is aligned with expectations.

---

## **5. Conclusion**

This documentation outlines the estimated AWS costs for the **Platform Account** and **Lakehouse Account**, providing transparency into the cloud infrastructure's pricing. By understanding these costs and regularly reviewing resource usage, we can optimize the infrastructure for both cost efficiency and operational effectiveness.

---

