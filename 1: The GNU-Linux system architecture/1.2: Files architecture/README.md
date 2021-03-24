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

WORK IN PROGRESS
