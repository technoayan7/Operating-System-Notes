
---

# Operating System Concepts - Interview Guide

### 1. **Operating System (OS) & Types**
   - **Definition**: Software that manages computer hardware and software resources and provides common services for applications.
   - **Types**:
     - **Batch OS**: Processes batches of jobs with no interaction.
     - **Time-Sharing OS**: Allows multiple users to interact with programs simultaneously.
     - **Distributed OS**: Manages a group of separate computers and makes them act as one system.

### 2. **Purpose of an OS**
   - **Resource Management**: Allocates CPU, memory, and I/O devices to processes.
   - **Task Management**: Manages tasks like process scheduling, multitasking, and resource sharing.
   - **User Interface**: Provides a user-friendly way to interact with the system (GUI or command-line).

### 3. **Real-Time Operating System (RTOS) & Types**
   - **Definition**: An OS designed for real-time applications where responses are needed within a specific time.
   - **Types**:
     - **Hard RTOS**: Guarantees critical tasks are completed on time.
     - **Soft RTOS**: Prioritizes timely responses but allows minor delays.
     - **Firm RTOS**: Tasks have deadlines, but some can miss them without major issues.

### 4. **Program, Process, and Thread**
   - **Program**: A static set of instructions written to perform a task.
   - **Process**: A running instance of a program, actively using resources.


| **Program**                                              | **Process**                                          |
|---------------------------------------------------------|-----------------------------------------------------|
| Contains a set of instructions designed to complete a specific task. | Instance of an executing program.                   |
| Passive entity that resides in secondary memory.       | Active entity created during execution, loaded into main memory. |
| Exists in a single place until deleted.                | Exists for a limited time, terminating after task completion. |
| Static entity with no resource requirement.             | Dynamic entity with high resource requirements, needing CPU, memory, and I/O. |

   - **Process Table**: The operating system manages processes, allocating processor time 
   and resources like memory and disks. The process table is maintained by the OS
to keep track of all processes, including their states and resources they are using.
   - **Thread**: A thread is a single sequence of execution within a process, often
called a lightweight process. Threads improve application performance through parallelism. For example, a web browser can use multiple threads for different tabs.

  
  | **Process**                                         | **Thread**                                           |
|-----------------------------------------------------|------------------------------------------------------|
| A process is a program in execution.                | A thread is a smaller unit within a process.         |
| Processes are isolated from each other.             | Threads share memory within the same process.        |
| Process communication is less efficient.            | Thread communication is more efficient.              |
| Processes are considered heavyweight.               | Threads are considered lightweight.                  |
| Process switching requires OS intervention.         | Thread switching does not require OS intervention.   |
| One blocked process doesn't affect others.          | A blocked thread can affect other threads in the same process. |


### 5. **PCB, Socket, Shell, Kernel, and Monolithic Kernel**
   - **Process Control Block (PCB)** tracks the execution status of a process,
   containing information like registers, priority, and execution state. The process
table is an array of PCBs, each representing a process in the system.
   - **Socket**: An endpoint for sending/receiving data over a network.
   - **Shell**: Interface to access OS services, either via command-line or GUI.
   - **Kernel**: The kernel is the core component of an operating system, managing
memory, CPU time, and hardware operations. It acts as a bridge
between applications and hardware-level data processing.

| **Kernel**                                              | **Operating System (OS)**                                  |
|---------------------------------------------------------|-----------------------------------------------------------|
| Central component of the OS.                            | System software that manages system resources.            |
| Converts user commands into machine-level instructions. | Manages overall system resources and operations.          |
| Acts as an interface between hardware and applications. | Acts as an interface between hardware and the user.       |
| Handles process, file, device management, and I/O.      | Provides data security, user access control, and privacy. |
| Types include Microkernel, Monolithic kernel, etc.      | Types include Single and Multiprogramming, Distributed OS, Real-time OS. |
   - **Monolithic Kernel**: A monolithic kernel manages system resources and implements 
   user and kernel services in the same address space, making the OS execution faster
   but increasing its size. It handles CPU scheduling, memory management, file management, and other functions through system calls.

   | **Microkernel**                                             | **Monolithic Kernel**                                        |
|-------------------------------------------------------------|-------------------------------------------------------------|
| Kernel and user services are in separate address spaces.    | Kernel and user services are in the same address space.      |
| Smaller in size compared to a monolithic kernel.            | Larger in size than a microkernel.                           |
| More easily extendible.                                     | Harder to extend.                                            |
| Service crashes do not affect the microkernel's operation.  | A service crash can cause the entire system to crash.        |
| Uses message queues for inter-process communication (IPC).  | Uses signals and sockets for inter-process communication.     |

### 6. **Multitasking vs. Multithreading**

| **Multi-threading**                                         | **Multi-tasking**                                       |
|-------------------------------------------------------------|--------------------------------------------------------|
| Multiple threads are executed at the same time within the same or different parts of a program. | Several programs (or tasks) are executed concurrently. |
| The CPU switches between multiple threads.                  | The CPU switches between multiple tasks or processes.   |
| It is a lightweight process, involving parts of a single process. | It is a heavyweight process, involving multiple processes. |
| Multi-threading is a feature of the process, allowing it to split into threads. | Multitasking is a feature of the OS, enabling it to handle multiple applications. |
| Involves sharing computing resources among threads of a single process. | Involves sharing computing resources (CPU, memory, devices) among multiple processes. |

### 7. **Multitasking vs. Multiprocessing**
   | **Multitasking**                                            | **Multiprocessing**                                         |
|-------------------------------------------------------------|-------------------------------------------------------------|
| Performs multiple tasks using a single processor.           | Performs multiple tasks using multiple processors.          |
| Has only one CPU.                                           | Has more than one CPU.                                      |
| More economical.                                            | Less economical.                                            |
| Less efficient than multiprocessing.                        | More efficient than multitasking.                           |
| Allows fast switching between tasks.                        | Allows smooth simultaneous task processing.                 |
| Requires more time to execute tasks.                        | Requires less time for task processing.                     |

### 8. **Process States and Queues**

   - **Process States**:  
     Different states that a process goes through include:
     - **New State**: The process is just created.
     - **Running**: The CPU is actively executing the process's instructions.
     - **Waiting**: The process is paused, waiting for an event to occur.
     - **Ready**: The process has all necessary resources and is waiting for CPU assignment.
     - **Terminate**: The process has completed execution and is finished.

   - **Process Queues**:
     - **Ready Queue**: Holds processes that are ready for CPU time.
     - **Waiting Queue**: Holds processes that are waiting for I/O operations.

### 9. **Inter-Process Communication (IPC)**
   - **Purpose**: Allows processes to communicate and share data.
   - **Techniques**: Includes pipes, message queues, shared memory, and semaphores.

### 10. **Dynamic Binding**
   - **Definition**: Linking a function or variable at runtime rather than at compile-time.
   - **Advantage**: Flexibility in program behavior and memory use.

### 11. **Swapping**
   - **Definition**: Moving processes between main memory and disk storage.
   - **Purpose**: Frees up memory for active processes, improving system performance.

### 12. **Context Switching**
   - **Definition**: Context switching involves saving the state of a currently running process and
loading the saved state of a new process. The process state is stored in the
Process Control Block, allowing the old process to resume from where it left off.
   - **Overhead**: Increases CPU load but allows multitasking.

### 13. **Zombie Process & Orphan Process**
   - **Zombie Process**: A terminated process still occupying memory until the parent acknowledges it.
   - **Orphan Process**: A child process without a parent, often adopted by the init system in Unix-based OS.

### 14. **RAID (Redundant Array of Independent Disks)**
   - **Definition**: A method of storing data across multiple disks for redundancy or performance.
   - **Types**: RAID 0 (striping), RAID 1 (mirroring), RAID 5 (striping with parity), etc.

### 15. **Starvation and Aging**
   - **Starvation**: when a process does not get the resources it needs for a long
time because other processes are prioritized.
   - **Aging**: Gradually increases priority of waiting processes to prevent starvation.

### 16. **Scheduling Algorithms**
   - **Purpose**: Determines the order in which processes access the CPU.
   - **Types**: Includes FCFS, Round Robin, Priority Scheduling, etc.

### 17. **Preemptive vs. Non-Preemptive Scheduling**
   - **Preemptive**: OS can interrupt and reassign CPU from a running process.
   - **Non-Preemptive**: Once a process starts, it runs until completion or voluntary release of CPU.

### 18. **FCFS & Convoy Effect**
   - **FCFS (First-Come, First-Serve)**: FCFS schedules jobs in the order they arrive in the ready queue. It is non-preemptive, meaning a process holds the CPU until it terminates or performs I/O, causing longer jobs to delay shorter ones.
   - **Convoy Effect**: Occurs in FCFS when a long process delays others behind it.

### 19. **Round Robin Scheduling**
   - **Definition**: Schedules processes in a time slice or quantum, rotating through processes to ensure fair allocation of CPU time and preventing starvation. It is cyclic and does not prioritize any process.
   - **Advantage**: Fair and efficient for time-sharing systems.

### 20. **Priority Scheduling**
   - **Definition**: Processes assigned CPU based on priority levels.
   - **Challenge**: Risk of starvation for lower-priority processes.

### 21. **Concurrency**
   - **Definition**: Multiple processes appear to run simultaneously.
   - **Achieved By**: Multithreading or multitasking within a single CPU.

### 22. **Race Condition**
   - **Definition**: Two processes access shared data simultaneously, leading to unexpected results.
   - **Solution**: Use locks or synchronization mechanisms.

### 23. **Critical Section**
   - **Definition**: A part of code that accesses shared resources and must not be executed by more than one process at a time.


### 24. **Synchronization techniques?**

    -  Mutexes
    -  Condition variables
    -  Semaphores
    -  File locks

- **Mutex**: Only allows one process at a time, preventing concurrent access.
- **Conditional Variable**: A variable used to control access in multithreading, allowing threads to wait until certain conditions are met.
- **Semaphore**: Allows multiple processes to access resources up to a limit.


### 25. Semaphore in OS

A **Semaphore** is a synchronization tool used in operating systems to manage access to shared resources in multi-threaded or multi-process systems. It keeps a count of available resources and uses two atomic operations, `wait()` and `signal()`, to control access.

#### Types of Semaphores:
1. **Binary Semaphore**:  
   - Has values 0 or 1.
   - Signals availability of a single resource.

2. **Counting Semaphore**:  
   - Can have values greater than 1.
   - Controls access to multiple instances of a resource, like a pool of connections.

#### Binary Semaphore vs Mutex:
| **Binary Semaphore**                                 | **Mutex**                                         |
|-----------------------------------------------------|---------------------------------------------------|
| Signals availability of a shared resource (0 or 1). | Allows mutual exclusion with a single lock.       |
| Uses signaling mechanisms.                          | Uses a locking mechanism.                         |
| Faster in some cases with multiple processes.       | Slower when frequently contended.                 |
| Integer variable holding 0 or 1.                    | Object holding lock state and lock owner info.    |



### 26. **Binary vs. Counting Semaphores**
   - **Binary Semaphore**: Only two values (0 or 1), similar to a lock.
   - **Counting Semaphore**: Allows more flexibility with a range of values for managing multiple resources.

### 27. **Producer-Consumer Problem**
   - **Definition**: Synchronization issue where producer and consumer processes access shared data.
   - **Solution**: Use semaphores or mutexes to control access.

### 28. **Belady’s Anomaly**
   - **Definition**: An increase in page faults despite increasing memory pages in certain algorithms.
   - **Occurs In**: FIFO page replacement algorithm.

### 29. **What is a Deadlock in OS?**
- A deadlock is a situation in which a set of processes are blocked because each process holds resources and waits to acquire additional resources held by another process.
- In this scenario, two or more processes are unable to proceed because they are waiting for each other to release resources.
- Deadlocks commonly occur in multiprocessing environments and can result in the system becoming unresponsive.

### Necessary Conditions for Deadlock
1. **Mutual Exclusion**: Resources cannot be shared; at least one resource must be held in a non-shareable mode.
2. **Hold and Wait**: Processes holding resources are allowed to wait for additional resources.
3. **No Pre-emption**: Resources cannot be forcibly taken from a process; they must be voluntarily released.
4. **Circular Wait**: There exists a set of processes such that each process is waiting for a resource held by the next process in the cycle.
### 30. **Banker’s Algorithm**
   - **Purpose**: Deadlock avoidance algorithm in resource allocation.
   - **Method**: Checks if resources can be safely allocated without causing deadlock.

### 31. Methods for Handling Deadlock

1. **Deadlock Prevention**:
   - Ensure that at least one necessary condition for deadlock cannot hold.
   - Allow resource sharing (Mutual Exclusion).
   - Require all resources to be requested upfront (Hold and Wait).
   - Permit resource preemption (No Pre-emption).
   - Impose a strict order for resource allocation (Circular Wait).

2. **Deadlock Avoidance**:
   - Dynamically examine resource allocation to prevent circular wait.
   - Use the Banker’s Algorithm to determine safe states; deny requests that would lead to an unsafe state.

3. **Deadlock Detection**:
   - Allow the system to enter a deadlock state, then detect it.
   - Use a Wait-for Graph to represent wait-for relationships; a cycle indicates a deadlock.
   - Employ a Resource Allocation Graph to check for cycles and determine the presence of deadlock. 

4. **Deadlock Recovery**:
   - Terminate one or more processes involved in the deadlock (abruptly or gracefully).
   - Use resource preemption to take resources from processes and allocate them to others to break the deadlock.


### 32. **Logical vs. Physical Address Space**
   | **Parameter**            | **Logical Address**                               | **Physical Address**                              |
|--------------------------|--------------------------------------------------|--------------------------------------------------|
| **Basic**                | Generated by the CPU.                            | Located in a memory unit.                        |
| **Address Space**        | Set of all logical addresses generated by the CPU. | Set of all physical addresses corresponding to logical addresses. |
| **Visibility**           | Visible to the user.                             | Not visible to the user.                         |
| **Generation**           | Created by the CPU.                              | Computed by the Memory Management Unit (MMU).    |

### 33. **Memory Management Unit (MMU)**
   - **Definition**: Hardware that translates logical to physical addresses.

### 34. **Main vs. Secondary Memory**
   Here are six important differences between primary memory and secondary memory, presented succinctly:

| **Primary Memory**                                        | **Secondary Memory**                                     |
|----------------------------------------------------------|---------------------------------------------------------|
| Used for temporary data storage while the computer is running. | Used for permanent data storage, retaining information long-term. |
| Faster access speed as it is directly accessible by the CPU. | Slower access speed; not directly accessible by the CPU. |
| Volatile in nature; data is lost when power is turned off. | Non-volatile; retains data even when power is off.      |
| More expensive due to the use of semiconductor technology. | Less expensive, often using magnetic or optical technology. |
| Capacity ranges from 16 to 32 GB, suitable for active tasks. | Capacity can range from 200 GB to several terabytes for extensive storage. |
| Examples include RAM, ROM, and Cache memory.             | Examples include Hard Disk Drives, Floppy Disks, and Magnetic Tapes. |

### 35. **Cache**
   - **Definition**: Small, fast memory close to the CPU for quick access to frequently used data.
   - **Caching**: Caching involves using a smaller, faster memory to store copies of data from
   frequently used main memory locations. Various independent caches within a
CPU store instructions and data, reducing the average time needed to access
data from the main memory.

### 36. **Direct Mapping vs. Associative Mapping**
   - **Direct Mapping**: Each block has a fixed cache location.
   - **Associative Mapping**: Any block can go into any cache line, more flexible.

### 37. **Fragmentation**
   - **Internal Fragmentation**: Fragmentation occurs when free memory space is too small to allocate
    to processes, leaving unusable memory blocks. It happens during dynamic memory allocation 
    when small free blocks cannot satisfy any request.
   - **Internal Fragmentation**: Wasted space within allocated memory.
   - **External Fragmentation**: Wasted space outside allocated memory.
   
   | **Internal Fragmentation**                                   | **External Fragmentation**                                 |
|--------------------------------------------------------------|-----------------------------------------------------------|
| Fixed-sized memory blocks are allocated to processes.        | Variable-sized memory blocks are allocated to processes.   |
| Occurs when allocated memory blocks are larger than required by the process. | Occurs when free memory is scattered in small, unusable fragments. |
| Solution: Best-fit block allocation.                         | Solution: Compaction, paging, and segmentation.            |
| Arises when memory is divided into fixed-sized partitions.   | Arises when memory is divided into variable-sized partitions. |
| Difference between allocated and required memory is wasted.  | Unused spaces between allocated blocks are too small for new processes. |

### 38. **Defragmentation**
   - **Definition**: Process of rearranging memory to reduce fragmentation.
   - **Compaction**: The process of collecting fragments of available memory space into contiguous blocks by moving programs and data in a computers memory or disk.

### 39. **Spooling**
   - **Definition**: Storing data temporarily for devices to access when ready, like print jobs.
   - Spooling stands for Simultaneous Peripheral Operations Online, which involves
placing jobs in a buffer, either in memory or on a disk, where a device can access
them when ready. It helps manage different data access rates of devices

### 40. **Overlays**
   - **Definition**: Overlays involve loading only the required part of a program into memory.
   unloading it when done, and loading a new part as needed. This technique efficiently manages memory usage.

### 41. **Page Table, Frames, Pages**
   - **Page Table**: Maps logical pages to physical frames.
   - **Frame**: Fixed-size physical memory block.
   - **Page**: Fixed-size block of logical memory.

### 42. Paging
   - **Definition**: Paging is a memory management technique for non-contiguous memory allocation,
   dividing both main and secondary memory into fixed size partitions called pages and frames,
   fetching process pages into main memory frames as needed.
   - **Purpose**: Avoids external fragmentation and simplifies memory management.

### 43. **Segmentation**
   - **Definition**: Dividing memory into segments based on logical units.

### 44. **Paging vs. Segmentation**
   | **Paging**                                             | **Segmentation**                                       |
|--------------------------------------------------------|-------------------------------------------------------|
| Invisible to the programmer.                           | Visible to the programmer.                            |
| Fixed-size pages.                                      | Variable-size segments.                               |
| Procedures and data cannot be separated.               | Procedures and data can be separated.                 |
| Allows virtual address space to exceed physical memory.| Breaks programs, data, and code into independent spaces. |
| Mostly found on CPUs and MMU chips.                    | Commonly found on Windows servers, limited in Linux.  |
| Faster memory access than segmentation.                | Slower memory access compared to paging.              |
| Results in internal fragmentation.                     | Results in external fragmentation.                   |


### 45. **Page Faults**
   - **Definition**: Occurs when a program accesses a page not in physical memory.

### 46. **What is virtual memory?**

     - A memory management technique in operating systems.
     - Creates the illusion of a large contiguous address space.
     - Extends physical memory using disk space.
     - Allows more programs to run simultaneously.
     - Stores data in pages for efficient memory use.
     - Provides memory protection.
     - Managed through methods like paging and segmentation.
     - Acts as temporary storage alongside RAM for processes.

### 47. **Demand Paging**
   - **Definition**: Demand paging loads pages into memory only when they are needed,
which occurs when a page fault happens.

### 48. **Page Replacement Algorithms**
   - **Types**: FIFO, LRU, Optimal; handle swapping when memory is full.

### 49. **Thrashing**
   - **Definition**: Excessive swapping between memory and disk, slowing the system. 
   
   - **Thrashing** occurs when a computer spends more time handling page faults 
   than executing transactions, degrading performance. It happens when the 
   page fault rate increases, leading to longer service times and reduced efficiency.

--- 
