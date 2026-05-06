# Lab: Design and Evaluate an AWS Solution Using the Well-Architected and Cloud Adoption Frameworks

---

## Learning Objectives

By the end of this lab, learners should be able to:

- Identify and apply the five pillars of the AWS Well-Architected Framework to a cloud workload
- Use the AWS Cloud Adoption Framework (CAF) to evaluate organizational readiness
- Recommend architectural improvements aligned with AWS best practices
- Communicate architectural decisions using structured reasoning and documentation

---

## Background

Your organization is migrating a **two-tier web application (frontend + backend database)** from on-premises servers to AWS.

Management requires that the migration:

- Aligns with AWS best practices
- Follows a well-architected design from the start

---

## Lab Tasks

### Task 1 – Review the Existing Architecture

- Identify workload components (e.g., frontend, backend, database)
- Note potential risks or weaknesses, such as:
  - No backup strategy
  - Single Availability Zone deployment
  - Open or overly permissive security groups

---

### Task 2 – Evaluate Using AWS Well-Architected Framework

Assess the system using the five pillars:

- Operational Excellence
- Security
- Reliability
- Performance Efficiency
- Cost Optimization

#### WAF Assessment Table

| Pillar | Observation (Strength / Weakness) | Improvement Recommendation | Supporting AWS Service |
|--------|-----------------------------------|---------------------------|------------------------|
| Operational Excellence | Manual deployment processes | Implement CI/CD pipeline for automation | AWS CodePipeline |
| Security | Open security groups | Apply least privilege access and tighten security groups | AWS IAM / Security Groups |
| Reliability | Single-AZ deployment | Deploy across multiple AZs with failover | AWS Elastic Load Balancer |
| Performance Efficiency | Static infrastructure scaling | Enable auto-scaling based on demand | AWS Auto Scaling |
| Cost Optimization | Always-on resources | Use reserved instances or auto-scaling to reduce idle cost | AWS Cost Explorer |

---

### Task 3 – Apply AWS Cloud Adoption Framework (CAF)

Evaluate readiness across six perspectives:

#### CAF Readiness Summary

**1. Business Perspective**

The organization shows strong intent for cloud adoption but lacks a clearly defined business case tied to measurable outcomes such as ROI or cost savings. To improve readiness, stakeholders should define KPIs, expected benefits, and alignment with business goals. Establishing a cloud value framework will ensure that migration efforts deliver tangible results.

**2. People Perspective**

There is limited evidence of cloud skills within the team. Upskilling through AWS training and certifications is necessary. Creating cross-functional teams and assigning cloud champions will help bridge knowledge gaps and support adoption.

**3. Governance Perspective**

Governance structures appear underdeveloped, particularly around compliance and policy enforcement. The organization should define cloud policies, tagging strategies, and compliance requirements to ensure proper oversight and accountability.

**4. Platform Perspective**

The current architecture lacks scalability and automation. Transitioning to infrastructure-as-code (IaC) using tools like AWS CloudFormation or Terraform will standardize deployments and improve consistency.

**5. Security Perspective**

Security practices are reactive rather than proactive. Implementing identity management (IAM), encryption, and monitoring tools will strengthen the organization's security posture and align with shared responsibility principles.

**6. Operations Perspective**

Operational processes such as monitoring, logging, and incident response are minimal. Adopting tools like AWS CloudWatch and AWS CloudTrail will improve visibility and enable faster issue resolution.

---

### Task 4 – Improved Architecture Design

#### Proposed Architecture (Description)

- **Frontend Layer**
  - Hosted on Amazon S3 (static website) + CloudFront CDN

- **Application Layer**
  - Deployed on EC2 instances within an Auto Scaling Group
  - Managed via Elastic Load Balancer (multi-AZ)

- **Database Layer**
  - Amazon RDS (Multi-AZ deployment with automated backups)

- **Security**
  - IAM roles with least privilege
  - Security Groups and Network ACLs
  - HTTPS via AWS Certificate Manager

- **Monitoring & Logging**
  - AWS CloudWatch (metrics and alerts)
  - AWS CloudTrail (audit logs)

- **Deployment**
  - CI/CD pipeline using AWS CodePipeline and CodeDeploy

This design ensures:

- High availability (multi-AZ)
- Scalability (auto scaling)
- Security (IAM, encryption)
- Cost efficiency (on-demand scaling)

---

## Deliverables

Learners must submit:

- Completed WAF assessment table
- CAF readiness summary
- Improved architecture diagram or description
- Reflection (150 words)

---

## Submission Criteria & Guidelines

### Format

Submit a GitHub repository containing:

- `aws_waf_caf_assessment.md` or PDF report
- Architecture diagram (draw.io, Lucidchart, or scanned image)
- README explaining your approach

### Submission Method

- Submit GitHub repository link via Microsoft Forms

---

## Evaluation Rubric

| Criterion | Description | Weight |
|-----------|-------------|--------|
| Technical Understanding | Accurate use of WAF pillars and CAF perspectives | 30% |
| Analytical Depth | Relevant improvements with strong reasoning | 25% |
| Architecture Design Quality | Alignment with AWS best practices | 25% |
| Documentation & Presentation | Clear, structured, and professional submission | 20% |

---

## Outcome

By completing this lab, learners demonstrate the ability to think like cloud architects — evaluating workloads critically, applying AWS frameworks, and communicating architectural improvements effectively.
