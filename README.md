INTER-PROCESS-COMMUNICATION IMPLEMENTATION:
This repository holds sample implementations for various inter-process-communication (IPC) methods on Linux.<br>
The following IPC methods are implemented:<br>
•	IPC using Filing<br>
•	IPC using Shared Memory<br>
•	IPC using Signals<br>
•	IPC  using Semaphore<br>
Project Installation:<br>
You can build the project and all necessary executables on any Linux operating system. The Method is given below:<br>
	Download Project.<br>
Open Terminal and login as root by writing su root<br>
	Write following command to run IPC using Semaphore:<br>
o	cd Downloads/zipfile_name<br>
o	unzip zipfile_name<br>
o	gcc –o obj ipc_Semaphore.c<br>
o	./obj <br>

	Write following command to run IPC using Filing:<br>
o	Firstly open two terminal using ctrl+shift+t<br>
	On first terminal<br>
	cd Downloads/zipfile_name<br>
	unzip zipfile_name<br>
	gcc –o obj fifo_read.c<br>
	On second terminal<br>
	gcc –o qwe fifo_write.c<br>
o	then on first terminal write,<br>
o	./obj<br>
o	And on second terminal,<br>
o	./qwe<br>

	Write following command to run IPC using Signals:<br>
o	cd Downloads/zipfile_name<br>
o	unzip zipfile_name<br>
o	gcc –o obj ipc_signals.c<br>
o	./obj <br>



	Write following command to run IPC using Semaphore:<br>
o	cd Downloads/zipfile_name<br>
o	unzip zipfile_name<br>
o	gcc –o obj ipcSemaphore<br>
o	./obj <br>


<br>
<body>
fork()System call is used to create process. Takes no argument and make parent and child process<br>
mkfifo(prameter1,parameter 2) parameter1= “file location”,parameter2= permissions //for file creation<br>
open(prameter1,parameter 2) parameter1= “file location”,parameter2= permissions //for file opening<br>
semop() performs operations on selected semaphores in the set indicated by semid.  Each of the nsops elements in the array pointed to by sops is a structure that specifies an operation to be performed on a single semaphore.<br>
kill()  kill is used to send signal from one process to another.<br>
signal()  Signal is used to modify the signal handler.<br>
Results:<br>
When making few big data exchanges then IPC (synchronization and memory copying) is neglectable if to compare with object serialization to byte array. Better having simple objects (e.g. string or array of strings or with sequential memory layout) for IPC. Serialization is slowest thing in local IPC. IPC takes considerable amount of time for many small objects.<br>
However, after detailed comparison of these algorithms, we found that shared memory is the better algorithm then other, because it not only communicates between more than two processes at a time, but also it is bi-directional which makes it better.<br>
Given below is the benchmark calculated for all of these algorithms. <br>
============ RESULTS ================<br>
Message size:      			 4096<br>
Message count:   			 1000<br>
Total duration:    			 1.945<br>
Average duration:   			 1.418<br>
Minimum duration:   		              0.000<br>
Maximum duration:   		              25.000<br>
Standard deviation: 			 1.282      <br>
Message rate:  			              514138     msg/s<br>
=====================================<br>
</body>
Goals:<br>
o	By using this you can learn how to implement IPC in different ways.<br>
o	It is helpful to choose better IPC method using there comparison<br>
To Be Done:<br>
•	Review C++ for performance issues related to serialization because C# custom serialization is faster<br>
•	Make multithreaded tests (consider single channel memory issues)<br>
•	Use all method in one program to give best for accuracy and speed. <br>
•	Write and test named pipe transport for open sources which lack it, make tests.<br>
•	Shuffle tests and shuffle data, investigate CPU cache influence<br>
•	Make tests of managed Protobuf<br>

.
