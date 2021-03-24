 # 1.2 Files architecture
 One of the fundamental criteria of a UNIX system is that everything is a file, with the only exception of the interfaces of network devices.
 ## 1.2.1 The Virtual File System and the characteristics of the files
On a UNIX system, all files are the same, plus extensions are just conventions and mean nothing to the kernel, which reads the data the same way.

Actually the system expects different types of files, but in another sense.

These are:
* Regular file: a file that contains data (what is usually meant by a file). It is indicated with "-";
* Directory: a file that contains a list of names associated with inodes. It is indicated with "d";
* Symbolic link: a file that contains a reference to another file or directory. It is indicated with "l";
* Char device: a file that identifies a character access device. It is indicated with "c";
* Block device: a file that identifies a block access device. It is indicated with "b";
* Fifo or pipe: a special file that identifies a one-way communication line. It is indicated with "p";
* Socket: a special file that identifies a two-way communication line. It is indicated with "s".

The fifos and the sockets are communication channels made available to the kernel to let the processes communicate with each other, they are two different ways to realize the communication between processes:
* Fifo: one process can write on it and another process that has opened it will read on the other end what the first one has written, nothing will be saved on disk, but it will all pass through the kernel that allows this communication as through a pipe;
* Socket: they do the same thing but allow two-way communication, where the second process can write back, and the first can read.

The main file operations are:
* Open: opens the file;
* Read: read the file;
* Write: writes to file;
* Llseek: moves within the file;
* Ioctl: access control operations;
* Readdir: reads the contents of a directory.

One of the basic programs for managing files is **ls** (**l**i**s**t files), which displays (with no arguments) the list of all files in the current directory.

Using the -l option it is possible to obtain an extended list, with the various properties of the files. The information is:
* File type: the first character of the first column;
* File permissions: the rest of the first column;
* Number of Hard Links to the file: the second column;
* The user and the owner group of the file: in the third and fourth columns;
* Size (in bytes): in the fifth column;
* Last file modification: in the sixth column;
* File name: in the last column.

Other options of the **ls** command are:
* -a: show invisible files;
* -i: write the inode number;
* -R: execute the list recursively for all subdirectories;
* -c: use the time of last file change, that is the changes on file properties;
* -u: use the last access time to the file;
* -d: it only displays the name and not the content when referring to a directory, and does not execute symbolic links.

WORK IN PROGRESS
