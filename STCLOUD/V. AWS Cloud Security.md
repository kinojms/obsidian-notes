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

Sample Services Managed by Customer:
Amazon EC2, Amazon Elastic Block Store, Amazon Virtual Private Cloud

Sample Services Managed by AWS:
AWS Lambda, Amazon Relational Database Service, AWS Elastic Beanstalk (automates deployment of resources)