# OOP Principles
1. Encapsulation
	- wrapping data and information under a single unit
	- binding together the data and the functions that manipulate them together in a class
2. Abstraction
	- displaying only the essential information and ignoring the other details
3. Polymorphism
	- having many forms
	- the ability of an entity to behave differently in different scenarios
	- can be any of the three types:
		  1. Operator Overloading - making an operator exhibit different behaviors in different instances
		  2. Function Overloading - using a single function name to perform different types of tasks
		  3. Function Overriding - changing the behavior of a function that is derived from a base class using **inheritance**
4. Inheritance
	- the capability of a class to derive properties and characteristics from another class
		- Sub Class (Child) - inherits properties from another class
		- Super Class (Parent) - the class whose properties are inherited by a sub-class
	- supports the concept of **reusability**—when we want to create a new class and there is already a class that includes some of the code we want, we can let the new class **inherit** code from the existing class

https://www.geeksforgeeks.org/object-oriented-programming-in-cpp/#encapsulation

# Introduction to C++

Widely used in Game Development (Game Engines like Unity), Desktop Software, Database Systems, Embedded Systems, Compilers, and Virtual Machines

Why is it so popular? - C++ provides low-level memory and hardware control like C, but with high-level abstractions like **classes** and **smart pointers** 

"C++ makes it harder to shoot yourself in the foot, but when you do, it'll blow your whole leg off" - Fireship, 2022

# C++ Syntax

## Basic Functions (Headers, Print, and Strings)

`#include <iostream>` - enables the program to handle input and output

```
int main() {
	// codes here

	return 0;
}
```
-- Literally just like in C

`std::cout;` - the `printf` equivalent in C++

`std::cout << "Hello nigga"` 
- the `<<` serves as the assignment operator
- this line is equivalent to `printf("Hello nigga")`

-- We can remove the `std::` if we add a namespace `using namespace std;` at the top of the file

`sample_string[] = "I like men";` - a string variable typed as an array of characters (yes more bullshit)

-- But to make the usual string variables like in Java, we can add `#include <string>` so we can write a string variable like this instead: `string LeBron = "King James uooogh;"`

```
// Sample Starter Code
#include <iostream>
#include <string>

using namespace std;

int main() {
	string myNigga = "I love picking cotton!";

	cout << myNigga;

	return 0;
}
```
## OOP-related Syntax

-- By default attributes and methods (data and functions) defined within a class is **private** (Encapsulation)

-- We can make the properties of a class **public** via the following:
```
class Nigger {

	int nCotton; // this is private

	public: // anything under this is public
		string niggaName;
		
		void pickCotton() {
			bendOver()
			cout << "Picking Cottons..."
		}

}
```

-- It's also possible to define methods outside of classes using a double colon
```
void SlaveTrader::whip() {
	cout << "GET BACK TO WORK!!"
}
```

-- Overloading - using the same function name but changing the parameters
```
class Nigger {

	int nCotton; // this is private

	public: // anything under this is public
		string niggaName;
		
		void pickCotton(int pickSpeed) {
			bendOver()
			cout << "Picking Cottons..."
		}
		
		void pickCotton(float pickSpeed) {
			bendOver()
			cout << "Picking Cottons..."
		}

}
```

-- Constructors and Destructors - to run code when an object is created or destroyed
```
class Nigger {

	int nCotton; // this is private

	public: // anything under this is public

		Nigger() {
			// constructor
		}

		~Nigger() {
			// destructors
		}

}
```

-- Inheritance - reuse code from existing classes
```
class Nigger {

}

class LilNigga: public Nigger {
	public:

		void pickCotton() { // from the parent class Nigger
		
		}
}
```

-- Instantiating an object and memory management
```
int main() {

	Nigger jamal; // className objName

	Nigger* myPointer = new Nigger; // pointers

	delete myPointer; // deallocate memory
	
	return 0;
}
```

-- Unique Pointers - easier and safer way to manage memory—by  ensuring that only one object can be allocated to memory
```
unique_ptr<Nigger> ptrJamal(new Nigger);:
```

## Running your C++ Program

-- Compiling the code
```
clang++ filename.cpp
```

-- Running the code
```
filename.exe
```


