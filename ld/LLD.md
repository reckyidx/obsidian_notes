
1. search for books with author, purchase, track of inventory, handle payment transaction
2. Design lift system (https://freedium.cfd/https://medium.com/geekculture/system-design-elevator-system-design-interview-question-6e8d03ce1b44)
3.  System Design - https://medium.com/@choudharys710/5-essential-system-design-questions-every-developer-should-know-ii-eb15fea83d53
4. Newsfeed systemdesign - 
5. Distributed locking
6. Replication lag
7. How to scale an application from 100 to 1 million requests per second
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
8. Simulate a queue with Promises (FIFO async task runner)
   
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