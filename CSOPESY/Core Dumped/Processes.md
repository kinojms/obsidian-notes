During a context switch, the OS snapshots the current state of the CPU and saves it into the Process—this is so that each the process regains control of the CPU it will find the registers exactly as they were when they were interrupted.

 Context Switch - a kernel routine; the action of capturing and restoring the current state of a Process so it can continue execution

This is how OS guaranteed Security and Correctness when sharing the CPU among multiple processes

When we switch Processes, we are replacing the entire context in which the OS operates

Process Control Block - a special structure that the Operating System uses to keep track of every single process
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
- The CPU State of a process includes: Program Counter to Flags
	- this is where the data (snapshot) of a 

