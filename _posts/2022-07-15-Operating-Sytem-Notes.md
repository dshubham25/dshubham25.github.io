---
layout: post
title: Operating System Notes
category: Core Subjects
excerpt: Guide on hosting a Jekyll site with custom domain on Github Pages.
redirect_from: /2022/07/15/Operating-System-Notes/
---

In this blog I will write all about Operating Sytem that is frequently asked in an interview.

### What is Operating System?

- An operating system that acts between the user and the computer hardware.
- The purpose of an OS is to provide a convenient environment for the users.
- It is also a resource allocator which is responsible for allocating system resources and a control program which controls the operations of the computer hardware.

### What is Kernal

Kernel is the core of the operating system. It connects applications to the actual processing of the data. It also manages all the communications between software and hardware components to ensure usability and reliability.

#### Types of Kernels

- Monolithic Kernel: : In this type of Kernel, all the User services and kernel services reside in the same memory space. The old operating system would use this type of Kernel. Some examples are Linux, Windows 95, 98, Unix, etc.

- Micro Kernel: This type of Kernel is small in size, and all the User and Kernel services reside in the different memory addresses. Operating systems like Mac OS X, windows use this type of Kernel.

### Daemon

Disk and execution monitor, is a process that runs in the background without user’s interaction. They usually start at the booting time and terminate when the system is shut down compaction

### Define User mode and Kernel mode.

- User mode: The system is in user mode when the operating system is running a user application such as handling a text editor. The transition from user mode to kernel mode occurs when the application requests the help of the operating system or an interrupt or a system call occurs.

The mode bit is set to 1 in the user mode. It is changed from 1 to 0 when switching from user
mode to kernel mode.

- Kernel mode: The system starts in kernel mode when it boots and after the operating system is loaded, it executes applications in user mode. There are some privileged instructions that can only be executed in kernel mode.
These are interrupt instructions, input output management etc. If the privileged instructions are executed in user mode, it is illegal and a trap is generated.

The mode bit is set to 0 in the kernel mode. It is changed from 0 to 1 when switching from
kernel mode to user mode.

#### Necessity of Dual Mode

The lack of a dual mode i.e user mode and kernel mode in an operating system can cause serious problems. Some of these are:
- A running user program can accidentally wipe out the operating system by overwriting it with user data.
- Multiple processes can write in the same system at the same time, with disastrous results.

### Multitasking

Multitasking refers to execution of multiple tasks (say
processes, programs, threads etc.) at a time. Multitasking is a logical extension of multiprogramming. The major way in which multitasking differs from multiprogramming is that multiprogramming works solely on the concept of context switching whereas multitasking is based on time sharing alongside the concept of context switching.

### Multiprogramming

In a modern computing system, there are usually several concurrent application processes which want to execute. Now it is the responsibility of the Operating System to manage all the
processes effectively and efficiently.

One of the most important aspects of an Operating System is to multiprogram.

In a computer system, there are multiple processes waiting to be executed, i.e. they are
waiting when the CPU will be allocated to them and they begin their execution. These processes are also known as jobs. Now the main memory is too small to accommodate all of these processes or jobs into it. Thus, these processes are initially kept in an area called job pool. This job pool consists of all those processes awaiting allocation of main memory and CPU.

CPU selects one job out of all these waiting jobs, brings it from the job pool to main memory
and starts executing it. The processor executes one job until it is interrupted by some
external factor or it goes for an I/O task.

### Multithreading

Multi threading is the ability of a process to manage its use by more than one user at a time and to manage multiple requests by the same user without having to have multiple copies of the program.

### Multiprocessing

Multiprocessing is the use of two or more CPUs (processors) within a single Computer system. The term also refers to the ability of a system to support more than one processor
within a single computer system. Now since there are multiple processors available, multiple processes can be executed at a time.

### What is IPC?

IPC means inter process communication- process to process notification, process to process synchronization which allows a programmer to coordinate activities among different program processes that can run concurrently in an operating system.

*Signals*: Signals come under IPC mechanisms that are used for notification – notification can be process to process – notification can be system to process.
Kill is the command by which one process can send a signal to other.
Example:
1) Kill SIGINT 1234
2) Kill SIGQUIT 1234

### Zombie Process

A zombie process is a process that has completed and in the terminated state but has its entry in the process table. It shows that the resources are held by the process and are not
free.

### Sockets

- A socket is defined as endpoint for communication, a pair of sockets is used by the pair of processes.
- It is made of IP address chained with a port number.
- They use the client server architecture.
- Server waits for incoming client requests by listening to specified port.
- On reception of request, server accepts connection from client socket to complete the connection.

### What is Starvation and Aging

Starvation: Starvation is a resource management problem where a process is denied of resource or service for a long time or has been repeatedly denied services.
Aging: This is a solution to starvation which involves gradually increasing the priority of processes
that wait in the system for a long time.

The aging factor must increase the requests priority as time passes and must ensure that a request will eventually be the highest priority request (after it has waited long enough) and
gets the chance to execute.

### Difference between Semaphore and Mutex

| Basis for Comparison | Semaphore | Mutex |
| ----------- | ----------- | ----------- |
| Basic | Semaphore is a signalling mechanism | Mutex is a locking mechanism|
| Existence | Semaphore is an integer variable. | Mutex is an object. |
| Function | Semaphore allow multiple program threads to access a finite instance of resources. | Mutex allow multiple program
thread to access a single resource but not
simultaneously. |
| Ownership | Semaphore value can be changed by any process acquiring or releasing the resource. | Mutex object lock is released only by the process that has
acquired the lock on it |
| Categorize | Semaphore can be categorized into counting semaphore and binary
semaphore | Mutex is not categorized
further. |
| Operation | Semaphore value is modified using wait() and signal() operation | Mutex object is locked or unlocked by the process
requesting or releasing the resource. |
| Resource Occupied | If all resources are being used, the process requesting for resource performs wait() operation and block
itself till semaphore count become greater than one | If a mutex object is already
locked, the process requesting for resources
waits and queued by the system till lock is released. | 

### fork and exec system calls ?

Fork is a system call by which a new process is created. Exec is also a system call, which is used after a fork by one of the two processes to place the process memory space with a new program.

### What is Thread? Difference between Thread and Process?

A thread is a single sequence stream within a process. Because threads have some of the
properties of processes, they are sometimes called lightweight processes. Threads are a
popular way to improve application through parallelism. For example, in a browser, multiple tabs can be different threads. MS word uses multiple threads, one thread to format the text, other thread to process inputs, etc.

A thread has its own program counter (PC), a register set, and a stack space. Threads are not independent of one other like processes as a result threads share with other threads their code section, data section and OS resources like open files and signals.

### System Calls?

System calls provide the interface between a process and the Operating system. System Calls are also called Monitor call or Operating-system function call. When a
system call is executed, it is treated as by the hardware as software interrupt. Control passes through the interrupt vector toa service routine in the operating system, and the mode bit is set to monitor mode.

### Difference between preemptive and non preemptive scheduling ?

| Parameters | Preemptive Scheduling | Non Premeptive Scheduling |
| ----------- | ----------- | ----------- |
| Basic | In this resource(CPU Cycle) are allocated to a process for a limited time | Once resources(CPU Cycle) are allocated to a process, the process holds it till it completes its burst time or switches to waiting state.
| Interrupt | Process can be interrupted in between. | Process can not be interrupted until it terminates itself or its time is up. |
| Starvation | If a process having high
priority frequently arrives in the ready queue, low priority processes may starve. | If a process with long burst time is running CPU, then later coming processes with less CPU burst time may starve. |
| Overhead | It has overheads of scheduling the processes. | It does not have overheads |
| Flexibility | flexible | rigid |
| Cost | Cost Associated | No cost associated | 
| CPU Utilization | In preemptive
scheduling, CPU utilization is high. | It is low |
| Example |  Round Robin and Shortest Remaining Time First. | First Come First
Serve and Shortest Job First. | 

### Mutual Exclusion

Mutual exclusion refers to the requirement of ensuring that no two process or threads are in their critical section at the same time. i.e. If process Pi is executing in its critical section, then no other processes can be executing in their critical sections.

### Critical Section

The critical section is a code segment where the shared variables can be accessed. An atomic action is required in a critical section i.e. only one process can execute in its critical section at a time. All the other processes have to wait to execute in their critical sections.

*Context Switching*: Switching the CPU to another process requires saving the state of the old process and loading the saved state for the new process. This task is known as context switch.

### Deadlock? How to avoid and prevent?

Deadlock is a situation when two or more processes wait for each other to finish and none of them ever finish. Consider an example when two trains are coming toward each other on same track and there is only one track, none of the trains can move once they are in front of each other. Similar situation occurs in operating systems when there are two or more processes hold some resources and wait for resources held by other(s).
There are three ways to handle deadlock
1. Deadlock prevention or avoidance: The idea is to not let the system into deadlock state.
2. Deadlock detection and recovery: Let deadlock occur, then do preemption to handle it once occurred.
3. Ignore the problem all together: If deadlock is very rare, then let it happen and reboot the system.

#### Necessary Condition for deadlock

1. Mutual Exclusion: There is a resource that cannot be shared.
2. Hold and Wait: A process is holding at least one resource and waiting for another resource which is with some other process.
3. No Preemption: The operating system is not allowed to take a resource back from a process until process gives it back.
4. Circular Wait: A set of processes are waiting for each other in circular form.

### Segmentation

Segmentation is a memory management technique in which each job is divided into several segments of different sizes, one for each module that contains pieces that perform related functions. Each segment is actually a different logical address space of the program.

When a process is to be executed, its corresponding segmentation are loaded into non-contiguous memory though every segment is loaded into a contiguous block of available memory.

Segmentation memory management works very similar to paging but here segments are of
variable-length where as in paging pages are of fixed size.

### Virtual Memory

Virtual memory creates an illusion that each user has one or more contiguous address
spaces, each beginning at address zero. The sizes of such virtual address spaces is
generally very high. The idea of virtual memory is to use disk space to extend the RAM. Running processes don’t need to care whether the memory is from RAM or disk. The illusion of such a large amount of memory is created by subdividing the virtual memory into smaller pieces, which can be
loaded into physical memory whenever they are needed by a process.

### Fragmentation

Fragmentation is memory wasted. It can be internal if we are dealing with systems that have fixed-sized allocation units, or external if we are dealing with systems that have variable-sized allocation units.

### Dynamic Loading

To obtain better memory-space utilization dynamic loading is used. With dynamic
loading, a routine is not loaded until it is called. All routines are kept on disk in a relocatable load format. The main program is loaded into memory and executed. If the
routine needs another routine, the calling routine checks whether the routine has been
loaded. If not, the relocatable linking loader is called to load the desired program into Memory.

### Dynamic Linking

Dynamic linking is similar to dynamic loading, rather that loading being
postponed until execution time, linking is postponed. This feature is usually used with
system libraries, such as language subroutine libraries. A stub is included in the image for each library-routine reference. The stub is a small piece of code that indicates how to locate the appropriate memory-resident library routine, or how to load the library if the routine is not already present.

### RAID

RAID stands for *Redundant Array of Independent Disks*. It is used to store the same data redundantly to improve the overall performance.
Following are the different RAID levels:
- RAID 0 - Stripped Disk Array without fault tolerance
- RAID 1 - Mirroring and duplexing
- RAID 2 - Memory-style error-correcting codes
- RAID 3 - Bit-interleaved Parity
- RAID 4 - Block-interleaved Parity
- RAID 5 - Block-interleaved distributed parity
- RAID 6 - P+Q Redundancy

### What is inode?

Inode is a data structure which holds all the attributes of a file. It is also called index number.
Some of the attributes of file are:
- File type
- Permission
- File size
- Time when last it is modified.