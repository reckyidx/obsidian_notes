
Initial Thoughts
 - what we are building
 - how many users
 - what not required

Identify problem type
- HLD - infra, scaling, service
- lld - class, schema, method, DB

Function Requirement
- Crud, Sync/Async operation, real time, eventual, api is required

Non Functional Requirement
- scale, availability, latency, consistency, security, cost constraints

Design database
- Sql Or NoSql, draft relationship, read heavy or write heavy, structured or unstructed data

Traffic & Growth Estimation
- Peak hours, scaling, data growth per day, request per second

API Contracts
- I/O - rest or gprc, async or sync, idompotency, error handling
  
Trade Offs
- sql or nosql, microservice or monolith, cache vs db hit, Strong vs eventual consistency (systems may temporarily show old data**, but **eventually all copies become the same)

Edge Cases
- db down, duplicate request, partial failure, retry stratergy

Final Stage 
**Clarify → Requirements → Constraints → Data → Scale → APIs → Failures → Trade-offs**