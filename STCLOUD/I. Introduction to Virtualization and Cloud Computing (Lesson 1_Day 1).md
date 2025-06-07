# Brainstorming
## Cloud
- **Web services** like databases, servers, storage, network
- Not on-premise (something we do not/cannot touch)
	- Public Cloud - AWS, Google, Azure, Alibaba
		- **not on-premise**
	- Private Cloud - CCS Cloud 
		- **can be on-premise**
		- owned and managed by the organization only for **them** specifically
	- Hybrid Cloud
		- can be both **on-premise** and **off-premise**
- access via the internet/network
	- when accessing public cloud services, we use the internet/network
	- if you access CCS Cloud and you are on-premises, you can access it as long as you are connected to the **local network** (internet is NOT required, only the network)
	- **Internet: Private and Hybrid**
	- **Network: Private, Public, and Hybrid**
- cost
	- energy, data centers
	- expensive - it depends
	- flexible, subscriptions
- on demand

When we talk about the "Cloud" it's something up in the sky (we don't see it)

This is like how Cloud Computing is done through the internet

When we access networks, it passes through multiple servers, companies, etc.

Is it cheaper? Is it expensive? The answer is "it depends"
## Virtualization
- simulation & emulation
- virtual resources
	- memory, machine
	- instead of physical RAM slots, we use virtual ones
	- intangible
	- copy what's in the real world and digitize them
	- virtual machine, memory, storage, desktop, containers, etc.
		- when RAM is insufficient, storage can be used as an alternative
		- RAM -> Storage swaps
		- Ex: If your PC has 8 GB RAM but you need 12 GB for something, we can use our SSD which has (for ex) 8 GB. Allot 6 GB from RAM and 6 GB from SSD swap them to each other, then you got 12 GB. 
		![[Pasted image 20250508114912.png]]
- machine (guest) within a machine (host)
	- Guest = Virtual, Host = Physical
	- Ex: Mac OS with Windows Virtual Machine
	- solves compatibility issues (scripts that only run on Linux when you're using Windows)
	- we can use this to simulate different environments (mobile OS in your laptop)
	- has state-saving capabilities (copy the current virtual machine's state like a save file in games)
- hardware solutions as software
	- converting something physical to virtual
- intangible

## Cloud vs Virtualization
- cloud is the **service**, **usage**, or **methodology**
- virtualization is the **technology**
## Traditional
- usual PC
- single OS
- on-premise or access via the network/remote desktop
- physical

![[Pasted image 20250508115728.png]]

# Traditional Computing
Refers to the use of **physical servers** and **datacenters** to deliver computing and other IT services

This used to be the **old practice** where **dedicated servers** are commonly used

The **host computer** would typically be installed with a **single OS directly on the hardware**

Since its dedicated, when the organization uses two OS (Windows and Linux for ex), they would need to use two separate servers for it

Would typically run one or a few applications per machine, which results in possible issues in **resource allocation** and **difficulty in scaling**
- servers may end up being **over utilized**—too much resource was allocated to this server/machine)
- or **under utilized**—resources were allocated to a machine with little to no traffic or usage)
## Compared to Virtualization:
- you can have 1 powerful machine, then given the resources of that machine, you can reallocate resources depending on the situation since it's a software and it's all on the same machine anyway (unlike Traditional where you need/have separate machines per server)
- maybe its lunch break and no ones using email server as much, then you can allocate that to other servers in the meantime. This is what we call **over provisioning**
- Over provision - you're providing extra resources even though not all the resources are being fully utilized 
# Virtualization

The technology that you can use to **create virtual representations of servers, storage, networks**

Mimics the functions of physical hardware

A Virtual Machine or VM is:
1. **self-contained** - a complete computer—can be copied and shared it'll still work properly
2. completely **independent** - not dependent on your physical machine's specs
3. **isolated software container** - all of its resources, OS, and applications are already there

Multiple VMs can run on a single computer (multiple LDPlayer instances lmaoo) with several OS
## Without Virtualization (if we stick to Traditional)
- due to **limitations of x86 servers**, many IT organizations must deploy multiple servers, each operating at a fraction of their capacity
- they might not **FULLY UTILIZE** all their resources
- instead of **MAXIMIZING** them, there are issues with dependencies so we'll have to **split it**
- Result = huge inefficiencies and excessive operating costs

## With Virtualization
- since it relies on software to simulate hardware, it enhances functionality while creating a virtual computer system
- enables IT organizations to **run more than one virtual system**
- you only have to manage ONE physical machine and enables easy resource allocation
- Result = economies of scale (cheaper) and greater efficiency
## To double-down on the point...
![[Pasted image 20250508122608.png]]
### Traditional Scenario
![[Pasted image 20250508122919.png]]
- Resources were wasted on more computers(?)
### Virtualization Scenario
![[Pasted image 20250508123104.png]]
- the extra resources (green) can be used in other services