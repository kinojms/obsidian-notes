![[Pasted image 20250613164204.png]]

Tasks:
1. Implement a FCFS scheduler using a multi-threaded approach 
	- 1 thread for scheduler
	- 1 thread per CPU (maybe make a cpu core class??)
2. "print" command
	- each process creates a text file where all its print commands are written
		- timestamp included
	- if there are 10 processes, there should be 10 text files created
3. 4 cores for the CPU scheduler

Test Case:
1. Create 10 processes, each with 100 print commands, upon the start of your OS emulator.
2. Periodically type the "screen -ls" command every 1 - 2 seconds until all processes are shown in the "finished processes" list.
3. Type "exit" to close your emulator.

**EXPECTED RESULT:** Your emulator should finish all processes in a first-come-first-serve sequence and produce 10 text files containing its associated print statements.

# MP Changelogs

Main.cpp 
- has a function that receives string initializer set to notinitialized 

consoleLayout.cpp 
- No longer has any display elements 
- Connects to various functions via the Functions.cpp and gFunctions.cpp 
- Creates processes via Process.cpp 
- NEW properly identifies -r and -s inputs
- ISSUE -s defaults to creating a new process if command doesn't exist 

Process.cpp 
- ISSUE: not sure how to properly make ProcessInfo a class without breaking the entire thing 
- Explanation:
	- createProcess - makes process via taking an input of string from consoleLayout(if there is no command that matches from -s) 
	- displayProcessInfo - looks for and shows processes made via screen -r 
	- ISSUE: displayAllProcessInfo - used to work but now cannot find any created processes even though displayProcessInfo works 
	- formatTimestamp- formats timestamps 

gFunctions.cpp 
- Houses general functions that are useful across the board 
- Explanation 
	- clearScreen - clears screen 
	- gotoxy - uses windows console functions to go to a specific x and y coordinate on the CMD 
	- clearLine - clears specific x coordinate lines 
Functions.cpp 
- Houses the specific function calls for screen scheduler-test etc. 

Display.cpp
- Has all the output couts we have including my individual dummy Nivada CLI XD 

Windows_console_minimal.h
- Has some of the functions in windows.h had to make it since windows.h and one of our .h files hate each other leading to a byte not defined scenario (best not to touch i also dont fully get it)

# New Code Structure

## Main
- calls the MainConsole class for the main program loop

## Display Class
- for print related 

## General Console class
- where general functions for each console will be inherited by other classes
- methods include:
	- receive_input() - gets user input
	- process_command() - executes the command based on user input
	- initialize() - print statements or things that run upon 

## Main Console class
- start of the program

## Process Console class
- switch to this console when `screen -r <process name>` is called
- displays the information of a specific process

## ConsoleManager class
- this is where switching of console/screens are handled
- the controller/manager for consoles
	- has sub-consoles

# Main
- creates an instance of console manager which runs the program

# ConsoleManager
- responsible for managing the consoles used in the program
- depending on what's needed, we want to switch to either the Main Console or Process Console
	- Main Console - the main menu screen
	- Process Console - the screen for displaying specific process information
- console instances are stored within an unordered_map named "ConsoleTable" of type String which also inherits the class `AConsole`
	- 
# AConsole (Parent Class)
- AConsole has the following methods:
	- initialize() - start of program; displays ascii art and other visual stuff
	- print_response() - displays the appropriate response to commands (ex: "Command accepted. Executing...")
	- process_command() - receives user input and executes the said command
## Main Console
- the main menu
- where mostly all interactions with the program are done
- commands include:
	- `initialize` - initializes the whole program (nothing will happen unless you enter this first)
	- `scheduler-start` - does nothing yet (for this current version)—simply returns a text "X command recognized. Doing something..."
	- `scheduler-stop` - does nothing yet (for this current version)—simply returns a text "X command recognized. Doing something..."
	- `report-util` - creates a log.txt file of the 

## Process Console

# Scheduler (Parent Class)
## FCFS Scheduler Class
- utility functions:
	- adds process to the scheduler
	- sort the process queue
- function to use the utilities and run the scheduler
Use this as reference only—don't copy
![[Pasted image 20250614013150.png]]


# Code Explanation
To make it simple, here's an analogy:
Process = Jobs
CPUCores = Workers
Scheduler = Manager
Functions = Supervisor

## Process.cpp (Job)
- is a "job" with a unique id (`pid`) and a list of instructions (100 print statements)
- when a "worker" (CPU Core) gets a "job" (Process), it runs the `execute()` method, which writes messages to a `.txt` file and marks itself as finished when done.

## CPUCore.cpp (Worker)
- each CPU Core is a "worker" with a unique id
- when the "manager" (Scheduler) assigns a job (Process), the worker (CPU Core) starts a new thread to run the Process' `execute()` method. (`void Process:execute()`)

## Scheduler.cpp (Manager)
- this keeps a queue of jobs (Processes) and a list of workers (CPU cores)
- it loops to check for any free workers (CPU cores)
- if a worker (CPU Core) is free and there's a job (Process) waiting to be done, it gives the oldest job (the first one in the queue) to that worker
- this reflects the FCFS—processes are executed based on their arrival time
- the manager keeps checking and assigning until all jobs (Process) are done and workers (CPU Core) are idle 

## Functions.cpp (Supervisor)
- sets up/initializes the manager and workers, creates the jobs, and starts the scheduling process using `screen -s scheduler-start`
- lets you check the current status of all jobs (Processes) using the command `screen -ls` 

### Note: 
The `.txt` files are stored in the solution's folder.

If you cloned my branch, you navigate through it like this: `OS_emulator/CSOPESY MP/<processes are saved here>`

I'll try and make a folder for this tomorrow and save the text files there instead.

### Working Commands:
```
initialize
screen -s scheduler-start // starts the scheduler
screen -s scheduler-stop // stops the scheduler
screen -ls // views the queue (current and finished processes)
```

### Big Issue: 
1. Lost `screen -r` functionality.  
	- I plan on making multiple Console classes for this (Main Console and Process Console) also use a ConsoleManager to switch between these two screens
2. Lost `screen -s <process name>` functionality.
	- will reimplement this after the deadline lmao

# TODOs
Modify the Process and Scheduler classes

Process class
- should have arrival time(?)

Scheduler class
- should have a "ready" queue
