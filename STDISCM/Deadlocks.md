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
	- a resource can be released only voluntarily by the thread ho
4. Circular wait