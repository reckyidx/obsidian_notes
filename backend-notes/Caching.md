Storing frequently accessed memory in the temporary location(server or client) to reduce the repeated data retrival, spped up response time.
Improves latency 

#### Website Caching

#### Server Caching
- acts as intermediate between browser and origin server
- Types - Object, opcode, CDN

#### Client side Caching
- Types - Browser request, JAVASCRIPT/AJAX, HTML 5
- JAVASCRIPT - Stores static assets (HTML, JS, CSS, images).
- Browser - managed at HTTP Header 

#### Remote Caching
 - Similar to server side which runs an application to serialize and deserialize the data.

#### How much data can be stored in cache
- 80/20 rule where 20 % object & 80 percentage of time (improves latency)


#### Cache cluster

- Genrally hash function  used to map each cache node (requestid - key & mod  - hash function) in order to find relevant cache node
- Adding one more cache node, data might not be equally distrubuted. so consistent caching in required inorder to solve data distribution problem
- 
![[Pasted image 20250803115359.png]]

#### Replacement policy

Data is temporarly stored so policy is required to maintain caching efficiently when capacity is full

 - First In First OUT - Stored data earlier are discarded as priority
 - Least Frequently Used -Removes the item that has been used the fewest number of times
   - A was used 5 times, B used 3 times, C used 1 time. Now insert D, and the cache is full. LFU removes **C**, the least frequently used.
 - Least Recently Used - Removes the item that **hasn’t been used for the longest time**.
	 -   You accessed A, B, C in that order. Now you access D, and the cache is full. LRU   removes **A**, the least recently used.

#### Update Policy

- Write Through  - update DB and cache same time
- Write Around - Read the DB data and update cache simultaneously. there will be cache miss
- Write Back - Data is written only to cache first, then asynchronously to DB. if system crashes, it may lose some data


#### Tools
Redis, Memcahced, Varnish, Edge cached

#### Purpose
- performance enhancement, latency reduction, throughput increase, resource conservation, fault tolerance, load adaption, cross cut concern handling

#### Mechanism
- browser cache, in memory cache, distributed cache
#### Cache Key
act as cache indicator and fetch data in O(1)

#### Cache Expiration
cache info become expired over a certain period of time
- Time based, rate limited, on demand , data driven


Useful Links :     https://github.com/Devinterview-io/caching-interview-questions
	         https://pradyumnachippigiri.substack.com/p/caching-playbook-for-system-design