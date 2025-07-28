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