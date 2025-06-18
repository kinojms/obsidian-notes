# Priority Inversion

Two processes sharing the same resource

P1 locks but is replaced with another process
- thus it doesn't unlock
	- the code under P1 doesn't end
- then P2 won't execute
- This is what we call a **Deadlock**

	Solution: Copy the process with the higher priority or just don't use Shared Memory

Deadlock Demonstration:
P3 (Prio 3) - locks

P2 (Prio 2) - arrives with higher prio

P3 (Prio 3) - doesn't unlock yet cause it got preempted with P2 

P1 (Prio 1) - arrives with higher prio

P2 (Prio 2) - doesn't end

# Multilevel Queue

Imagine in a single queue of multiple priorities, we instead, spread them into multiple queues by priority.

Ex:
Queue 1 (Prio 1)

Queue 2 (Prio 2)

Queue 3 (Prio 3)

If we have multiple queues, but only 1 CPU, we start from the **top**

# Multilevel Feedback Queue

Always only 1 input per queue

P1 (5) -> Queue 1 (TQ = 8) : Finishes @ Queue 1

P2 (9) -> Queue 1 (TQ = 8) -> P2 (1) -> Queue 2 (TQ = 16) : Finishes @ Queue 2

## Aging

Processes keep getting added

Very long processes take so long for them to finish

We introduce a concept called "aging"

Age - number of time cycles before a process (that hasn't ended) is entered back to the input

## Global Time Quantum

After a certain number of cycles, we return ALL processes IN THE READY QUEUE back to the input

Literally restart the WHOLE thing

Processes in the CPU stay there until their TQ is done