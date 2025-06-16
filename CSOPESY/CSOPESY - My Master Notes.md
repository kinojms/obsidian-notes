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
- the OS ensures that all applications receive a fair number of resources
- each program has components where allocations are already pre-defined
- Components of a Program:
	- Main Program - points to the main function
	- Subroutine - contains all functions declared in code
	- Libraries - external functions or dependencies required
	- Symbol table - holds variables
	- Stack - holds temporary variables for function calls. Also stores the return address of a given function call
	- Heap - memory for dynamically allocated objects

	- Main Program to Symb