
---

### 📌 What are percentiles?

Percentiles describe **how fast an API responds for a percentage of users**.

|Percentile|Meaning|Interview Style Explanation|
|---|---|---|
|**P50**|50th percentile|Median latency: what a _typical_ user sees|
|**P95**|95th percentile|The slowest 5% of requests → performance issues for some|
|**P99**|99th percentile|Worst-case **tail latency** experienced by very few users|

📍Useful because **average latency can hide bad user experiences**.

---

### ⚙️ How are percentiles calculated?

1. Collect response times within a time window
2. Sort from fastest → slowest
3. Select the percentile position
    - P50 → 50th percentile value
    - P95 → 95th percentile value
    - P99 → 99th percentile value
        

📌 They are **not averages**  
They are **directly taken values** from sorted data.

---

### 🧠 Why do we care about P95 / P99?

They show **performance degradation in real environments** due to:

- Network delays
- Database spikes / slow queries
- Cold starts / cache misses
- External dependency slowness
- Heavy payload orders
- Locking/contention under load
    
Companies track P99 because:

> Even 1% of users can be millions of requests at scale.

---

### 📊 Example (5 data points)

Data: `200, 400, 600, 800, 1200 ms`

|Percentile|Value|Explanation|
|---|---|---|
|**P50**|600 ms|Middle value (3rd request)|
|**P95**|1200 ms|Near-worst tail|
|**P99**|1200 ms|Same tail (small dataset)|

With a small dataset, high percentiles often point to the **slowest element**.

---

### ❓ Are percentiles configured?

No.  
Percentiles are **calculated**, not set.  
What _is_ configured is **alert thresholds**, e.g.:

> Alert when P95 > 400ms for 5 minutes

---

### 🧩 Observability Tools Use Percentiles

Grafana, DataDog, NewRelic, Dynatrace, Kibana, CloudWatch:

- Calculate percentiles in rolling time windows
- Help detect **spikes, jitter & outliers**
    

---

### 🏁 TL;DR for Interview

> “Percentiles help measure real user latency.  
> P50 represents typical performance.  
> P95 and P99 reveal **tail latency** — the worst user experiences caused by occasional slow database queries, network issues, or dependency delays.  
> Percentiles are calculated from sorted response times — not averages — and help teams set alerts and optimize systems for consistency, not just speed.”

---

If you want, I can also provide:  
✔ A quick page on **improving P99 latency**  
✔ Interview questions and answers on performance and monitoring  
✔ Topics to cover for **Senior Node.js / System Design interviews**

Would you like me to prepare a **one-page PDF** version of this cheat-sheet?