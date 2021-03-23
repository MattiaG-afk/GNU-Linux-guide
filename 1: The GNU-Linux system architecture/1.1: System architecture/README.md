# 1 System architecture
## 1.1 The basic architecture
The GNU / Linux system was born, like all UNIX systems, to be multitasking and multiuser.

The architecture of the GNU/Linux system, like all UNIX system, is based in the separation between:
* Kernel: that is the nucleus of the system, to which hardware resource management is required (CPU, memory, peripherals);
* Processes: that are the program execution unit, ranging from basic system commands, to applications, etc.
The kernel's job is to run many processes at the same time efficiently.

This leads to a split between:
* Kernel space: which is the environment in which the kernel runs;
* User space: which is the environment available to users, where processes are run.

This division shows that only the kernel can directly access hardware resources, while the programs are executed in a protected manner, in a virtual environment, but which can access the resources made available to the kernel thanks to standardized functions called **system calls** (standard: POSIX.1).

System calls and other basic functions are collected in a single library which is the **GNU C Library** (**glibc** for short).

The only program that is then executed is the kernel. A part of the kernel called **scheduler**, is responsible for managing the processor time, and is therefore responsible for deciding which process must be performed at a given moment (multitasking).

A second part, the **VM** (or **Virtual Memory**), deals with managing the use of available memory. Virtual memory is what makes each process see its own address space which is then remapped into actual physical memory.

The last part of the kernel, the **drivers**, is a set of modules that allow the management of various peripherals, providing access for programs.

The consequence of the division between user and kernel space is that in this way it is not possible for a single program to disturb the action of another program or of the kernel itself.
## 1.2 The functioning of the system
WORK IN PROGRESS
