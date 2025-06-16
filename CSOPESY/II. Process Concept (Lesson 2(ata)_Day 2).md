# Process 
- an OS executes a variety of programs that run as a **process**
- **Process** - a program in execution; process execution must progress in sequential fashion. No parallel execution of instructions of a single process
- Has multiple parts:
	- Program Code - also called the text section
	- Current activity including **program counter**, processor registers
	- Stack containing temporary data
		- Function parameters, return addresses, local variables
	- Data section - contains global variables
	- Heap - containing memory dynamically allocated during run time

NOTE: Minimize the use of local variables cause they're expensive via memory

- Program is passive entity stored on disk (exe file)
	- It becomes a process when an executable file is loaded into memory
- Execution of program started via GUI mouse clicks, CLI entry of its name, etc.
- One program can be several processes—developers use threading to accomplish this
	- For example, multiple users executing the same 

## Memory Layout of a C Program
![[Pasted image 20250514075051.png]]

Memory binding happens at multiple stages: at compilation time, linking time, etc.

Ex: linked to memory address is fixed relative to the 0 in the memory

# Process State
![[Pasted image 20250514075410.png]]

When you execute a new process, it will be admitted to the "ready" queue

How can it manage running all processes happening at the "same time"?
- utilizes a ready queue, and these processes are scheduled, then they're ran

Interrupts
- error being thrown
- abruptly stops the process before it stops running

# Process Control 
- kinda like the index card system used by professors
- a tracker of the CPU or OS
- also called **task control block** (via the OS Book)

![[Pasted image 20250514075911.png]]

Time Quantum - how much time is allocated to a process

# Threads
- process has a single thread of execution
- consider having multiple program counters per process
	- Multiple locations can execute at once
- multiple threads of control -> threads
- must have storage for thread details, multiple program counters in PCB
- it's like a process within a process (?)

# Process Scheduling
![[Pasted image 20250514080213.png]]
NOTE: the goal of the OS is to **maximize** CPU use

Signals - higher level of interrupts

# Context Switch
- CPU switches from one process to another
- like how a person is interrupted mid-thought and they forgot what to do (just like me fr)

![[Pasted image 20250514080541.png]]

Ex: Save states in games saves a snapshot of the MEMORY then when it loads, it'll reload the snapshot of the memory state at the time

# Process Scheduling
![[Pasted image 20250514080819.png]]

# Multitasking in Mobile Systems
- easier in mobile cause only one application runs at a time, compared to a full desktop experience while multiple windows are open at the same time
- its tough to manage who gets to which resource (for desktops)
- easier but it

while suspended:
	stops fetching messages

# Process Creation

Similar to students ID number

Advantage of parents making child processes - shared resources (kinda like inheritance

Execution Process options 
- concurrently
- parents wait until their children fucking die

The child is a complete copy of the parent (so whatever the parent can do the child can too) OR it's a completely different program

# Process Termination

`return 0` 

Your program can be used by another program as good programming practice, we use `return 0`

Parents may `abort()` the execution of children processes because sometimes these children exceed allocated resources (this is usually the case why termination happens)

-- No parent waiting but isn't terminated, the process is a zombie—eats memory to execute its process but the output isn't used or is useless

-- Parent terminated without using `wait()`, process is an orphan

-- These will appear in the exams so brush up on these concepts (zombie, orphan processes)

To create a process there's a lot of things to initialize

Empty process - a process that doesn't have anything. takes over an existing process? (search this)

# Interprocess Communication (IPC)

Two types of sharing processes with another
- shared memory - faster but if there are multiple process writing to the same memory, its hard (one writer, many readers)
- message passing - u still have to pass through the networking stack

# WRAP UP
processes is an integral part of an OS

its a construct that allows OS to manage how shit executes on the CPU

The OS is in charge of the scheduling

NOTE: Alt + Tabbing sometimes freezes your game, this is cause of too many processes happening at the same time/loading a large amount of resources from foreground to ...

NOTE: Higher FPS = Full Screen; Lower Memory Consumption = Borderless Window















