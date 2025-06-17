# Interprocess Communication (IPC) 
Facilitated by the OS

Cooperating process - shares data with other processes
- enables computational speedup
- allows for modularity

Independent - never interacts with another process

Computation speedup - your program can spawn multiple processes to speed up the thing

Modularity - especially in Linux, a program should only do one thing (specialized) so we make a separate process/program if we wanna do something else

Convenience

## Shared memory
- allows memory space to be shared directly
- kind of hard to do this
- can only be written by one process at a time
- dev has to implement some kind of process synchronization
- depends on your compiler
- this is NOT shared register
	- diff processes have diff registers
	- for loops iterating `i` basically just gets the `i` refreshed/updated not the register
- VERY FAST
## Message passing
- both process (A and B) instead of sharing a variable, they pass messages instead—also facilitated by the OS
- any message passing becomes a producer-consumer problem
	- Ex: instructor produces modules, HWs; consumer does them
	- Ex: producer process makes info that is consumed by a consumer process
### Producer-Consumer Problem

Two variations
- difference is whether the producer waits or not

unbounded:
- producer never waits

bounded:
- producer must wait till all consumers are full

### Full Buffer
- just doing a counting of how much data you have in your allocated buffer
	- typically we have a counter for this
	- if there is something in your buffer, we add, etc.
- the issue with this is the possibility of a Race condition
	- for example: counter++ is not yet done but its quantum cycle is over. so it'll abruptly stop
	- there synchronization mechanisms for this

## Message Passing
- it's just like throwing data
	- much like packet passing in CSNETWK
- Person A has to get Person B's attention first before they pass messages
	- Note: Chrome spawns multiple threads just to load a single website
- unidirectional - one way flow of interaction
- bi-directional - uses a feedback loop so sender also receives replies

## Implementation of Communication Link

Physical:
- shared memory
- hardware bus
- network
Logical:
- direct or indirect
- synchronous or asynchronous
- automatic or explicit buffering

### Direction communication
- its a communication perspective wherein we have to explicitly talk to each other
- send(P, message) - we are sending something to P
- receive(Q, message) - P will reply to Q acknowledging that they will establish a connection
- exactly one link
- the link MAY be unidirectional, but is USUALLY bi-directional

### Indirect Communication
- there's a concept of a mailbox
- sender and receiver doesn't need to lock themselves out
- in a Venn diagram, the common between two processes that want to communicate with each other will be the mailbox
- depends if uni or bi-directional

Operations:
- create a new mailbox
- send and receive messages thru mailbox
- delete a mailbox

## Synchronization

- Blocking is considered synchronous (Direct)
	- blocking send 
		- ex: when checking attendance, if sir calls my name, he's not calling other people
	- blocking receive
		- ex: like a phone call, technically sir is blocked until he's available to receive messages
- Non-blocking is considered asynchronous (Indirect)

## Buffering

- ex: you're connected to YT and its buffering. we are downloading frames to your buffer and its usually implemented in a queue

1. Zero capacity - ex in verbal comm—if u wanna talk to me and I'm not listening to you, there's no buffer to store your info. so we need to rendezvous/get my attention for that.
2. Bounded capacity
	- there's a limited amount of messages that one can receive
3. Unbounded capacity
	- sender never waits
	- keep on sending messages
	- unlimited(?) capacity—its just something that's very big (not really unlimited)

## Windows

- LPC - functions are available in a different process. like calling a function (that doesn't exist on your process) to a different process

### Pipes
- acts as a conduit allowing two processes to communicate
- Has two holes, one on each end
- Is an exclusive communication channel between two processes only

#### Ordinary Pipes
- allows communication in standard producer-consumer style
- usually unidirectional—allows communication between parent-child
- however, they don't communicate at the same time 

#### Named Pipes
- fixes the unidirectional issue
- its now bidirectional
- several processes can use the named pipe for communication
- usually multiple types: TCP, UDP, MulticastSocket - data can be sent to multiple recipients
	- Note: UPNP - universal plug n play

## Remote Procedure Calls (RPC)
- mostly Windows
- we're gonna use Google RPC in DISCCM
- calling a function in a different computer
- make sure if two systems are communicating and one is bigger than the other, we have to account for this difference in architecture as well (but usually packages already deal with this for you)

## Socket
- a pair of IP address and port numbers
- an endpoint for communication
- 