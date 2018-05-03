INTER-PROCESS-COMMUNICATION IMPLEMENTATION:
This repository holds sample implementations for various inter-process-communication (IPC) methods on Linux.
The following IPC methods are implemented:
•	IPC using Filing
•	IPC using Shared Memory
•	IPC using Signals
•	IPC  using Semaphore
Project Installation:
You can build the project and all necessary executables on any Linux operating system. The Method is given below:
	Download Project.
Open Terminal and login as root by writing su root
	Write following command to run IPC using Semaphore:
o	cd Downloads/zipfile_name
o	unzip zipfile_name
o	gcc –o obj ipc_Semaphore.c
o	./obj 

	Write following command to run IPC using Filing:
o	Firstly open two terminal using ctrl+shift+t
	On first terminal
	cd Downloads/zipfile_name
	unzip zipfile_name
	gcc –o obj fifo_read.c
	On second terminal
	gcc –o qwe fifo_write.c
o	then on first terminal write,
o	./obj
o	And on second terminal,
o	./qwe

	Write following command to run IPC using Signals:
o	cd Downloads/zipfile_name
o	unzip zipfile_name
o	gcc –o obj ipc_signals.c
o	./obj 



	Write following command to run IPC using Semaphore:
o	cd Downloads/zipfile_name
o	unzip zipfile_name
o	gcc –o obj ipcSemaphore
o	./obj 

Explanation
Function:
fork()->System call is used to create process. Takes no argument and make parent and child process
mkfifo(prameter1,parameter 2)-> parameter1= “file location”,parameter2= permissions //for file creation
open(prameter1,parameter 2)-> parameter1= “file location”,parameter2= permissions //for file opening
semop()-> performs operations on selected semaphores in the set indicated by semid.  Each of the nsops elements in the array pointed to by sops is a structure that specifies an operation to be performed on a single semaphore.
kill()->  kill is used to send signal from one process to another.
signal()->  Signal is used to modify the signal handler.
Results:
When making few big data exchanges then IPC (synchronization and memory copying) is neglectable if to compare with object serialization to byte array. Better having simple objects (e.g. string or array of strings or with sequential memory layout) for IPC. Serialization is slowest thing in local IPC. IPC takes considerable amount of time for many small objects.
However, after detailed comparison of these algorithms, we found that shared memory is the better algorithm then other, because it not only communicates between more than two processes at a time, but also it is bi-directional which makes it better.
Given below is the benchmark calculated for all of these algorithms. 
============ RESULTS ================
Message size:      			 4096
Message count:   			   1000
Total duration:    			 1.945
Average duration:   		 1.418
Minimum duration:   		 0.000
Maximum duration:   		 25.000
Standard deviation: 		 1.282      
Message rate:  			     514138     msg/s
=====================================

Goals:
o	By using this you can learn how to implement IPC in different ways.
o	It is helpful to choose better IPC method using there comparison
To Be Done:
•	Review C++ for performance issues related to serialization because C# custom serialization is faster
•	Make multithreaded tests (consider single channel memory issues)
•	Use all method in one program to give best for accuracy and speed. 
•	Write and test named pipe transport for open sources which lack it, make tests.
•	Shuffle tests and shuffle data, investigate CPU cache influence
•	Make tests of managed Protobuf

.
