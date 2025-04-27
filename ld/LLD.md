
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