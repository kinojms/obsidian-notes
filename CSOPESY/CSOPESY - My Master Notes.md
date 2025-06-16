# Intro to Operating Systems

## Computer System
Has three main components:
- Hardware - physical components and drivers
- OS - coordinates use of hardware with user applications
- Applications - typical apps used by a user

## Primary Tasks of an OS:
- serve as the bridge or API to hardware resources
- Resource Allocator - CPU and Memory allocation to an application. Decides how to share resources among other user programs
- Control Program - **controls behavior** of user programs to **avoid** **improper** use of computer resources (CPU and memory hoggers, programs with infinite loops, etc.)
- Security - helps protect the application's data from one another (prevents register mismatch, etc.)
- Improvisation - finds a way to improvise when hardware resources are scarce. Provides an illusion of dedicated machine with infinite memory and processors

### OS as an API to hardware resources
- How do we display something on-screen? 
	- display interfacing, screen buffers, refresh rates, etc.
- How do we access input devices?
	- `getch()`, `keyin()`, `std::in` API calls
- How do we access storage? How do we organize our files in storage?
	- fire directory systems implementation (Windows Explorer), user access permissions

### OS as a Resource Allocator
- programs are allocated
- memory address is decided by the OS
- each program has its own set of instructions
- each program and its corresponding line of instruction can be assigned to be executed on a logical processor
	- this heavily depends on the OS scheduling mechanism and CPU hardware design
### OS as a Control Program
- the OS ensures that **all applications** receive a **fair number of resources**
- each program has **components** where allocations are already **pre-defined**
- Components of a Program:
	- *Main Program* - points to the main function (10k)
	- *Subroutine* - contains all functions declared in code (20k)
	- *Libraries* - external functions or dependencies required (10k, 10k)
	- *Symbol table* - holds variables (30k)
	- *Stack* - holds temporary variables for function calls. Also stores the return address of a given function call (100k)
	- *Heap* - memory for dynamically allocated objects (100k)

	- Main Program to Symbol Table
		- usually defined during compile time. Hence, they have a fixed size
	- Heap and Stack
		- the sizes of both have limits, but are generally consumed during run-time. Hence, the heal or the stack may not use the allocated space completely
	- Stack Overflow Scenario: A faulty recursive function causes the stack to exceed its limit which returns the SO error
	- OutOfMemory Error: Excessive allocation of objects (continuously loading images) or unoptimized use of dynamic storages will exceed allocated heap space
	
- the OS pre-allocates memory on each application
- each application has a certain boundary on their components and overstepping these boundaries throw errors

### OS reinforcing Security
- each process has its own allocation and cannot be accessed by any other process
- if processes need to share information, each process must have instructions on writing/reading a shared file
- OS typically denies any malicious memory accesses
	- but some tools exists to circumvent this (Cheat Engines)

### OS for improvisation
- in memory management, all OS perform a technique called **virtual memory**, where the OS uses secondary storages (HDD/SDD) as main memory whenever RAM is used up
	- this gives the illusion of a very large main memory
- most OS employs Round Robin scheduling algorithms, giving all processes an equal amount of execution time per CPU cycle
- Windows 10 uses multi-level feedback queue scheduling (Round Robin with Priority Levels)

*Note: The OS is technically a process but has higher priority than most, if not all, processes*
# OS Emulator

## Typical Sequence of how an OS is loaded & run
1. Bootstrap:
	- perform low-level initialization (hardware setup, memory initialization, etc.)
	- load the kernel into memory and start executing it
	- ex: Perform hardware initialization
2. Kernel initialization:
	- initialize data structs (process table, file system, etc.)
	- set up interrupt handlers and device drivers
	- initialize memory management and scheduling algorithms
	- ex: initialize process table and memory manager (memory allocation algo, demand paging)
3. Start system services:
	- start essential system services (file system, networking, etc.)
	- Launch system daemons and background processes 
	- Example: Start file system service and network service o Observation: These are processes that are persistent in the OS – always alive/periodically invoking functions