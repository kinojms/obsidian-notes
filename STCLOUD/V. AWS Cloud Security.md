# AWS Shared Responsibility Model
- Shared across all cloud services
- Ex: If you were to go to an Ice Skating Rink, you can rent skates and if something happens, it can be either your fault or the provider's fault

![[Pasted image 20250707130341.png]]

## AWS Responsibility: Security of the cloud
- physical security of data centers
	- controlled, need-based access
- hardware and software infrastructure
	- storage decommissioning, host operating system (OS) access logging, and auditing
	- if the server's OS breaks down, that's not your responsibility
- network infrastructure
	- intrusion detection
- virtualization infrastructure
	- instance isolation

*Data Carving - recovering "deleted" data*

## Customer Responsibility: Security in the cloud
- Amazon Elastic Compute Cloud (Amazon EC2) isntance OS
	- including patching, maintenance
- applications
	- passwords, role-based access, etc.
- security group configurations
- OS or host-based firewalls
	- including intrusion detection or prevention systems
- network configurations
- // recheck ppt

### Service Characteristics and Security Responsibility
Infrastructure as a service (IaaS)
- more flexibility over configuring networking and storage settings
- customer is responsible for managing more aspects of the security
- customer configures the access controls
Platform as a service (PaaS)
- customer does not need to manage the underlying infrastructure
- AWS handles the OS, database patching, firewall configuration, and disaster recovery
- customer can focus on managing code or data
Software as a Service (SaaS)
- software is centrally hosted
- licensed on a subscription model or pay-as-you-go basis
- services are typically accessed via web browser, mobile app, or application programming interface (API)
- customers do not need to manage the infrastructure that supports the service
- the one who sets up the service is the one in control (thus is responsible for any issues)

Sample Services Managed by Customer:
Amazon EC2, Amazon Elastic Block Store, Amazon Virtual Private Cloud

Sample Services Managed by AWS:
AWS Lambda, Amazon Relational Database Service, AWS Elastic Beanstalk (automates deployment of resources)

SaaS Examples:
AWS Trusted Advisor, AWS Shield, Amazon Chime

# AWS Identity and Access Management (IAM)
- a directory service - allows to control users, group, roles, policies
	- group - entity where users are mapped to
	- roles - **temporary**
- use IAM to manage access to AWS resources
	- a resources is an entity in an AWS account that you can work with
	- ex resources: an Amazon EC2 instance or an Amazon S3 bucket
- you can control who can terminate Amazon EC2 instances for example
- define fine-grained access rights

## IAM: Essential Components
1. IAM User - a person or application (calls an API) that can authenticate with an AWS account
2. IAM Group - a collection of IAM users that are granted identical authorization
3. IAM Policy - the document that defines which resources can be accessed and the level of access to each resources
4. IAM Role - to grant a set of permissions for making AWS service requests (temporary)

## Authorization: What can you do?
- a user, group, or role are given policies (what they can do), then they are given access to selected resources (EC2 instances, S3 buckets, etc.)
- assign permissions by creating an IAM policy
- permissions determine **which resources and operations** are allowed:
	- all permissions are implicitly denied by default
	- if something is explicitly denied, it is never allowed
- best practice: follow the **principle of least privilege** (give users the LEAST amount of permissions to do their job)

*Note: the scope of IAM service configurations is global. Settings apply across all AWS Regions*

## IAM Permissions
How does IAM determine permissions?
1. Is the permission explicitly *denied*?
	1. Yes: Deny
	2. No: Is the permission explicitly *allowed*?
		1. Yes: Allow
		2. No: Deny (Implicitly Deny)

# Securing a new AWS Account
Best practice: Do not use the AWS account root user except when e