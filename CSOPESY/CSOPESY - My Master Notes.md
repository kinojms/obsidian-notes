# Intro to Operating Systems

## Computer System
Has three main components:
- Hardware - physical components and drivers
- OS - coordinates use of hardware with user applications
- Applications - typical apps used by a user

Primary Tasks of an OS:
- serve as the bridge or API to hardware resources
- Resource Allocator - CPU and Memory allocation to an application. Decides how to share resources among other user programs
- Control Program - **controls behavior** of user programs to **avoid** **improper** use of computer resources (CPU and memory hoggers, programs with infinite loops, etc.)
- Security - helps protect the application's data from one another (prevents register mismatch, etc.)
- Improvisation - finds a way to improvise when hardware resources are scarce. Provides an i