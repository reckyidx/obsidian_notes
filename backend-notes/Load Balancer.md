
 - Operates at transport layer of the OSI(open system interconnection) model
 - To distribute network traffic across multiple server effeciently
 - optimize resource utilization, enhance system performance, and ensure high availability and fault tolerance
 - Algorithm (round robin, least connection) 
 - Different type  - Application, network
		 - Application : Http header, cookie and URL 
		 - Network: TCP & UDP
 - Pros: High performance and low latency, suitable for sharing UDP and TCP efficiently,

### Algorithm
#### Static Load Balancing
1. Round Robin
	- Simple load balancing technique where request  distributed across multiple server in a sequential manner
	- pro: when all server have similar capacity and performance
2. Weighted Round Robin
	 - Same as round robin but it provides weighted score (depends on req distribution)
	 - Pros: When server have different config, utilize server max power, prevents smaller server overloading
	 - Cons: complexity, Maintainence
3. Source IP Hash 
	 - Req originated from same source IP are consistently directed to same server
	 - Pro: Focuses on session like online banking where customer stick to same server
	 - cons: uneven load distribution, 

#### Dynamic Load Balancing
1. Least Connection Method
	 - Assign new request to least connection active server
	 - pros: Balanced load, dynamic
	 - example: video streaming, larger file upload
2. Least Response Time Method
	 - directing new requests to the server with the quickest response time
	 - Pro: heavy, fluctuating user traffic where response time matters, ecommerce and streaming
3. Resource Based
	 - incoming requests based on the current resource availability of each server, such as CPU usage, memory, or network bandwidth
	 - Pro: applications that perform CPU-intensive or memory-heavy tasks




   