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
- free use or ****