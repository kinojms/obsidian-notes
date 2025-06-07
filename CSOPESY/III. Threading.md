**Marquee Console Tips**
- Start from top
- 45 degree angle direction
- Use this to practice dealing with your refresh rate
- Refresh rate/Polling rate
- How much are you refreshing your screen and polling your input buffers
- Tune your refresh rate depending on your computer

**Steps**
1. Get size of the whole window
2. Get size of the particular region up to the input section
3. Start computing the coordinates of "H" and "!"—these are your bumpers
	- Getting "H" first is important—(base offset) get its coordinate first then you'll be able to get the rest of the string
4. Make Two Major Threads for handling:
	1. Refreshing of screen
	2. Polling of input

**Common Mistakes:**
	Screen Tearing - makes 2 lines of full text; caused by
	Ghosting - trail of letters
	Typing is Lagging/Doubling - one of the letters will be swapped in terms of order, etc.

# Threading
- "multithreaded" - uses multiple threads in terms of execution
- threads run within applications
- Google Chrome is a good example—it allows us to have multiple tasks
- Mobile Apps usually have one main thread (for UI)—but background threads are created for other tasks
- Process Control block - 
- Threading allows for simplifying code and increasing efficiency by utilizing more CPU cores—we're maximizing our computer's resources
- depending on the design, we can create a threadpool worker model with one piece of code where multiple threads fire off the same logic

## Single Threaded vs Multithreaded Processes
- shared data between parent thread to child thread
	- able to share through references
	
- main thread: opening files, loading dataset, etc.
- child threads: divide the workload to each thread

## Benefit of Threading
- responsiveness
- resource sharing
	- its like "uy pasabay nalang!"
	- its piggybacking off an existing process already
- economy
- scalability

ARM Big Little Architecture
- per CPU core has one large, one little core

# Multicore Programming
- the pressure is with the developers
- these are the challenges
- multicore or multiprocessor systems puts pressure on programmers, challenges include:
	- dividing activities
	- balance
	- data splitting
	- data dependency
		- like waiting on your grpmate to finish their part before you do yours
	- testing and debugging
		- its harder to debug threads
- Parallelism implies a system can perform more than one task simultaneously
- Concurrency supports more than one task making progress
	- Single processor/core, scheduler providing concurrency
	- one CPU core but two processes, you interleave between both processes—switching back and forth basically
## Concurrency vs Parallelism
![[Pasted image 20250528081556.png]]

## Types of Parallelism
- data parallelism - distributes subsets of the same data across multiple cores, same operation on each
	- subdivide the data
- task parallelism - distributes threads across cores, each thread performing unique operation
	- same data but different tasks are being done on it at the same time

CPU have faster refresh rate than GPUs, but GPUs have significantly more cores than CPU—thus, GPUs can do more tasks 

## Amdahl's Law (in Exam)
- used to predict the speedup you would achieve when you convert your software to something parallel
![[Pasted image 20250528082325.png]]
- software can be divided into two parts:
	- parallelizable f- parts that can be offloaded into multiple threads (initialization and are fixed)
	- serial s - 
	- the more you make it parallel, we make the whole time shorter

## User Threads and Kernel Threads
- User threads - management done by user-level threads library
- User space - threads we interact with
- Kernel space - background threads

# Multithreading Models
## Many to One
- many user-level threads mapped to a single kernel thread
- one thread blocking causes all to block
- ex: GPU running multiple games—the GPU can only efficiently handle one process at a time
## One to One
- each user-level thread maps to kernel thread
- creating a user-level thread creates a kernel thread
## Many to Many
- many user-level threads can map to multiple kernel threads
## Two level Model
- similar to M:M 
- one thread is exclusive for graphics while the other threads are for game logic and other stuff

Hardware Acceleration - to maximize CPU

For console applications we use `<windows.h>`
