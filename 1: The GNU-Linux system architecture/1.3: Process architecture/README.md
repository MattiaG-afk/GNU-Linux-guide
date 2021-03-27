 # 1.3 Process architecture
 ## 1.3.1 The characteristics of the process architecture
 The ranking of processes in a tree hierarchy base is based on the parent-child relationship can be printed with the **pstree** command.
 
In the creation of a child process it inherits from the father a whole series of properties and resources, and in particular one of the characteristics that distinguishes the architecture of the processes in a UNIX-like system is that all the files opened in the parent process will remain such and immediately also available for the child.
 
A second difference compared to other multi-user systems is that in Linux the creation of a process and the execution of a program are two separate operations, managed by two different system calls, the first of which creates a new process, identical to the parent, the which normally goes to use the second to run another program.
 
This feature also allows you to write a single program that executes multiple processes, with a structure in which the father executes the part that takes care of receiving requests, and for each of them he has a specially created child perform the operations necessary to provide their responses.
 
The command that allows you to get the list of active processes in the system is **ps** (**p**rocess **s**tatus), with the option:
* a: processes launched by other users will also be displayed, as long as they refer to a terminal;
* x: all processes not associated with a terminal are displayed;
* f: it allows to show the hierarchy of processes;
* r: allows you to restrict the selection to only actual running processes.

The output of the **ps** command is divided into columns:
* PID: in the first column, it shows the so-called process ID of the process. This is the number the kernel uses to uniquely identify each process; this number is assigned when the process is created, and is unique as long as the process is active;
* TTY: in the second column, it shows the so-called "control terminal" of the process. The non-interactive processes (daemons) that are used to perform a series of service tasks, having to be active even when there is no user connected, instead work in the background (for which there is no control terminal) the TTY column shows therefore a '?';
* STATUS: shows the status of the process. In fact, the system provides five different states for the processes:
     * runnable (R): the process is running or ready to run (i.e. waiting for the CPU to be assigned to it);
     * sleep (S): the process is waiting for a response from the system but can be interrupted by a signal;
     * uninterruptable sleep (D): the process is waiting for a response from the system (usually for I/O), and cannot be interrupted under any circumstances;
     * stopped (T): the process was stopped with a SIGSTOP, or is being tracked;
     * zombie (Z): the process has ended but its termination status has not yet been read by the father;
* TIME: indicates the CPU time used so far by the process
* COMMAND: reports the command line used to launch the program.

