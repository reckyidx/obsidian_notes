
|Day|Focus Area|
|---|---|
|1-2|Event loop, async/await, callbacks, microtasks/macrotasks|
|3|Streams, Buffers, File system|
|4|Express.js deep dive + middleware pattern|
|5|Auth (JWT/OAuth), API security|
|6|Database (SQL vs NoSQL), indexing, query performance|
|7|System design basics, scaling patterns|
|8|Redis, caching, queues (BullMQ)|
|9|Docker, deployments, CI/CD|
|10|Testing (Jest, Supertest, mocking)|
|11|Node.js internals + performance optimization|
|12|Mock interviews + behavioral questions|
|13-14|DSA refresh + Leetcode/CodeSignal practice|
## 🧠 1. **Interview Questions by Topic**

### ✅ Node.js Core

- What is the Node.js event loop? Explain each phase.
    
- How does Node.js handle asynchronous I/O under the hood?
    
- What's the difference between `setImmediate()` and `process.nextTick()`?
    
- Explain backpressure in streams and how to handle it.
    
- When would you use `Buffer`, and how is it different from a regular string?
    

### ✅ Express / Web APIs

- How does middleware chaining work in Express?
    
- How do you handle centralized error handling in Express?
    
- How would you implement rate limiting in an API?
    
- What is the difference between `req.params`, `req.query`, and `req.body`?
    

### ✅ Auth / Security

- How does JWT-based authentication work?
    
- How do you prevent CSRF in an API that serves a web frontend?
    
- What is CORS, and how do you configure it safely?
    

### ✅ System Design

- Design a scalable URL shortener.
    
- How would you design an API for a real-time chat system?
    
- How do you handle file uploads at scale in a distributed system?
    
- What are the tradeoffs between monolithic and microservice architecture?
    

### ✅ Databases

- When would you choose SQL over NoSQL?
    
- How do you handle transactions in MongoDB?
    
- What are indexes and how do they affect performance?
    

### ✅ Testing / DevOps

- How would you test an Express route that has external API dependencies?
    
- How do you ensure test isolation when testing DB-related logic?
    
- What would your `Dockerfile` look like for a production Node.js app?
    

---

## 🧩 2. **Coding Challenge Topics (with Examples)**

### 🔹 Strings & Arrays

- Reverse words in a sentence (Leetcode 151)
    
- Longest substring without repeating characters (LC 3)
    

### 🔹 Hashmaps & Sets

- Two sum (LC 1)
    
- Group anagrams (LC 49)
    

### 🔹 Recursion / Backtracking

- Generate parentheses (LC 22)
    
- Subsets / combinations
    

### 🔹 Trees

- Binary tree level order traversal (LC 102)
    
- Lowest common ancestor
    

### 🔹 Graphs

- Clone a graph
    
- Topological sort
    

### 🔹 Misc.

- Debounce/throttle implementation in JavaScript
    
- Deep clone an object (handle circular refs too)
    

---

## 💻 3. **Quick Practice Tasks (Daily Drills)**

Here are some **daily mini-challenges** you can do in ~30 mins:

- Implement a simple in-memory cache with TTL
    
- Write a mock version of `setTimeout` using `setImmediate`
    
- Build a middleware logger for Express with color-coded logs
    
- Simulate a queue with Promises (FIFO async task runner)
    
- Write a file stream that uppercases text and saves it to a new file
    
- Write a rate limiter using Redis and Node.js
    
- Build a REST API for a blog (CRUD posts + search)
    
- Design a simple chat server using WebSockets
    

---

## ⚙️ 4. Want a custom test or mock interview?

I can:

- Build a **custom 90-min Node.js test** with MCQs + coding
    
- Simulate a **mock interview** (system design or tech round)
    
- Give **DSA drill sets** tailored to your weak points