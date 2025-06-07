>[!Tip]
>Google Cloud had good AI services
>AWS has the cheapest services
# Recap
## Traditional
- an environment where the organization would need to use **dedicated** resources to be used by their services and applications
- issues of a **dedicated** server
	- one or a few services
	- issue in compatibility
- purpose of dedicated
	- expansion
	- sudden need/spikes makes it hard to adjust (5/5 Shopee Sale, Paydays, etc.)
- hard to expand cause you'll have to reallocate or reconfigure multiple machines
## Virtualization
- instead of managing multiple machines, only one machine is needed
- we can **maximize** resources by adding more virtual machines if there're extras
- multi OS design is possible
	- one machine is running on Windows, another on Linux, etc.

# Virtualization
- Has a middleware called Hypervisor— the technology that does the abstraction/translation
## Properties of Virtualization
### Partitioning
- dividing resources between virtual machines
- running multiple OS or VMs in a single physical machine—promoting resource maximization
- promotes flexibility, agility—its fast when you need it (compared to traditional)
- anything about **resources**
- efficiently use and maximize the hardware resources
- the capability of **deploying multiple OS or VMs in a single physical machine**
### Isolation
- **fault isolation** at the hardware level (however, if a physical hardware breaks, the whole system is cooked)
- enables save states and snapshots for easier investigation of a VM crashing or breaking down
- reduce risk of dependencies and conflicts—they don't have to be on a different server and can run by themselves
	- Ex: Green VM can be connected to Red VM but are on different servers(?)
- enables sandboxing of applications and workloads, ensuring compatibility for testing and development environments without affecting the underlying infrastructure
	- sandboxing - isolates sand only within the box
### Encapsulation
- move and copy virtual machines as **files**
- allowed to **combine** and **add information** for it to be complete
- improved portability
- virtual instances being **self-contained**, **independent**, and **portable**
- able to perceive or represent virtual instances as data or files
- as long as its **software**—it's isolation but software-based
### Hardware Independence
- this property will **overlap with other properties**, but not vice versa
- provides **flexibility**, improved disaster recovery, cost efficiency, and simplified infrastructure upgrades (refers to the physical upgrades)
- provision or migrate to any server without the need to perform reconfigurations on the virtual machine
- you can send copies of VMs to other people and they'll run regardless of the user's hardware (ofc their physical machine should have enough resources to run it)
- hardware independence - different hardware brands (AMD or Intel) won't matter
- allows for virtual instances to have the capability to be deployed
- the capability to provision a virtual instance to any host device

## Types of Virtualization

**Server, Network, Storage** 
- for Sir Fritz, these are what started virtualization, then it branched out to more technologies

**Server, Desktop, Storage, Data, Network, Application**
### Server/Compute Virtualization
- the concept of a server is virtualized
- the traditional kind of virtualization
- enables multiple OS to **run on a single physical server**
- **partitions** a physical server into multiple virtual servers
- can be **configured remotely** (user is at home while physical server is in the office)
- benefits include:
	- greater IT efficiencies
	- reduced operating costs
	- maximization of resource
	- faster workload performance
	- higher server availability
	- eliminated server sprawl and complexity
- **keywords: many OS, partition, operations, maximize**
- best described as **enabling multiple** different or similar operating systems to run on a **single physical machine**
	- you get MULTIPLE virtual machines
### Desktop
- desktops are now virtualized
- **keywords: productivity, personal use, DaaS (the service), Remote Desktop Services (desktop as sessions), VDI (the technology), LDV (running it on your local machine—meaning your PC should be beefy enough)**
- typically only one or two virtual machines specifically for work 
- pretty new and especially relevant today
- companies usually give you a desktop but some companies follow BYOD, Remote Work, WFH
- deploying **desktops as a managed service** enables IT organizations to **respond faster** to changing workplace needs and emerging opportunities
- virtualized desktops and applications can also be **quickly and easily delivered** to branch offices, outsourced and offshore employees, and mobile workers using tablets
- typically categorized as Local Desktop Virtualization (LDV) or Remote Desktop Virtualization (RDV) (you use the server's resources, not yours—all you need is a good network and a good monitor—you just stream the desktop on any device so it doesn't matter if you're using a potato PC or even a Tablet
	- LDV - creates a virtualized environment within your own PC—more accessible but not for potato PC
	- RDV - connects to a physical remote machine and is good if you have a potato PC—all you need it good internet connection and a good monitor
- makes desktop management efficient, secure, and saves money on desktop hardware
- Types include:
	- #### Desktop as a Service (DaaS)
		- **cloud service solution** that delivers virtualized desktops and applications
		- sounds like a Cloud Service Model but for STCLOUD (Sir Fritz), he does not consider it as one
			- just a category under the Service Model
			- a solution that cloud services provide
		- Types: client-defined, vendor-defined, and managed DaaS
		- can be present in the public/private cloud
		- something we subscribe to and is on-demand
		- this IS a **service**, but the technology behind this is VDI
	- #### Virtual Desktop Infrastructure (VDI)
		- a **technology/product** that **allows DaaS** to happen
		- a **product** usually deployed on an on-premise datacenter
		- users access the virtual desktop on the server by using client devices
		- Ex: if you have 5 virtual machines, just access the portal and click on the machine you want to access
		- kind of like a remote desktop gateway
		- more cost-effective in the long run compared to DaaS
		- **product or application** that is usually the backbone behind a cloud service delivering virtualized desktops and applications
		- it's like a software you can download 
	- #### Local Desktop Virtualization (LDV)
		- keyword: local
		- hypervisor runs on a **local computer** containing virtual machines
		- **switch** between **local and virtual** environment as application
		- constraint: you are using your local computer—it needs to have enough resources to run both the Host OS + Guest OS
		- good for solo developers if you have a powerful enough PC setup
	- #### Remote Desktop Services (RDS)
		- remote access Windows desktop sessions, also called Terminal Service
		- **multiple users** are using a **shared virtual machine**
		- most companies/organizations use a Dumb terminal to forward you to the mainframe
		- Mainframe - all the computations and shit are being done here
		- we use different accounts (admin, user)
		- other users will see different things on their virtual desktop 
		- one VM, many user sessions
		- single powerful machine then users can just access that same machine without making virtual machines
		- separate sessions, separate accounts
		- it's not like Windows Shared View or something
### Storage
- we're virtualizing the concept of a storage
- **keywords: capacity, DAS, SAN, NAS, backup & redundancy is abstracted, heterogeneity**
- what is a storage?
	- say we have a PC with SSD (120 GB) and HDD (512 GB). you used 60 GB in your SSD, and 450 GB in you HDD. you only have 60 and 62 GB remaining in your SSD and HDD respectively.
	- what if Q > file A = 80 GB? you can't use either storage device since it won't fit
		- Solution 1: if you split the 80 GB into 40 each and store them in both devices? sure this'll work, but the program won't run, cause you'll have to combine them together again for it to work
		- Solution 2: take 40 GB from one device to another, but this'll introduce file transfer issues and can be tedious and corrupt data
		- both solutions are viable, BUT there are limitations
	- we look at storage not as separate disks but as a **capacity**
	- we can combine them into what we call a **Volume Group**—a virtual volume combining two storage devices together (SSD + HDD for example)
	- Volume Group = 632 GB - Used Storage = 510 GB results in 122 GB free
		- now the 80 GB issue from the example earlier is now resolved!
- storage virtualization combines the functions of physical storage devices such as network attached storage (NAS) and storage area network (SAN)
	- in a nutshell:
		- NAS - typically viewed as a SINGLE storage—a **single** computer with a lot of storage connected to the network that also runs a file system/file storage—we treat files as a file storage, meaning we follow a hierarchical storage (file/folders)
		- SAN - it's literally a network of storage devices. instead of a file-based storage, we treat it as a block storage (clusters and stuff). managed by the computer connected to the SAN.
		- DAS (Direct attached storage) - SSD, HDD, Flash drives
		- all are ARCHITECTURES for storage
- whatever the storage architecture or vendors (Sandisk, etc.) you're using, the storage can be pooled despite being heterogeneous, from different vendors or of different types
- storage virtualization uses multiple physical data storage and creates a large unit of virtual storage that you can assign and control by using management software
- IT admins can streamline storage activities, such as archiving, backup, and recovery, because multiple storage devices are **virtually** **combined into a single storage device**
### Data
- virtualizes data sources and its types/formats
	- data can come from many sources: IoT, sales, survey
	- data has many formats: CSV, JSON, XML
	- data can come from various locations: HQ, site, etc.
- **keywords: source, formats, location, abstraction software (API calls), software layer, processes a request, suitable format**
- best described as enabling a software layer between the **data** and **applications**
- best described as having its tool with the capability **to process an application's data request** and return results in a **suitable format**
- combining all these **different formats** from multiple sources is a hassle
- we make a data virtualization tool/solution that can do all these for you
	- just call the API connected to this solution and retrieve the result
- it's like a software level of abstraction
- creates a **software layer** between this data and the applications that need it
- modern organizations collect data from **several sources** and in **different formats** and are stored in **different places**, such as in a cloud infrastructure or on-premises data center
- data virtualization tools process an application's data request (using API calls) and return results in a suitable format
- this results in increased flexibility for data integration and support cross-functional data analysis
### Network
- the idea of a network is now virtualized (switches, firewalls, optic copper, network ports, etc.)
- **keywords: HW Independence, better operations**
- networking is now very flexible
- helps us move beyond the limitations of physical networks
- you can have routers, LAN ports, etc. as software
- completely reproduces a **physical network**, allowing applications to run on a virtual network as if they were running on a physical network
- achieves greater operational benefits and all the hardware independencies of virtualization
- large scale BUT the server will be slow (cause it can reproduce around 1k+ VMs
- network virtualization presents logical networking devices and services to connected workloads, such as:
	- logical ports
	- switches (UTM)
	- routers (UTM)
	- firewalls (UTM)
	- load balancers -> UTM
	- VPNs and more -> UTM

![[Pasted image 20250515115950.png]]
DMZ Architecture
- web and database are interconnected
- internet can only connect to web server but cannot connect to database
### Application
- virtualizes the concept of an app
- **keywords: apps itself, stream, remote, local**
- an app is a software we download from the internet and use it
	- though, there are compatibility issues like apps only for mobile or desktop
- application virtualization pulls out the functions of applications to run on operating systems other than the OS for which they were designed (ex: run Linux apps on a Windows machine w/o any configurations)
- application streaming - users stream the application from a remote server. runs only on the user's device when needed
- server-based application virtualization - users access the remote application from their browser or client interface without installing
- local application virtualization - the application code is deployed with its own environment to run on all operating systems without changes
- allows **software and applications** to be accessed **remotely**
- **enables software** to run on operating systems other than those that they were not designed for
	- Ex: Allows for playing games not available in Linux 
- Ex: G-Suite or Office 365, Steam, Epic Games, etc.
## Benefits of Virtualization

### Reduced capital and operating costs
#### What
- Reduces the need for physical hardware cutting both upfront investments and maintenance costs.
- Capability to run multiple VMs. This means using a hypervisor to host many independent virtual computers on one physical machine, maximizing hardware utilization.
- Due to its abstraction and emulation of hardware, virtualization allows users to create a new machine but with little cost for the materials needed.
-  Virtualization allows you to run multiple virtual machines on a single physical server, reducing the need for a large number of physical servers. This consolidation leads to lower hardware costs and reduced energy consumption for power and cooling.
#### Why
- This cuts costs, particularly on hardware investment and power consumption as well as maintenance expenses.
- Fewer physical servers mean less power usage, cooling, and space requirements. This lowers expenses.
- By consolidating workloads, organizations can lower expenses. Fewer physical servers are needed, directly reducing hardware purchases, power consumption, cooling costs, and physical data center space.
- This helps reduce the need for buying additional hardware and costs less for maintenance.

### Minimized or eliminated downtime
#### What
- Virtualization allows for live migration in which VMs can be moved between hosts without shutting them down, minimizing downtime.
- Fewer physical servers mean less power usage, cooling, and space requirements. This lowers expenses.
- By consolidating workloads, organizations can lower expenses. Fewer physical servers are needed, directly reducing hardware purchases, power consumption, cooling costs, and physical data center space.
- This helps reduce the need for buying additional hardware and costs less for maintenance.
#### Why
- This cuts costs, particularly on hardware investment and power consumption as well as maintenance expenses.
- Fewer physical servers mean less power usage, cooling, and space requirements. This lowers expenses.
- By consolidating workloads, organizations can lower expenses. Fewer physical servers are needed, directly reducing hardware purchases, power consumption, cooling costs, and physical data center space.
- This helps reduce the need for buying additional hardware and costs less for maintenance.
### Increased IT productivity, efficiency, agility, and responsiveness
#### What
- Virtualization streamlines management and automates processes, enabling IT teams to deploy and manage systems more effectively.
- Virtualization lets IT teams deploy, manage, and scale systems faster.
- Streamlined IT operations. This involves managing all virtual resources from a central console and dynamically allocating resources from shared pools.
- Virtualization allows faster deployment, centralized management, and better resource utilization
#### Why
- Centralized management, automated resource allocation, and reduced manual tasks enable IT staff to react promptly to organizational requirements.
- Encapsulation allows for IT teams to quickly move around virtual machines without the need for much manual setup.
- Since multiple VMs can run on a single server resources are maximized increasing overall efficiency. IT staff can provision and manage resources faster and with less manual effort, improving response times to business needs and getting more value from existing hardware.
- Running multiple virtual machines is possible due to not requiring hardware and manual labor, saving time
### Faster provisioning of applications and resources
#### What
- New servers, environments, or applications can be swiftly deployed using VM templates or containers.
- Virtual machines and containers can be created quickly, speeding up deployments.
- Templates for VMs. Pre-configured VM images, along with automation tools, allow for rapid deployment of new virtual machines
- Means that new systems, applications, or services can be set up and made available more quickly.
#### Why
- The predefined configurations and automation facilitates the setup process, significantly decreasing deployment time.
- Automation tools make it easy to spin up environments on demand. Virtualization removes the need for manual setup per machine.
- Automated provisioning eliminate the need for manual hardware configuration essentially removing the need for IT personnel to manually set up hardware. New servers and applications can be deployed in minutes rather than weeks, as the need for physical hardware setup is removed, freeing up IT staff.
- Allows IT teams to create and deploy virtual machines or environments from pre-configured templates, eliminating the need for manual hardware setup and significantly speeding up deployment times.
### Greater business continuity and disaster recovery
#### What
- VMs can be easily backed up, replicated and restored across various locations, leading to greater business continuity.
- Virtualization enables backups and failovers that help maintain operations during disruptions.
- VM Security and Replicability. This includes features like point-in-time snapshots for quick rollbacks and the ability to continuously replicate VMs to a secondary location.
- Operations can continue with minimal interruption during unexpected events, and systems can be quickly restored after failures.
#### Why
- Virtualization enables efficient backup strategies and failover systems, minimizing data loss and downtime during disasters.
- VMs can be replicated and restored quickly, reducing data loss and downtime.
- Features like snapshots and automated failover ensure that critical systems can be quickly restored. Snapshots allow instant recovery from errors, while VM replication and automated failover drastically improve recovery times (RTO) and minimize data loss (RPO) during major outages.
- Enables features such as backup snapshots, VM replication, and failover systems, which allow rapid recovery and smooth transitions to backup environments.
### Simplified data center management
#### What
- Virtualization centralizes control over computing, storage and networking resources, facilitating easier management from a single interface.
- Managing a virtualized environment is easier with centralized control panels and automation.
- Centralized IT resources. A unified management platform provides a single interface to oversee and control all virtualized components (servers, storage, network).
- Easier to monitor, control, and maintain IT infrastructure
#### Why
- Administrators can monitor and manage virtual environments more efficiently, reducing complexity as management tools provide a unified view of the entire infrastructure.
- Instead of having to manage multiple different machines and monitor each one, much of the work can be done via automation tools or through a singular panel.
- Administrators can easily view and manage IT resources making administrative tasks more streamlined. It provides a holistic view of the entire IT environment, simplifying monitoring, troubleshooting, and configuration tasks for administrators.
- Virtualization centralizes management, automates tasks, and reduces the number of physical servers, making the entire environment easier to oversee and operate.
### Availability of a true Software-Defined Data Center
#### What
- All elements of the data center such as computing, storage and networking resources, are abstracted into software.
- Virtualization is a key component of Software-Defined Data Centers as all infrastructure is managed through software.
- Virtualizing resources. This extends virtualization beyond just compute power to also include the network (Software-Defined Networking) and storage (Software-Defined Storage).
- All data center resources—compute, storage, networking, and security—are virtualized and managed through software.
#### Why
- Virtualization enables full automation and scalability by decoupling hardware from software, allowing for dynamic allocation of resources through centralized software tools.
- Virtualization abstracts hardware, allowing flexible, automated control over resources.
- Virtualization allows the capability of turning hardware components into software enabling SDDC. By abstracting all hardware into software, the entire data center infrastructure can be managed and automated programmatically, offering unprecedented flexibility and efficiency.
- Virtualization enables abstraction and automation of hardware functions, allowing flexibility and full control through software without relying on physical hardware.
# Hypervisors
![[Pasted image 20250526130809.png]]

- also known as a virtual machine monitor, or VMM, is a software that **creates** and **runs virtual machines**
- allows for a host computer to support multiple guest VMs by **virtually sharing** its resources
	- **Virtualization = Sharing**
- also provides **greater IT mobility** since the guest VMs are independent of the host hardware
- multiple virtual machines can **run on one physical server**, **reducing space**, **energy**, and **maintenance** requirements
- Ex: Microsoft Hyper-V, PROXMOX (open-source and is used in CCS Cloud), Xen Project, VMWare ESXi (one of the best ones)
	- these are all Type-1 Hypervisors 
## Virtualization and Hypervisors
- virtualization works by **abstracting physical hardware** and devices from the applications running on that hardware
- Hypervisors **makes virtualization possible**—it does that layer of abstraction—by translating requests between the physical and virtual resources
- Hypervisors support the **creation and management of VMs by abstracting** a computer's software from its hardware
- Bare metal hypervisors are sometimes embedded into the firmware (BIOS) to enable the OS of a computer to access and use virtualization software (Intel-VT or AMD-V)
- Decoupling - removing independency between hardware and software??
- **Don't confuse** bare metal with host machine
	- bare metal - physical machine
	- host machine - the "machine" that hosts a guest machine. this doesn't restrict the host machine to a physical one. host machines can be virtual ones that "host" another virtual machine inside it.
- **Virtualization - technology**
- **Hypervisor - translation and abstraction**

## Benefits of Hypervisors
### Speed
- virtual machines can be **created instantly**, making it easier to provision resources as needed for **dynamic workloads** (changing workloads, either scaling up or down)
- elasticity 
### Efficiency
- running **several VMs on a physical machine is more efficient** than to run multiple underutilized physical machines
### Flexibility
- **separates the OS from the underlying hardware**, so the software no longer relies on specific hardware devices or drivers
### Portability
- **multiple OS** to reside on the **same physical server**; VMs in the hypervisor run **independently** from the physical machine; allows **shifting of workloads** and **allocate resources as needed**
## Types of Hypervisors
### Type 1 - Bare Metal of Native Hypervisor
- **lightweight OS** directly running on top of the host machine
- **isolated** from the guest OS, resulting in **better security**
- **better performance** than hosted hypervisors (Type 2)
- mostly used by **enterprise** for **data center** computing needs
- performance-wise is the best choice
- you don't use the hypervisor directly—usually two or more machines with one machine dedicated for the hypervisor
- normally for datacenters
- **viewed as an OS**
- has fewer levels of abstraction
- PROXMOX, Hyper V, ESXi, Xen
	- Hyper V: VM -> HW
### Type 2 - Hosted or Client Hypervisor
- runs as a **software** on an OS, like other programs
- can still run the **same** or a **different guest OS** from the host OS
- have **higher latency** than bare metal hypervisors
- mostly used by end users and software testing, where higher latency is less of a concern
- what we're more familiar with
- VMWare Player, VMWare Workstation, VMWare Fusion, Virtual Box, Parallels
- **viewed as an app or software** 
- has more steps in levels of abstraction (more levels of abstraction)
		![[Pasted image 20250526134948.png]]
	- VM2 -> Hypervisor -> OS -> Hardware
#### Note: 
A **bare-metal server** (non virtualization or traditional) will always provide **higher performance** than a virtual server sharing with other virtual servers. **(good for speed)**
	Why? Because there's no hypervisor, no abstraction/translation. It's direct, pure, resource use for that particular machine
		BUT there's no resource maximization for this option 

Traditional > Type 1 > Type 2
### Difference of T1 and T2 Hypervisors
![[Pasted image 20250526135451.png]]
- T1 OS level is the same as Hypervisor level

![[Pasted image 20250526140053.png]]

![[Pasted image 20250526135821.png]]

#### Main Difference
- T1 Hypervisor is treated as the OS
- T2 Hypervisor is treated as a separate layer (as an application)

## Virtual Machines vs Containers
![[Pasted image 20250526140538.png]]

### Containers
- shared OS
- OS Virtualization
- the OS is from the container engine
- it gets the container engine and the kernel, and that's what it uses for its OS
- best option for same OS setup
- lightweight—due to it having no OS
- it gets the running OS portion from the hosts'
- shares the host's kernel for each container
- more portable
- uses fewer resources
- good for portable and scalable **applications**

### Virtualization
- different OS setup
- starts slower cause it has to boot up its own OS
- heavy cause it has its own OS installed
- guest OS is totally separate from the host's OS
- less portable
- uses more resources
- good for **isolation** or isolating applications

## Hypervisors vs Containers
Container Engines are closer to Hypervisors

### Hypervisors
- allows an operating systems to run independently from the underlying hardware using VMs
- can run multiple OS on top of a bare-metal hypervisor or installed on top of the OS of a hosted hypervisor
- share virtual resources
- used to create and run VMs
- more featured and is generally used by end users to enterprise organizations

### Container
 - allows applications to run independently
 - run on any operating system
 - for apps basically
 - extremely portable
 - these package an app and its services
 - more lightweight and portable than VMs and used for fast and flexible app development and deployment
 - great for application environments, packages, dependencies

## Virtualization vs Cloud
### Virtualization
- this is the **technology**
- creates multiple simulated environments from 1 physical hardware system
- configuration is image-based (ISO)
- lifespan lasts for years (long-term)
- high capital expenditures (CAPEX) but low operating expenses (OPEX)
- workload focuses on scaling up
- tenacity is stateful

### Cloud
- methodology or service that **uses** virtualization
- self-service, on-demand platform
- it's like making a UI and running API calls to virtualize something
- makes virtualization more accessible to those who are familiar with the technology
- pools and automates virtual resources for on-demand **use** (keyword: use—cause cloud is a **usage**)
- configuration is template-based (something reproducable or a static format)
	- creates packages like how buying a Combo Meal from Jollibee is faster and more convenient than buying individual meals
- lifespan lasts hours to months (short-term)
- Private cloud: High CAPEX, low OPEX
- Public cloud: Low CAPEX, high OPEX
- workload focuses on scaling out—distribution, deployment, etc.
- tenacity is stateless