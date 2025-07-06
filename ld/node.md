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

1. When to spawn a thread in node js?
		By default async & non blocking event in nature. CPU bound task can block the event loop on such scenario we can spawn new thread using worker_thread 
			- **Performing CPU-intensive operations**
				- complex calculations, image processing, or large data parsing
			- **Parallel processing is needed:**
				- multiple tasks can be executed concurrently, worker threads enable parallel execution, reducing overall processing time
			- **Avoiding blocking the event loop**
				- Long-running synchronous operations can halt the event loop. Worker threads allow these operations to run in the background, ensuring the event loop remains free to handle other requests.

2. What is oop not oops
	OOP(object oriented programming language) is a program paradigm based on concept of objects
		Principle
			- Encapsulation
			- Inheritance
			- Polymorphism (child class method override of its parent class.)
			- Abstraction
			- Multiple inheitance is not supported in js instead we can use composite class (ref of two class in constructor)
		Core Concepts
			- classes and object
			- Method creation
			- Data hiding
			- Code resuability
3. Bind
	- Building Partial Functions for Reuse. Say you have a logging utility where you want to reuse the same format but with different log levels
	  `function log(level, message) {
		  console.log(`[${level.toUpperCase()}]: ${message}`);
		}
		
		// Create partials using bind
		const infoLog = log.bind(null, 'info');
		const errorLog = log.bind(null, 'error');
		
		infoLog('User signed in');   // [INFO]: User signed in
		errorLog('Something broke'); // [ERROR]: Something broke
		`
	 - 