# CSOPESY MO1 Requirements

Reading config file

`screen -s <process name>` functionality
- creates a process

`report-util` functionality
- CPU utilization report
- dummy values

`screen -r <process name>`
- views that specific process' log files
- switch to a new screen

## Barebones Process Instructions

`DECLARE(var, value)`
- declares an int16 with variable name "var", and a default "value"
- makes a variable with an int value

`PRINT(msg)`
- dictates what will be displayed when called
- literally prints out a "msg"
- if no print msg is given, a default value message of "Hello world from (process name) " is set instead 

`SLEEP(x)`
- force sleep that process for "x" amount of time
- set the thread::sleep_for value to x

`ADD(var1, var2/value, var3/value)`
- first param should always be a variable
	- if the variable wasn't declared beforehand, it's default value is 0
- performs an addition operation
- all variables are 0 by default
	- if you didn't declare `var1` beforehand, then it'll be 0 + var2 + var3
	- kind of like assembly instructions

`SUB(var1, var2/value, var3/value)`
-  first param should always be a variable
	- if the variable wasn't declared beforehand, it's default value is 0
- performs an addition operation
- all variables are 0 by default
	- if you didn't declare `var1` beforehand, then it'll be 0 + var2 + var3
	- kind of like assembly instructions

`FOR([instructions], repeats)`
- has its own instruction queue 
- instructions in the queue are randomized at the moment FOR is initialized
	- ex: Generating a random FOR instruction
	- FOR([ADD,SUB,ADD], 3)
- the implementation of this instruction's function will have its own queue which it loads in random instructions as well

# Currently Done Features

1. Config file is done and can be read by the program
2. Barebones implementation of instructions
	- They are not being called anywhere in the program except for `PRINT`
	- Currently testing out if the other instructions are functioning properly
3. Unordered Map of instructions is implemented
	- Used for randomization of instructions per process
		- 1 - PRINT
		- 2 - DECLARE
		- 3 - ADD
		- etc.
NOTE: The instructions are just barebones. They don't receive any kind of input from anywhere (as parameters) 

# TODOs
1. Generate random instructions when a process is created (random number of instructions from range `min ins` to `max ins`)
	- What's done: 
		- Processes can now be created with a random number of assorted instructions 
	- Explanation:
		- these instructions are ENQUEUED or pushed into a queue within the process for it to execute
	- TODO: 
		- For instructions DECLARE, ADD, SUB: there should be a way to randomly generate their arguments/parameters upon being created/pushed into the queue
		- For the FOR instruction: figure out a way to limit nested `FOR` instruction to 3
			- `FOR` instruction will have its own set of random instructions so this will also use the same function for generating random instructions
			- however, it should have a way to keep track of how deep you are in the nested FOR loop so it doesn't exceed past 3 nests
2. `process -s <process name>` functionality
	- a function to create a process
	- calls the instruction generator
	- adds this newly created process to the ready queue
3. `screen -r <process name>` functionality
	- figure out a way to switch screens


 TODO II 
 1. "batch-process-freq" in `config.txt` should determine how many processes are generated /  
 2. don't make 10 process off the bat when starting the scheduler /
 3. the scheduler should create processes by itself /
 4. fix the low cpu core and min ins/max ins scheduler start and stop issue
 5. add a logger for FOR instructions that were randomly generated /
 6. simplify process -s (process name) on screen switch information /
	- refrain from info dumping
	- only include the process name, process ID, core its assigned to, timestamp at the moment the screen switches
	- display the Logs only after entering "process-smi"
7. double check RR implementation /

# TC 4
Perform the following changes to the emulator:
1. A process created will always have a variable "x" in its symbol table with a value of 0
2. Instructions generated will always be an alternating PRINT("Value from: " + x) and an ADD(x, x, [1-10])—randomize ADD operation between 1 to 10
ex: If there will be X instructions per process, it must always be of the set [PRINT, ADD, PRINT, ADD, ...] and so on.

The parameters for your "config.txt" should be:
num-cpu 1
scheduler "rr"
quantum-cycles 20
batch-process-freq 1
min-ins 100000
max-ins 100000
delay-per-exec 0

Create the following processes via "screen -s" commands:
- proc-01

Upload a video that shows the following in sequence:
1. Create the processes using the "screen -s" command.
2. Type the "screen -ls" command.
3. View "proc-01" execution via "screen -r" command.
4. Wait for 15 seconds.
5. Type "exit" in the screen, and "exit" in the main menu.
6. Close the program and run it again. Repeat #1 - #5.

# TC 5
1. Type the "scheduler-test" command.
2. Wait for 10 seconds
3. Type the "scheduler-stop" command.
4. Wait for 30 seconds.
5. Type the "screen-ls" command.

# TC 3
num-cpu 4
scheduler "rr"
quantum-cycles 5
batch-process-freq 1
min-ins 1000
max-ins 2000
delay-per-exec 0

Upload a video that shows the following in sequence:
1. Execute "scheduler-start" command.
2. Wait for 5 seconds.
3. Type the "screen-ls" command.

**Expected output:** It should show a 100% CPU utilization printed in the screen-ls command and mostly running processes.

# TC 6
![[Pasted image 20250628220200.png]]

# TC 7
![[Pasted image 20250628220311.png]]

