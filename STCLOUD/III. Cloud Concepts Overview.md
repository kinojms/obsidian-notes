# Cloud Computing
- is the on-demand deliver of **computing** or **IT resources** via the **network**
- AWS - public cloud
- cloud deployments
	- public
		- via the internet
		- pay as you go
	- private
		- via the network
		- capex/opex
	- hybrid
- if we say internet, it does not fully reflect the definition of a private cloud

**Infrastructure as Hardware**
- cloud computing enables (due to virtualization) you to stop thinking of your infrastructure as hardware, and instead think and use it as software
## Traditional Computing Model
- infrastructure as hardware
- hardware solutions:
	- requires space, staff, physical security, planning, capital expenditure
		- cooling, electricity, floorplan, etc.
	- have a **long hardware procurement cycle**
	- require you to provision capacity by **guessing** theoretical maximum peaks

## Cloud Computing Model
- infrastructure as software
- software solutions:
	- are flexible—on-demand
	- can change more quickly, easily, and cost-effectively than hardware solutions
	- eliminate the undifferentiated heavy-lifting tasks

## Cloud Service Models
### IaaS (Infrastructure as a service)
- **computing resources**
	- servers
	- storage
	- networks
	- firewalls
	- public IP
- flexibility over controls (more control over IT resources)
- **full control**
### PaaS (Platform as a service)
- **control panel**
- can choose apps/software
	- apache, nginx, mysql, mongodb, filezilla, etc.
- can choose version
- kinda like a **dashboard** for you to choose options
- **less flexible** compared to IaaS
- **just enough control**
### SaaS (Software as a Service)
- **lesser control** over IT resources
- more on subscription
	- google drive, onedrive, gdocs, wordpress
- no version selection
- no app/servers
- user-level customization
- **no control**
## Cloud Computing Deployment Models
### Public Cloud
- internet, global
- pay as you go
- subscription/rental
- low capex/high opex
### On-premises (Private Cloud)
- most companies have their own private cloud solutions
- CCS cloud is an example
- single organization
- network
- high capex/low opex
	- you own it, you buy the servers. so high capital
	- low monthly costs for maintaining the servers
### Hybrid
- startups produce their own servers
- public + private
## Similarities between Public Cloud and Traditional IT
### Traditional
- **Security**: firewalls, ACLs, Admins
- **Networking**: router, network pipeline, switch
- **Compute**: on-premises servers
- **Storage and DB**: DAS, SAN, NAS, RDBMS
	- DAS - USB's
	- SAN - area of storage devices
	- NAS - network attached storage—centralized location on a network to store data
### Public Cloud
- **Security**: security groups, Network ACLs, IAM
- **Networking**: Elastic Load Balancing, Amazon VPC
- **Compute**: AMI -> Amazon EC2 instances
- **Storage and DB**: Amazon EBS, Amazon EFS, Amazon S3, Amazon RD5

Products can just be a combination of the following resources: **Security, Networking, Compute, and Storage**

#### Security
- a very important aspect
- make sure to understand its implications
- it is an integral part of any application, process, research, etc.
- **Firewalls** - they're just if statements
- Security groups - 
- ACLs - 
- Administrators - active directory; we have users, roles which we can give permissions to

# Advantages of Cloud Computing
- but some are mostly advantages of virtualization

## Trade capital expense for variable expense
- capex - initial payment; one time big time 	
- opex - recurring costs (rent, utility, etc.)
- data center investment based on forecast
- pay only for the amount you consume
- if you KNOW its worth it, then a high capital would be better
- if you're not sure, then variable expense is viable
## Massive Economies of Scale
- because of aggregate usage from all customers, AWS can achieve higher economies of scale and pass savings on to customers
- AWS Cloud (Economies of Scale) --> Savings
- For example:
	- Server = 1M
	- 10 Servers = 9M (discounted cause of the buy in bulk deal)
## Stop Guessing Capacity
- enables scaling on demand
- you don't have to second guess in buying servers for your business 
- in a traditional perspective, the following can happen:
	- if you buy 2 servers but they weren't fully utilized, then you overestimated server capacity
	- if you buy 2 server but needed 4, then you underestimated server capacity
## Increases Speed and Agility
- the reason for this is because we use virtualization
- since its virtual, we can just click and we're done
- issue: weeks between wanting resources and having resources
- cloud converts that to minutes rather than weeks
## Its not about saving money
- its more on the perspective **where** your money is used
- you are spending more money, but you're also earning more profit out of it
- you can just focus on growing your business faster rather than think about the tedious and stress-inducing aspect of running data centers
- put your money somewhere else rather than allocating all to data centers
## Go global in minutes
- however, if you're a PH based company and your clients are also in the PH, then this isn't an advantage
- may be an advantage on a base-to-base case 
- not **always** an advantage
- if company is NOT on a global scale, but clients are global, then its an advantage

# Cloud Services
- a **web service** is any piece of software that makes itself available over the internet and uses a **standardized format**—such as Extensible Markup Language (XML) or JavaScript Object Notation (JSON)—for the request and the response of an **application programming interface (API) interaction**

## Choosing a Service
- the service you select depends on your business goals and technology requirements
- figure out the service models you want first, then select the service you wish to use

## Ways to interact with AWS
- AWS Management Console (Web UI, business, new students)
	- easy-to-use graphical interface
- Command Line Interface (AWS CLI) (IT, Ops)
	- access to services by discrete commands or scripts
	- the best and fastest for experienced users
- Software Development Kits (SDKs) (DevOps, devs)
	- access services directly from your code (such as Java, Python, and others)
	- if you wanna make a new version of something

## Cloud Adoption Framework: Six Perspectives
Business
People
Governance
- focus on **business** capabilities

Platform 
Security 
Operations
- focus on **technical** capabilities

Reflect on these first before you decide
Shared Responsibility Model - some responsibility lies on you, and some on the cloud