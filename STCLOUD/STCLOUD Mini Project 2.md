# Objective: 
To create a cost estimation of owning and maintaining a machine in the **Cloud** vs that of a **Traditional** infrastructure

# Scenario:
The CCS department of DLSU spearheaded a program to provide computational and storage resources to its students and faculty members. However, they are unsure which of the following choices are more *cost-effective per computation or storage capability*:
1. Purchasing a physical machine and deploying it as a **traditional** infrastructure
2. Availing services on the **cloud**, particularly with AWS, Azure, or Google Cloud as a possible public cloud provider

The computational and storage considerations of the College is as follows:
- **CPU** - either a i5 or i7 processor with **8 to 16 cores**
- **Memory** - either **16GB or 32GB**
- **Storage** - either **128GB or 256GB SSD** or **512GB or 1TB HDD**

Part of their proposal is to draft a cost estimate of purchasing and maintaining a physical device compared to availing a cloud service.

// Compare the cost of traditional vs cloud 

Since they are unsure of a lot of things, the College would like to know the following information:
1. **Cost of purchasing and maintaining a physical machine** for both *CapEx* and *OpEx*
	- look for a Desktop Computer (no need for I/O and peripherals) that is within the identified considerations from https://villman.com/Category/Desktop-PCs or https://asianic.com.ph/product_list/desktops
	- you may **include electricity only as part of the OpEx**, as we can assume that manpower and Internet connectivity is already available in the datacenter
	- the **cost estimate** should also include the electricity bill *during* operation
		- _*The cost of the electricity bill may be estimated from the Wattage or VA of the Desktop Computer's Power Supply following 12kWh cost. Use the following electricity bill calculator for your estimates:_ [_https://www.rapidtables.com/calc/electric/electricity-calculator.html_](https://www.rapidtables.com/calc/electric/electricity-calculator.html)
2. **Cost of availing a cloud service, with AWS, Azure, and/or Google Cloud**
	- make the specifications of the cloud machine, **similar to that of the physical machine** that you would use for the estimation (for price competitiveness)
	- the cloud machine would generally use server processor cores and such, but for the sake of ease in computation, **abstract those details as just CPU cores along with RAM**
	- Details of the estimate would be as follows:
		- have two (2) general scenarios:
			1. have the machine run 24/7
			2. run only from 8AM to 5PM daily
		- remember to choose a region that is **close** to the intended user or that would have the **least** cost (cite reason for your choice in the documentation)
	- For each of the defined scenarios, compute for the estimate when using the following:
		- (1) On-Demand Instances;  
		- (2) Standard Reserved Instance a reservation term of 1 year and no upfront payments;  
		- (3) Standard Reserved Instance a reservation term of 1 year and partial upfront payments;  
		- (4) Standard Reserved Instance a reservation term of 1 year and all upfront payments;   
		- (2) Standard Reserved Instance a reservation term of 3 years and no upfront payments;  
		- (3) Standard Reserved Instance a reservation term of 3 years and partial upfront payments; and  
		- (4) Standard Reserved Instance a reservation term of 3 years and all upfront payments.
		- *Note that all reservation options may not be available for all providers (AURI, PURI, NURI) so use only if applicable.*
# Task
To support the College by creating a **documentation** (max of 3 pages) with the following information:
1. First is to have about **1 page discussing the desktop computer and cloud machine specifications**. Also, discuss the similarity and differences (if any) of the machines used as reference. Remember to **include the link of the specific desktop computer** that you would be referencing and a **screenshot** containing its brief description, technical specifications, and price. Finally, the **specifications of the different cloud machines from the 3 identified cloud service providers**. Use a table to show the details of all 4 machines

2. Have **1 pages showing the cost estimation and calculations**. You may use tables to provide a clean an thorough representation of your estimates. Don't forget to **include some graphs** to show the comparison of these costs throughout the years and identify points where the costs meet if any.  

3. Lastly is to have **1 page to discuss the findings, analysis, conclusion, as well as your recommendation** for the College. Also provide a **discussion of possible savings if they choose one option over the other**. Additionally include your own assumptions and limitations used in the cost estimates provided, if any (i.e., excluding software license costs, manpower costs, rental costs, etc.).  

4. Also **don't forget to include your spreadsheet for the base computations as reference** only, but the written document should contain most of the relevant information.