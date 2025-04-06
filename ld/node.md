Built on reactor pattern with the help of demultiplexer
To acheive concurrency - do not block slow sync code
multi theread will block initiated theread until i/o received from user or system. it causes memory utilization

Non -blocking
	1. does not block execution
	2. user connected to same thread using busy waiting. busy waiting is kind of polling algorithm
Event Demultiplexer
	3. Source -> demultiplexer (callback) -> 
Libuv
Low class  level of abstraction created in C and process below operation
		1. Create API for event loop
		2. manage event queue
		3. run async i/o ops
		4. queue other task