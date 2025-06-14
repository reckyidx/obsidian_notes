### About LLD
	A phase in software development process where detailed system components and thier interaction are specified. it involves converting HLD into more detailed blueprint addressing their specific algorithm, data structure and interfaces. and which groups data and behaviours into object.
		diffreent component
			1. object oriented principle 
			2. process of analyzing and design
			3. design pattern 
			4. UML diagram 
			5. solid principle


	
![[Pasted image 20250614122148.png]]

#### OOP
	focuses on writing modular, scalable and reusable code.

### NOTES

2. search for books with author, purchase, track of inventory, handle payment transaction
3. Design lift system (https://freedium.cfd/https://medium.com/geekculture/system-design-elevator-system-design-interview-question-6e8d03ce1b44)
4.  System Design - https://medium.com/@choudharys710/5-essential-system-design-questions-every-developer-should-know-ii-eb15fea83d53
5. Newsfeed systemdesign - 
6. Distributed locking
7. Replication lag
8. How to scale an application from 100 to 1 million requests per second
	   Client
		  |
		CDN (Cloudflare)
		  |
		Load Balancer (NGINX / AWS ELB)
		  |
		[Node.js App Server] x 1000+
		  |
		Redis (for cache/session)
		  |
		DB Cluster (Postgres with read replicas or NoSQL like DynamoDB)
		  |
		Queue (Kafka/RabbitMQ)
		  |
		Worker Nodes
9. Simulate a queue with Promises (FIFO async task runner)
   
```
   class TaskQueue {
  constructor() {
    this.queue = [];
    this.running = false;
  }

  // Add a task to the queue
  add(task) {
    this.queue.push(task);
    this.run(); // trigger execution
  }

  // Core runner: executes one task at a time
  async run() {
    if (this.running) return;
    this.running = true;

    while (this.queue.length > 0) {
      const task = this.queue.shift(); // FIFO
      try {
        await task(); // wait for it to complete
      } catch (err) {
        console.error("Task error:", err);
      }
    }

    this.running = false;
  }
}

```

```
const queue = new TaskQueue();

// Simulated async tasks
function createTask(name, time) {
  return () =>
    new Promise((resolve) => {
      console.log(`Starting: ${name}`);
      setTimeout(() => {
        console.log(`Finished: ${name}`);
        resolve();
      }, time);
    });
}

// Add tasks
queue.add(createTask("Task 1", 1000));
queue.add(createTask("Task 2", 500));
queue.add(createTask("Task 3", 200));
```
10. https://github.com/prasadgujar/low-level-design-primer/blob/master/questions.md
11. 