GPU-bound game - more parts of the game where it needs more GPU power than CPU

Splash screens serve as distractions for resources to load

Developers do other tricks to make OS more seamless like unskipable cutscenes

CPU and I/O burst work together—"salitan sila"

When entering a new phase of a software, there's a huge concentration of CPU resources to load in the resources for that phase

CPU clock - 

Boost Clock - can boost the CPU for a small amount of time, but it isn't sustainable
- Tau Boost Window - boosting CPU at its max performance but again, it's not sustainable. CPU overheats for prolonged boosting

Max Boost Clock is 5-6 Gigahertz

Skill effect - electrons hit the wire within a ... 

## Predicting length of Next CPU Burst
- can only estimate the length - should be similar to the previous one
- then pick process with shortest predicted CPU burst
- some devs try to predict the CPU burst they need via Khanban FIltering??
![[Pasted image 20250531083849.png]]
NOTE:
Ryzen Master can boost performance for AMD-based processors

## CPU Scheduler
- selects from among the process  in really queue, and allocates a CPU core to one of them
	- queue may be ordered in various ways
- CPU scheduling dmay take place when a process:
	1. switches from running to waiting state
	2. running to ready state
	3. waiting to ready
	4. terminates

## Preemtive and Nonpreemtive Scheduling
- inutusan ng nanay - preemptive (can be interrupted)
- taking an exam - nonpreemtive (cant stop once started)

C has 3 modes: read, write, append

## Race Conditions
Static threads can end up overwriting the outputs of another thread when threading isn't managed properly

## Dispatcher
- this module gives control of the CPU to the process selected by the CPU schedule; this involves:
	- switching context
- scheduler will try to as much as possible preserve processes inside a core

## Scheduling Criteria
- we don't want too much power consumption but WE NEED POWER—so we have to find a good balance
- Power Supply Efficiency - sometimes to get a few increases in performance, it would spike in power consumption (this is why most CPU's market 80-90 performance)
- Turnaround - from the time you're ready to execute to actually executing the process

# CPU Scheduling Algorithms
## FCFS - First Come, First Serve
- FIFO
- Run until done
- In early systems, FCFS meant one program scheduled until done
![[Pasted image 20250531081041.png]]

- P1 = 0 to 24 time units (time units is arbitrary—it doesn't mean anything)
- P2 = 3 time units
- P3 = 3 time units
- Throughput - what's the number of processes done after a given point in time
- Waiting time - how much time does processes wait before getting executed
- if we have 3 CPU cores and multiple processes, they can have 0 waiting times since they execute in different cores
- burst time is arbitrary

### Seatwork
![[Pasted image 20250531083422.png]]

| 0        | 1   | 2   | 3   | 4   | 5        | 6   | 7        | 8   | 9   | 10  | 11  | 12  | 13  | 14  | 15  | 16  | 17  | 18  | 19       | 20  | 21  | 22  |
| -------- | --- | --- | --- | --- | -------- | --- | -------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | -------- | --- | --- | --- |
| P1 Start |     |     |     |     | P2 start |     | P3 start |     |     |     |     |     |     |     |     |     |     |     | P4 start |     |     |     |

| Process | Arrival Time | Burst Time | Priority |
| ------- | ------------ | ---------- | -------- |
| P1      | 1            | 20         | 1        |
| P2      | 3            | 4          | 6        |
| P3      | 8            | 6          | 2        |
| P4      | 11           | 12         | 3        |
## Shortest-Job-First (SJF) Scheduling
- associate with each process the length of its next CPU burst
- use these lengths to schedule the process with the shortest time
- prioritize shorter/smaller tasks
- the goal is to finish a lot of things BUT it puts off a lot of big things down the line
- challenge is how to find out if a job is short
	- we could ask the user how long a task will take
	- or by estimate
- not to be confused with shortest remaining time first algo

![[Pasted image 20250531083829.png]]

## Shortest Remaining Time First
- preemtive version of SJN
- introduces the concept of Arrival Time
![[Pasted image 20250531083957.png]]

(Time Unit - Arrival Time Unit) then check which has the shortest burst time (P1 or P2), then insert that process in that time/block
- we only subtract the execute time
- if the given is NOT ordered, then order it by arrival time (Only for this algorithm)
	- for same arrival times, we sort it by process ID 

## Round Robin (RR)
- everybody gets to move forward given that everyone (for ex) has 5 time units to execute a process
- in RR we have a concept of Time Quantum Cube
	- its that time that everybody gets GUARANTEED time units
	- in theory its slower since it keeps context switching
		- in theory, this'll be alleviated if we have multiple CPU cores
- its okay to increase the Time Quantum if you know the dataset you're handling is big

![[Pasted image 20250531084930.png]]

Sample Computation
List first P1, P2, P3
Arrange them by order
Then subtract the Burst Time by each time unit per cycle

1st Loop:
The order is P1, P2, P3 
BT: 24, 3, 3

2nd Loop:
The order is P2, P3, P1
BT: 20, 3, 3

3rd Loop:
The order is P3, P1, P2
BT: 20, 0, 3

**NOTE**: It's possible for the CPU to be *idle* for a long time

## Priority Scheduling w/ Round Robin
- run the process with the highest priority. Processes with the same priority run round-robin
- for processes with the same priority level, 


