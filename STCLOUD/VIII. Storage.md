# Core AWS Services
## Networks
- represents I/O
- Amazon VPC
## Compute
- represents CPU
- Amazon EC2
## Storage
- represents Memory/Storage
- Amazon Storage Buckets, Databases, etc.

*These are **core** services because each represents the resources that make up the design of how our computers work*
## Security
- AWS Identity and Access Management (IAM)

*Other services are generally branches of these main services*

# Storage

Has four categories: Amazon S3, Amazon EBS, Amazon EFS, Amazon S3 Glacier

## Amazon S3
- object storage
- the entire entity is considered an object
- great for static files (images, videos, audio)
- each file is an object
- Ex: Google Drive
- you can't put an OS in here
## Amazon EBS
- block storage
- treats a file as a series of chunks or clusters
	- a group of many blocks
- VM/CT
- hard drives, SSDs use block storage
- great for dynamic files (those that constantly change)
	- Ex: text files, documents, databases, etc.
## Amazon EFS
- NFS - network file systems
- high scale storage
- file sharing
- non root disk
## Amazon S3 Glacier
- also an object storage, but the difference is that this is more for **long-term**
- specifically called an **archival** storage which uses magnetic tapes (like a cassette)
	- functions like a long tape (like a turing machine) that has a reader which reads the middle part of the strip as it rotates
	- you can't skip here, you have to rewind it if you want to go back to a certain part
- cheapest price per GB
- not instant retrieval
- think of it like going back to school after years post-graduation just to request for a copy of your Form 137

# Databases
## Amazon Relational Database Services
- Relational Database (RDS), PaaS, Managed SQL DB
- managed service - the cloud manages the service FOR you (like configurations) so you can focus on your data
- SQL 
- vertical scale - many entries, same columns
- *if you are confident in your skills in handling databases, it might be better to opt for VMs instead*
## Amazon DynamoDB
- 