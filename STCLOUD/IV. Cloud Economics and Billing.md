# AWS Pricing Model
## Compute
- CPU, GPU, etc.
- charged by:
	- charged **per hour/second**
		- hour - corresponds to duration—how long you're using the machine
	- varies by instance type
		- CPU, RAM, Storage
	- by location
		- you can choose the region
		- per region has a difference in price
	- cost always depends on the use case 
	- *per second is for Linux only*

*Note: We use Cloud Pricing Calculators to estimate how much it will cost you if you would opt for cloud or on-premise*

*We WON'T have computations for Midterms*

## Storage
- charged by:
	- charged typically per GB
	- storage type

## Data Transfer
- outbound is aggregated and charged
- inbound has no charge with some exceptions)
	- depends where the data passes through
- charged typically per GB

# How do you pay for AWS?
- rent, reserve, volume-based discount, time
## Pay for what you use
- pay only for the services that you consume, with no large upfront expenses
- rent / on-demand
- more demand than reserve
- focuses on **rental** or **operational expenses**
	- may be good for you if you don't have that much money from the start 
- scaling in and out = elasticity
## Pay less when you reserve
- you are committing to a **long-term usage** of the cloud
- **lower cost** at the expense of **guessing capacity**
- 1 or 3 yr commitment
- *Note: If you reserve, you lose scaling on-demand advantage
- is cheaper than on-demand
- invest in Reserved Instances (RIs)
- save up to 75%
- Options for reservation:
	- **All Upfront Reserved Instance (AURI)** -> Largest discount
		- similar to traditional
		- *high capex, low opex*
	- **Partial Upfront Reserved Instance (PURI)** -> Lowest discount
		- seen as a down payment with monthly cost
		- *capex + opex*
	- **No Upfront Payments Reserved Instance (NURI)** -> Smaller discount
		- rent but w/ commitment
		- *high opex, low capex*
## Pay less when you use more and as AWS grows
- volume based discounts
- realize volume-based discounts:
	- savings as usage increases
	- tiered pricing for services like Amazon Simple Storage Service 
- As AWS grows:
	- services become cheaper over time
	- AWS focuses on lowering cost of doing business
	- this practice results in AWS passing savings from economies of scale to you
## Custom Pricing
- special pricing for high volume clients
- meet varying needs through custom pricing
- available for high-volume projects with unique requirements
## AWS Free Tier
- free use or **credits** for some services


*Note: Cloud is not perfect. There are certain use cases where cloud is great and where it's not. You have to consider what's beneficial for your company. (Cost-Benefit Analysis)*

## Services with no charge
- no cost for configuration/orchestration
- but you pay for services that they provision
- Orchestration - deploying servers, configs, etc.
	- there are rules and you automatically deploy your resources
- Ex:
	- Amazon VPC - Network
	- Elastic Beanstalk - Orchestration
	- Auto Scaling - Orchestration
	- AWS CloudFormation - Orchestration
	- AWS Identity and Access Management - Directory Services / Orchestration
- not everything has a cost

# Total cost of Ownership
**How do you compare which is cheaper between on-premise vs. cloud?**
- they are very different, but COST can be a common factor to consider
![[Pasted image 20250616131940.png]]

## Total Cost of Ownership (TCO)
- the financial estimate to help identify direct and indirect costs of a system
- Why use TCO?
	- to compare the costs of running an entire infrastructure environment or specific workload on-premises vs. on AWS
	- to budget and build the business case for moving to the cloud
- Financial Estimate of Renting vs Owning

### TCO Considerations
![[Pasted image 20250616132311.png]]

- on premise considers HW, SW, Facilities, and Labor as considerations for TCO
### AWS Pricing Calculator
- all cloud providers give a way to estimate the cost of services
- use the calculator to:
	- estimate monthly costs
	- identify opportunities to reduce monthly costs
	- model your solutions before building them
	- explore price points and calculations behind your estimate
	- find the available instance types and contract terms that meet your needs
	- name your estimate and create and name groups of services
- easier compared to manually computing traditional costs

### Additional Benefit Considerations
- consider if it is beneficial to your business and technology needs
- **Hard Benefits:**
	- reduced spending 
	- reductions in hardware and software purchases (capex)
	- reductions in oepx, backup, and disaster recovery
	- reduction in operations personnel
	- not more of reducing cost, but rather where you're putting you money (redirecting money to other places)
	- you don't necessarily reduce spending but instead you:
		- outsource
		- rent/subscribe (opex)
- **Soft Benefits:**
	- reuse of service and applications that enable you to define (and redefine solutions) by using the same cloud service
	- increased developer productivity
		- focus on PaaS/SaaS or Infra as SW
	- improved customer satisfaction
		- latency & ease of use
	- agile business processes that can quickly respond to new and emerging opportunities
		- speed & agility
	- increase in global reach
- *Note: It's all based on use-cases where it might be more beneficial for you to go for cloud* 
