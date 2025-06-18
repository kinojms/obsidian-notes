# OS Structure
Monolithic
- one of the oldest approaches
- the entire OS runs as a single programming mode
- all OS services are coupled in a single large kernel
- all hardware interaction, syscall, I/O operation, happens in a single address space
- Pros: efficient performance due to minimal overhead and communication between components
- Cons: any bug in one part of the system can potentially crash the entire OS
Layered
- organizes the OS into a hierarchy of layers with each layer building on the services provided by lower layers
- the key idea is to separate OS functionality into distinct layers
- Pros: makes it modular and easier to debug
- Cons: can become too complex
Microkernel
- takes modularity to the next level
- the OS is divided into a small core kernel that provides the most basic functions
- while other services run as separate processes
- Pros: improves flexibility and makes the system easier to extend
- Cons: can introduce performance overhead due to increased IPC (inter process communication)
- addresses some issues from Monolithic but has its own trade offs
Modular
- combines some aspects of Monolithic and Microkernel
- the kernel is composed of modules that can be dynamically loaded and unloaded as needed
- Pros: provides flexibility (Microkernel) while maintaining the performance benefits of Monolithic systems
- Linux uses this design

# OS Operations
Multiprogramming
- a chef (CPU) preparing multiple dishes (programs) simultaneously 
Multitasking
- gives the illusion of multiple programs running at the same time
- like how a juggler keeps multiple balls in the air
Dual-mode Operation
- has two levels of access
	- User mode - has restrictions and limited access
	- Kernel mode - system has full access and privileged access
- system calls allow system to switch between these two modes
	- if the user programs wants to do a privileged action like accessing a hardware or creating a new process, we perform a syscall—a request to the OS to perform this action on their behalf
	- after making the syscall, the system switches to kernel mode, performs the requested operation, and switches back to user mode
Timer Interrupts
- crucial for maintaining control of the CPU
- like an alarm clock for the OS
- at regular intervals, the timer generates an interrupt
- this switches the system to kernel mode—preventing any single program from hogging the CPU indefinitely and allows the OS to make scheduling decisions 
I/O Handling
- when a program needs to perform an I/O, it does a syscall
- the OS then takes over and manages the interaction with the hardware
- ex: reading/writing to a disk, interacting with peripherals
- this can optimize performance and ensure security