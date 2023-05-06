# Linux Architecture

## Components of [[Linux]] Systems
The Linux operating system has three components
### Kernel
The kernel is the core part of Linux. It is responsible for the major activities of the operating system. It consists of various modules and it interacts directly with the underlying hardware. The kernel provides the required abstraction to hide low level hardware details to system or application programs

### System Library
System libraries are special functions or programs that allow application programs or system utilities to access the kernel's features. They implement most of the functionalities of the OS and do not require the kernel's code access rights.

### System Utilities
These are responsible for doing specialised, individual level tasks


## Kernel Mode vs User Mode
Kernel component code is executed in a privileged mode called *kernel mode* which has full access to all resources of the computer. This code represents a single process, executes in a single address space and does not require any context switching so therefore is very efficient and fast.

## Basic Features
These are some of the important features of the Linux OS:

### Portable
Portability means software can work on different types of hardware in the same way. Linux can be installed almost anywhere

### Open Source
The source code for Linux is freely available and contributed to by a community.

### Multi-user
Multiple users can access system resources like memory/RAM/programs, etc. at the same time

### Multiprogramming
Multiple applications can run at the same time

### Hierarchical File System
There is a standard file structure that is like a tree

### Shell
Linux provides an interpreter program that can be used to execute commands for the OS

### Security
Linux has security features like password protection, file access control, data encryption, etc.
