# CS25C11 – Operating Systems Laboratory

![Language](https://img.shields.io/badge/Language-C-blue)
![Course](https://img.shields.io/badge/Course-Operating%20Systems-green)
![Regulation](https://img.shields.io/badge/Regulation-2025-orange)
![University](https://img.shields.io/badge/Anna%20University-2025-red)

## 📚 About

This repository contains the **C programs and practical implementations** for the **CS25C11 – Operating Systems Laboratory** course.

The programs cover fundamental Operating System concepts including:

* UNIX commands
* Process creation and system calls
* File handling using system calls
* CPU scheduling
* Process synchronization
* Deadlock avoidance
* Memory management
* Page replacement
* Disk scheduling

The programs are designed for practical laboratory practice and demonstrate the implementation of important Operating System concepts using **C programming**.

---

## 🎓 Course Information

| Detail               | Information                                |
| -------------------- | ------------------------------------------ |
| Course Code          | CS25C11                                    |
| Course               | Operating Systems Laboratory               |
| Programme            | B.E. Computer Science and Engineering      |
| Specialization       | Artificial Intelligence & Machine Learning |
| Regulation           | Anna University – Regulation 2025          |
| Institution          | Ramco Institute of Technology              |
| Programming Language | C                                          |

---

## 📂 Experiments

### 1. Basic UNIX Commands

Study and practice basic UNIX commands for:

* Directory navigation
* File manipulation
* File permissions
* Searching and displaying file contents

Commands covered include:

`pwd`, `ls`, `cd`, `mkdir`, `rmdir`, `touch`, `cat`, `cp`, `mv`, `rm`, `head`, `tail`, `wc`, `grep`, `chmod`, and `chown`.

---

### 2. fork(), exec() and wait() System Calls

Demonstrates:

* Process creation using `fork()`
* Process image replacement using `exec()`
* Parent-child synchronization using `wait()`
* Process identification using `getpid()` and `getppid()`

The child process executes the `ls -l` command using `execlp()`.

---

### 3. File Copy using open(), read() and write()

Implements file copying using low-level UNIX system calls:

* `open()`
* `read()`
* `write()`
* `close()`

The program accepts source and destination file names and copies the source file contents into the destination file.

---

## ⚙️ CPU Scheduling

### 4. First Come First Serve (FCFS)

Simulates the **FCFS CPU scheduling algorithm** and calculates:

* Waiting Time
* Turnaround Time
* Average Waiting Time
* Average Turnaround Time

---

### 5. Shortest Job First (SJF) – Non-Preemptive

Implements **Non-Preemptive SJF scheduling**.

The program selects the arrived process having the smallest burst time and calculates:

* Waiting Time
* Turnaround Time
* Average Waiting Time
* Average Turnaround Time

---

### 6. Round Robin

Implements the **Round Robin CPU scheduling algorithm** using a specified time quantum.

The program calculates:

* Waiting Time
* Turnaround Time
* Average Waiting Time
* Average Turnaround Time

A ready queue is maintained for process execution.

---

### 7. Priority Scheduling – Non-Preemptive

Implements **Non-Preemptive Priority Scheduling**.

The program considers:

* Arrival Time
* Burst Time
* Priority

A smaller priority number represents a higher priority.

---

## 🔄 Process Synchronization

### 8. Producer-Consumer Problem using Semaphores

Implements the bounded-buffer **Producer-Consumer Problem** using:

* POSIX Threads
* Semaphores
* Mutex

The program ensures proper synchronization between producer and consumer processes and prevents buffer overflow, underflow and race conditions.

Compile using:

```bash
gcc producer_consumer.c -o producer_consumer -lpthread
```

---

### 9. Dining Philosophers Problem using Semaphores

Implements the **Dining Philosophers Problem** using POSIX threads and semaphores.

The solution uses:

* Binary semaphores for forks
* A counting semaphore called `room`
* POSIX threads

The `room` semaphore allows at most `N-1` philosophers to attempt to pick up forks simultaneously, preventing circular wait.

Compile using:

```bash
gcc dining_philosophers.c -o dining_philosophers -lpthread
```

---

## 🔒 Deadlock Management

### 10. Banker's Algorithm

Implements the **Banker's Algorithm for Deadlock Avoidance**.

The program:

* Calculates the Need matrix
* Checks whether the system is in a safe state
* Generates a safe sequence
* Processes resource requests
* Grants requests only when the resulting state remains safe

The algorithm uses:

**Need = Maximum − Allocation**

---

## 💾 Memory Management

### 11. Contiguous Memory Allocation

Implements three contiguous memory allocation strategies:

#### First Fit

Allocates a process to the first available block large enough to hold it.

#### Best Fit

Allocates a process to the smallest available block that can accommodate it.

#### Worst Fit

Allocates a process to the largest available memory block.

The program displays the block allocated to each process for all three strategies.

---

### 12. Page Replacement Algorithms

Implements three page replacement algorithms:

* FIFO
* LRU
* Optimal

The program:

* Accepts a page reference string
* Accepts the number of page frames
* Displays page hits and faults
* Displays frame contents
* Calculates total page faults

#### FIFO

Replaces the page that has been in memory for the longest time.

#### LRU

Replaces the page that has not been used for the longest period.

#### Optimal

Replaces the page whose next use is farthest in the future.

---

## 💿 Disk Scheduling

### 13. Disk Scheduling Algorithms

Implements:

* SSTF
* SCAN
* C-SCAN

The program accepts:

* Disk request queue
* Initial head position
* Disk size
* Initial direction

It displays the **seek sequence** and calculates the **total head movement**.

### SSTF

Services the request closest to the current head position.

### SCAN

Moves the disk head in one direction, services requests, reaches the disk boundary and then reverses direction.

### C-SCAN

Moves in one direction, reaches the disk boundary and jumps back to the beginning before continuing in the same direction.

---

## 📁 Suggested Repository Structure

```text
Operating-Systems-Laboratory/
│
├── README.md
│
├── 01-Basic-UNIX-Commands/
│
├── 02-Fork-Exec-Wait/
│
├── 03-File-Copy-System-Calls/
│
├── 04-FCFS-Scheduling/
│
├── 05-SJF-Non-Preemptive/
│
├── 06-Round-Robin/
│
├── 07-Priority-Scheduling/
│
├── 08-Producer-Consumer/
│
├── 09-Dining-Philosophers/
│
├── 10-Bankers-Algorithm/
│
├── 11-Memory-Allocation/
│
├── 12-Page-Replacement/
│
└── 13-Disk-Scheduling/
```

---

## 🛠️ Requirements

To execute the programs, the following are recommended:

* GCC Compiler
* Linux / UNIX environment
* Terminal
* POSIX Threads library for synchronization programs

For programs using pthreads and semaphores:

```bash
gcc filename.c -o output -lpthread
```

For normal C programs:

```bash
gcc filename.c -o output
```

Run using:

```bash
./output
```

---

## 🧠 Concepts Covered

This repository provides practical implementation of the following Operating System concepts:

| Category          | Concepts                               |
| ----------------- | -------------------------------------- |
| UNIX              | Basic UNIX Commands                    |
| Processes         | `fork()`, `exec()`, `wait()`           |
| Files             | `open()`, `read()`, `write()`          |
| CPU Scheduling    | FCFS, SJF, Round Robin, Priority       |
| Synchronization   | Producer-Consumer, Dining Philosophers |
| Deadlock          | Banker's Algorithm                     |
| Memory Management | First Fit, Best Fit, Worst Fit         |
| Virtual Memory    | FIFO, LRU, Optimal                     |
| Disk Management   | SSTF, SCAN, C-SCAN                     |

---

## 🎯 Learning Objectives

By completing these experiments, students can understand and implement:

* Basic UNIX commands and file permissions
* Process creation and synchronization
* Low-level file operations
* CPU scheduling algorithms
* Process synchronization mechanisms
* Semaphore-based solutions
* Deadlock avoidance techniques
* Memory allocation strategies
* Page replacement algorithms
* Disk scheduling algorithms

---

## 💻 Programming Language

All major experiments in this repository are implemented using:

```text
C Programming Language
```

Some synchronization programs additionally use:

```text
POSIX Threads (pthread)
POSIX Semaphores
```

---

## 👨‍💻 Author

**Operating Systems Laboratory**

CS25C11
B.E. Computer Science and Engineering (AI & ML)
Ramco Institute of Technology

---

## 📌 Note

This repository is intended for **academic and laboratory practice**. The implementations follow the experiments and terminology provided in the CS25C11 Operating Systems Laboratory manual.
