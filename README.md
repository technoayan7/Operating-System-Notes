
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
   - **Thread**: The smallest sequence of programmed instructions within a process, allowing concurrent execution.

### 5. **Socket, Shell, Kernel, and Monolithic Kernel**
   - **Socket**: An endpoint for sending/receiving data over a network.
   - **Shell**: Interface to access OS services, either via command-line or GUI.
   - **Kernel**: Core component managing system resources, like memory and CPU.
   - **Monolithic Kernel**: A type of kernel where all OS services run in the same memory space for efficiency.

### 6. **Multitasking vs. Multithreading**
   - **Multitasking**: Running multiple applications simultaneously.
   - **Multithreading**: Running multiple threads within a single application to improve efficiency.

### 7. **Multitasking vs. Multiprocessing**
   - **Multitasking**: Uses one CPU to run multiple tasks by quickly switching between them.
   - **Multiprocessing**: Uses multiple CPUs or cores to run tasks simultaneously, improving performance.

### 8. **Process States and Queues**
   - **Process States**: New, Ready, Running, Waiting, Terminated.
   - **Process Queues**:
     - **Ready Queue**: Holds processes ready for CPU time.
     - **Waiting Queue**: Holds processes waiting for I/O.

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
   - **Definition**: Process of saving and restoring the state of a CPU so a different process can run.
   - **Overhead**: Increases CPU load but allows multitasking.

### 13. **Zombie Process & Orphan Process**
   - **Zombie Process**: A terminated process still occupying memory until the parent acknowledges it.
   - **Orphan Process**: A child process without a parent, often adopted by the init system in Unix-based OS.

### 14. **RAID (Redundant Array of Independent Disks)**
   - **Definition**: A method of storing data across multiple disks for redundancy or performance.
   - **Types**: RAID 0 (striping), RAID 1 (mirroring), RAID 5 (striping with parity), etc.

### 15. **Starvation and Aging**
   - **Starvation**: A process waits indefinitely for resources.
   - **Aging**: Gradually increases priority of waiting processes to prevent starvation.

### 16. **Scheduling Algorithms**
   - **Purpose**: Determines the order in which processes access the CPU.
   - **Types**: Includes FCFS, Round Robin, Priority Scheduling, etc.

### 17. **Preemptive vs. Non-Preemptive Scheduling**
   - **Preemptive**: OS can interrupt and reassign CPU from a running process.
   - **Non-Preemptive**: Once a process starts, it runs until completion or voluntary release of CPU.

### 18. **FCFS & Convoy Effect**
   - **FCFS (First-Come, First-Serve)**: Processes handled in order of arrival.
   - **Convoy Effect**: Occurs in FCFS when a long process delays others behind it.

### 19. **Round Robin Scheduling**
   - **Definition**: Assigns each process a fixed time slice in cyclic order.
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

### 24. **Conditional Variable**
   - **Definition**: A variable used to control access in multithreading, allowing threads to wait until certain conditions are met.

### 25. **Semaphores vs. Mutex**
   - **Semaphore**: Allows multiple processes to access resources up to a limit.
   - **Mutex**: Only allows one process at a time, preventing concurrent access.

### 26. **Binary vs. Counting Semaphores**
   - **Binary Semaphore**: Only two values (0 or 1), similar to a lock.
   - **Counting Semaphore**: Allows more flexibility with a range of values for managing multiple resources.

### 27. **Producer-Consumer Problem**
   - **Definition**: Synchronization issue where producer and consumer processes access shared data.
   - **Solution**: Use semaphores or mutexes to control access.

### 28. **Belady’s Anomaly**
   - **Definition**: An increase in page faults despite increasing memory pages in certain algorithms.
   - **Occurs In**: FIFO page replacement algorithm.

### 29. **Deadlock, Conditions & Prevention**
   - **Deadlock**: Processes hold resources while waiting for others, causing a standstill.
   - **Conditions**: Mutual exclusion, hold and wait, no preemption, circular wait.
   - **Prevention**: Avoid one or more conditions using strategies like ordering resources.

### 30. **Banker’s Algorithm**
   - **Purpose**: Deadlock avoidance algorithm in resource allocation.
   - **Method**: Checks if resources can be safely allocated without causing deadlock.

### 31. **Buffer**
   - **Definition**: Temporary memory storage area for data exchange between components.

### 32. **Logical vs. Physical Address Space**
   - **Logical Address**: Generated by CPU, virtual.
   - **Physical Address**: Actual location in memory.

### 33. **Memory Management Unit (MMU)**
   - **Definition**: Hardware that translates logical to physical addresses.

### 34. **Main vs. Secondary Memory**
   - **Main Memory**: RAM, directly accessed by CPU, volatile.
   - **Secondary Memory**: Disk storage, not directly accessed by CPU, non-volatile.

### 35. **Cache**
   - **Definition**: Small, fast memory close to the CPU for quick access to frequently used data.

### 36. **Direct Mapping vs. Associative Mapping**
   - **Direct Mapping**: Each block has a fixed cache location.
   - **Associative Mapping**: Any block can go into any cache line, more flexible.

### 37. **Fragmentation**
   - **Internal Fragmentation**: Wasted space within allocated memory.
   - **External Fragmentation**: Wasted space outside allocated memory.

### 38. **Defragmentation**
   - **Definition**: Process of rearranging memory to reduce fragmentation.

### 39. **Spooling**
   - **Definition**: Storing data temporarily for devices to access when ready, like print jobs.

### 40. **Overlays**
   - **Definition**: Loading only needed parts of a program into memory to save space.

### 41. **Page Table, Frames, Pages**
   - **Page Table**: Maps logical pages to physical frames.
   - **Frame**: Fixed-size physical memory block.
   - **Page**: Fixed-size block of logical memory.

### 42

. **Paging & Its Need**
   - **Definition**: Dividing memory into pages to handle data efficiently.
   - **Purpose**: Avoids external fragmentation and simplifies memory management.

### 43. **Segmentation**
   - **Definition**: Dividing memory into segments based on logical units.

### 44. **Paging vs. Segmentation**
   - **Paging**: Fixed-size pages, avoids external fragmentation.
   - **Segmentation**: Variable-size segments, groups data logically.

### 45. **Page Faults**
   - **Definition**: Occurs when a program accesses a page not in physical memory.

### 46. **Virtual Memory**
   - **Definition**: Technique that gives applications more memory than physically available.

### 47. **Demand Paging**
   - **Definition**: Loads pages into memory only when needed.

### 48. **Page Replacement Algorithms**
   - **Types**: FIFO, LRU, Optimal; handle swapping when memory is full.

### 49. **Thrashing**
   - **Definition**: Excessive swapping between memory and disk, slowing the system.

--- 
