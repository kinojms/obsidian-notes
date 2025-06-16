# Intro to Operating Systems

## Computer System
Has three main components:
- Hardware - physical components and drivers
- OS - coordinates use of hardware with user applications
- Applications - typical apps used by a user

## Primary Tasks of an OS:
- serve as the bridge or API to hardware resources
- *Resource Allocator* - CPU and Memory allocation to an application. Decides how to share resources among other user programs
- *Control Program* - **controls behavior** of user programs to **avoid** **improper** use of computer resources (CPU and memory hoggers, programs with infinite loops, etc.)
- *Security* - helps protect the application's data from one another (prevents register mismatch, etc.)
- *Improvisation* - finds a way to improvise when hardware resources are scarce. Provides an illusion of dedicated machine with infinite memory and processors

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

	- **Main Program to Symbol Table**
		- usually defined during compile time. Hence, they have a fixed size
	- **Heap and Stack**
		- the sizes of both have limits, but are generally consumed during run-time. Hence, the heal or the stack may not use the allocated space completely
	- **Stack Overflow Scenario:** A faulty recursive function causes the stack to exceed its limit which returns the SO error
	- **OutOfMemory Error:** Excessive allocation of objects (continuously loading images) or unoptimized use of dynamic storages will exceed allocated heap space
	
- the OS **pre-allocates** memory on each application
- each application has a **certain boundary** on their components and **overstepping** these boundaries **throw errors**

### OS reinforcing Security
- kind of like encapsulation(?)
- each process has its own allocation and **cannot be accessed by any other process**
- if processes need to share information, each process must have instructions on writing/reading a shared file
- OS typically denies any malicious memory accesses
	- but some tools exists to circumvent this (Cheat Engines)

### OS for improvisation
- in memory management, all OS perform a technique called **virtual memory**, where the OS uses secondary storages (HDD/SDD) as main memory whenever RAM is used up
	- this gives the illusion of a very large main memory
- most OS employs **Round Robin** scheduling algorithms, giving all processes an equal amount of execution time per CPU cycle
- **Windows 10** uses multi-level feedback queue scheduling **(Round Robin with Priority Levels)**

*Note: The OS is technically a process but has higher priority than most, if not all, processes*
# OS Emulator

## Typical Sequence of how an OS is loaded & run
```
#include <iostream>

void bootstrap();
void initializeKernel();
void startSystemServices();
void enterMainLoop();
void shutdownAndCleanup();

int main() {

	// Step 1: Boostrapping
	bootstrap();

	// Step 2: Init Kernel
	initializeKernel();

	// Step 3: Start System Services
	startSystemServices();

	// Step 4: Enter Main Loop
	enterMainLoop();

	// Step 5: Shutdown & Cleanup
	shutdownAndCleanup();

}
```

1. *Bootstrap:*
	- perform low-level initialization (hardware setup, memory initialization, etc.)
	- load the kernel into memory and start executing it
	- ex: Perform hardware initialization
	- Chinese Supervisor wakes up and starts the factory
2. *Kernel initialization:*
	- initialize data structs (process table, file system, etc.)
	- set up interrupt handlers and device drivers
	- initialize memory management and scheduling algorithms
	- ex: initialize process table and memory manager (memory allocation algo, demand paging)
	- Supervisor sets up the equipment and production line
3. *Start system services:*
	- start essential system services (file system, networking, etc.)
	- Launch system daemons and background processes 
	- Example: Start file system service and network service 
	- Observation: These are processes that are persistent in the OS – always alive/periodically invoking functions
	- Supervisor wakes up the child laborers with their own respective tasks
4. *Enter main loop:*
	- continuously handle interrupts and system calls
	- dispatch user processes and manage their execution
	- handle user input and manage I/O operations
	- ex: enter an infinite loop to handle system events
	- Typical SHEIN factory working day 
5. *Shutdown and cleanup:*
	- gracefully terminate running processes and services
	- clean up allocated resources and release memory
	- halt or reboot the system
	- ex: clean up resources and prepare for shutdown
	- SHEIN factory dismissal time—terminates child laborers / puts them to sleep for the day, shuts down the assembly/production line, then eventually the factory

# Operating System Structures

## OS Services

![[Pasted image 20250616205835.png]]

### User Interface
- refers to the display interface and reading of peripheral inputs like the keyboard/mouse, touch screen, etc.
- early OS started with command-line interfaces (CLI), which uses text commands and keyboard for entering them—this is what our OS emulator will look like

- since we will be doing a command-line-interface style emulator, essential features are:
	- **Command Interpreter**
		- most OS treat the command interpreter as a **special program that is running when a process is initiated** or when a user first logs on (on interactive systems)
		- **Virtual Machines** (via Cloud) merely provides a Linux **shell** with Python and ML libraries **pre-installed**
		- developing a command interpreter requires processing of commands received from keyboard input
			- has a list of recognizable commands
			- tokenization of commands
	- System Calls
		- are libraries or interfaces developed that exposes services in an OS (ex: print functions, read/write of files, etc.)
		- also refers to system APIs
			- several Programming Languages have system APIs that are automatically included (print,/println class/object management, etc.)
	- 
