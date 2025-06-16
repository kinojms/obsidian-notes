During a context switch, the OS **snapshots the current state of the CPU** and saves it into the Process—this is so that when each process regains control of the CPU, it will find the registers exactly as they were when they were interrupted.

**Context Switch** - a kernel routine; the action of capturing and restoring the current state of a Process so it can continue execution

This is how OS guaranteed **Security and Correctness** when sharing the CPU among multiple processes

When we switch Processes, we are **replacing the entire context** in which the OS operates

**Process Control Block** - a special structure that the Operating System uses to keep track of every single process
- a process has the following:
	- Unique ID
	- multiple states:
		- New
		- Running
		- Ready
		- Waiting
		- Terminated
	- Program Counter 
	- List of General Purpose Registers
	- Instruction Register
	- Flags
	- Stack Pointer (depends on hardware)
	- Index Registers (depends on hardware)
	- Memory Management information - includes the memory limits of each process' address space
- The **CPU State** of a process includes: **Program Counter to Index Registers**
	- this is where the captured CPU state is stored (snapshot)

The OS also keeps track of all the memory blocks allocated to each process using the Memory Management 

![[Pasted image 20250616164753.png]]
*Figure 1. Sample PCB Struct*

The PCB is NOT the Process itself but rather the representation of a Process. It serves as a repository for all the data needed to start or resume a Process, along with some extra info. 

This representation is what is actually placed in a queue.

This concept is applicable to single processor and multicore systems. The only difference is that multicore systems can operate with multiple contexts at the same time due to each core having its own execution pipeline. 

# Process vs Program