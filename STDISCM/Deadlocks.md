## System Model
- system consists of resources
- resource types are R1, R2, ..., Rm
- CPU cycles, memory space, I/O devices

Issue with locking: paunahan maglock tapos wala na, ginamit na ng isa ung resources

## Deadlock Characterization Attributes <- this will show up in the exam
1. Mutual exclusion
	- only one thread at a time can use a resource
2. Hold and wait
	- a thread holding at least one resource is waiting to acquire additional resources help by other threads
3. No preemption
	- a resource can be released only voluntarily by the thread holding it, after that thread has completed its task
	- voluntary releasing of resources being consumed
4. Circular wait
	- waiting on someone else to move while they're also waiting for you to move 
	- Mexican standoff
	- "sasama ako if sasama sya"
	- mutual dependency on one another

## Resource Allocation Graph
- has vertices and edges (obviously)
![[Pasted image 20250916130810.png]]
- this will show up in the exam: "This is a resource allocation graph, describe it"
	- "Resource 2 is assigned to Thread 1 and Thread 2"
	- "Is this graph a deadlock? True or False"
	- "Articulate why is there a deadlock?"
- T1, T2, T3 are threads. These are consumers of resources
- Arrow coming out of resources means it's assigned to a Thread
- Arrow coming out of the threads = resources being demanded(?)
![[Pasted image 20250916131135.png]]
- this has a circular wait
- but since T2 and T4 are independent (can operate immediately), it breaks the Hold & Wait characteristic, thus resulting in a Non-Deadlock scenario

# Handling Deadlocks
- ensure that the system will **never** enter a deadlock state:
	- prevention
	- avoidance
		- pretend the deadlock never happened
- allow the system to enter a deadlock state and then recover
- ignore the problem and pretend that deadlocks never occur in the system

## Deadlock Prevention
- invalidate one of the four necessary conditions for deadlock:
	- Mutual Exclusion - not required for sharable resources; must hold for non-sharable resources
	- Hold and Wait - must guarantee that whenever a thread requests a resource, it does not hold any other resources
		- Definition: if a process wants to execute more, it'll try to access more resources without release already held resources
		- require threads to request and allocate all its resources before it begins execution or allow threads to request resources only when the thread has none allocated to it
		- **Low resource utilization; starvation possible**
		- in a Try/Catch block, use a Finally block to release held resources
	- Infinite resources
		- have an abundance of resources that no one runs out
		- does not have to be infinite, just large to be more than enough
		- "infinite" is a bit of a stretch—since in CS, "infinite" just means "very big" or "a lot"
	- No sharing of resources
	- Do not allow waiting
		- phone line - busy
			- calling someone who's already talking to someone else
			- since you heard the busy tone, you can drop the call for now then try again later
		- ethernet/WiFi - on collision, back off
		- inefficient due to retry attempts
	- No preemption:
		- if a process that is holding some resources requests another resource that cannot be immediately allocated to it, then all resources currently being held are released
		- inefficient and very niche
	- Circular wait
		- impose a total ordering of all resource types, and require that each thread requests resources in an increasing order of enumeration
		- borderline banker's algorithm
		- won't show up in the exam (hopefully)
## Deadlock Avoidance
- assumes a priori information available
	- simplest and most useful model requires that each thread declares the maximum number of resources of each type that it may need
	- the deadlock-avoidance algorithm dynamically examines the resource-allocation state to ensure that there can never be a circular-wait condition
	- resource-allocation state is defined by the number of available and allocated resources, and the maximum demands 