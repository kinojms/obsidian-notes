Drive Link: https://drive.google.com/file/d/1WUWgxMVn2qwlMFb3FxUXxJn5Y4LLWOMG/view

# Chapter 1
**Operating System**
- a software that manages a computer's hardware
- kinda like a Temu manager allocating/planning the amount of workload to give to certain child laborers

## 1.1 What Operating Systems do
We first look at the OS' role in the overall computer system. 

A *computer system* consists of the following components: ***hardware***, ***OS***, ***application programs***, and the ***user***.

**Hardware** - the CPU, the memory, and the I/O devices—provides the basic computing resources for the system

**Application Programs** - word processors, spreadsheets, compilers, and web browsers—define the ways in which these resources are used to solve users' computing problems. 

***The OS controls the hardware and coordinates its use among the various application programs for the various users***

**Computer System** - consists of the hardware, software, and data. 

***The OS also provides the means for proper use of these resources in the operation of a computer system. Kind of like the government, where it provides an environment so other programs/committees can do useful work***

### The User View
The goal is to maximize the work that the user is performing. In this case, the OS is designed mostly for **ease of use**, with some attention to performance and security and **none paid to resource utilization**.

![[Pasted image 20250504203509.png]]

### System View
From the computer's POV, the OS is the program most intimately involved with the hardware. We can view an OS as a **resource allocator**. A computer system has many resources that may be required to solve a problem: CPU time, memory space, storage space, I/O devices, and so on. 

An OS is a control program. A **control program** manages the execution of user programs to prevent errors and improper use of the computer. It is especially concerned with the operation and control of I/O devices.

### Defining Operating Systems
*The term OS covers many roles and functions.*

But in general, we have no completely adequate definition of an operating system. OS exist because they offer a reasonable way to solve the problem of creating a usable computing system. The fundamental goal of computer systems is to **execute programs and make solving user problems easier.**

The common definition, and the one we usually follow, is that the OS is the one program **running at all times on the computer**—usually called the **kernel**. There are also two other types of programs:
- **System Programs** - these are associated with the OS but are not necessarily part of the kernel
- **Application Programs** - these include all programs not associated with the operation of the system

If we look at OS for mobile devices, we see that once again the number of features constituting the operating system is also increasing. Mobile OS often include not only a core kernel but also **middleware**—a set of software frameworks that provide additional services to application developers that supports databases, multimedia, and graphics (only a few).

#### In summary,
the operating system includes the always-running **kernel**, **middleware** frameworks that ease app development and provide features, and **system programs** that help in managing the system while it's running. 

## 1.2 Computer-System Organization
A modern computer system consists of one or more CPUs and a number of device controllers connected through a common **bus** that provides access between components and shared memory. 

Typically, OS' have a **device driver** for each device controller. This driver understands the device controller and provides the rest of the OS with a uniform interface to the device. 

The CPU and the device controllers can **execute in parallel**, competing for memory cycles. To ensure orderly access to the shared memory, a **memory controller** synchronizes access to the memory. 

### Interrupts
Consider an I/O operation:
1. The device driver loads the appropriate registers in the device controller
2. The device controller examines the contents of these registers to determine which action to take (read a character from keyboard for example)
3. The device controller starts the transfer of data from the device to its local buffer
4. Once complete, the device controller informs the device driver that it has finished its operation
5. The device driver then gives control to other parts of the OS, possibly returning the data or a pointer to the data (if the operation was a read)

For other operations, the device driver returns status info such as "write completed successfully" or "device busy".

*But how does the device controller inform the device driver that it has finished its operation?*
This is accomplished via an **interrupt**.

#### Overview on Interrupts
Hardware may trigger an interrupt at any time by sending a signal to the CPU, usually via system bus. 

Interrupts are used for many other purposes and are a key part of how OS and our hardware interact.

For example, when the CPU is interrupted, it stops what it's currently doing and immediately transfers execution to a fixed location. 
- This fixed location usually contains the starting address where the service routine for the interrupt is located.

The interrupt must transfer control to the appropriate interrupt service routine by invoking a generic routine to examine the interrupt information

