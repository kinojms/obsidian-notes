# Dynamic Linking
## Static Linking
system libraries and program code combined by the header into the binary program image
// discontinued


instructions in processes is assigned to a memory address(?)
memory address is pre-defined during compile time  

Fetch - iterate over instructions and assign a page to it
Load - during load time, the 
Compile - checks and adjusts for system compatibility
Execution - `.dll` 

An instruction gets a memory address during execution/run time

OS also crams to maintain compatibility

# Logical and Physical Address Space
Logical - virtual address
- allows the OS to put the address that is beyond the size of the memory
- to address BEYOND the capacity of your RAM
- Elden Ring is 50+ GB, but NOT ALL functions are being loaded all the time and at the same time

Backing store - where processes are placed when your program hasn't reached this point when it's needed
- until that function is needed, it's placed in the backing store
- it can be assigned a memory, but not placed in the physical memory unless needed
- kind of like a waiting room

Logical and Physical is an offset of FF (hex value of logical address)
ex:
physical address is at 00
logical address is at FF
we can say that the process is in 00 but with an offset of FF (or simply 00 + FF)

# Dynamic Loading
- the entire program doesn't need to be in memory to execute
- routine is not loaded until it is called
- better memory space utilization: unused routine is never loaded

# Contiguous Allocation
- main memory must support both OS and user processes
- limited resource, must allocate efficiently
- contiguous allocation is one early method
- amin memory usually into two partitions:
	- resident OS, usually help in low memory with interrupt vector
	- user processes then held in high memory
	- each process contained in single contiguous section of memory
# Per Tick Workflow for MO1
- runs in scheduler
- now OS will decide which instruction to execute (find instruction)
- find which memory address this instruction its assigned to
- read what's inside of the memory (the actual code is inside the memory)
- execute
Note: Don't use `.txt` files; you won't know what the code is unless you read the memory

# Dynamic Storage-Allocation Problem
ERD Diagram


# Fragmentation
- reduce external fragmentation by compaction
- shuffle memory contents to place all free memory together in one large block