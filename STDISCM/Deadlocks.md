## System Model
- system consists of resources
- resource types are R1, R2, ..., Rm
- CPU cycles, memory space, I/O devices

Issue with locking, paunahan maglock tapos wala na, ginamit na ng isa ung resources

Deadlock Characterization Attributes <- this will show up in the exam
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

Resource Allocation Graph
- has vertices and edges (obviously)
![[Pasted image 20250916130653.png]]
- this will show up in the exam: "This is a resource allocation graph, describe it"
- T1, T2, T3 are threads. These are consumers of resources