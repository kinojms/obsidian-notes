## Distributed vs Decentralized
![[Pasted image 20250916134345.png]]

### Two views on realizing distributed systems
- integrative view - connecting existing networked computer systems into a larger system
- expansive view - an existing networked computer systems is extended with additional computers
### Two definitions (Will show up in exams)
- Decentralized system
	- processes and resources are **necessarily** spread across multiple computers
	- ex: MVC applications
- Distributed System
	- processes and resources are **sufficiently** spread across multiple computers
	- ex: Torrents, Fitgirl, etc.
		- functions both as a producer and consumer
### Some common misconceptions
- centralized solutions **do not scale**
	- make distinction between **logically** and **physically** centralized
	- the root of the DNS (Domain Name Service):
		- logically centralized
		- physically (massively) distributed
		- decentralized across several organizations
- centralized solutions have a single point of failure
	- generally not true
### Perspectives on Distributive Systems
- Architecture - common organizations
- Process - what kind of processes, and their relationships
- Communication - facilities for exchanging data
- Coordination - application-independent algorithms
- Naming - how do you identify resources?
- Consistency and Replication - performance requires of data, which need to be **the same**
- Fault tolerance - keep running in the presence of partial failures
- Security - ensure authorized access to resources