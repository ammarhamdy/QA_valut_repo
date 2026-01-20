
# Throughput

Throughput is the actual rate at which work, data, or products are successfully processed, transmitted, or produced within a specific timeframe, measuring efficiency by focusing on ==successful== output rather than just maximum potential.


# Bandwidth
Bandwidth is the **maximum rate at which data can be transferred** from one point to another over a network or communication channel.

> Bandwidth = data capacity per unit time

| Term           | Meaning                             |
| -------------- | ----------------------------------- |
| **Bandwidth**  | Maximum possible data transfer rate |
| **Throughput** | Actual data transferred             |
| **Latency**    | Delay before data starts moving     |


# Bandwidth vs Rate Limiting
- **Bandwidth limit** → total data volume per second
- **Rate limit** → number of requests per second


# RPS (Requests Per Second)
RPS measures the throughput of your application. 

> It is the total number of successful requests your server completes in one second.

**In the Table:** Look for the "Current RPS" column. 
This shows the live speed of each specific endpoint.

**In the Chart:** The Total Requests per Second graph shows a green line.

**Health Check:** If you increase the number of users but the green line (RPS) stays flat, your server has hit its "==bottleneck==" and cannot handle more traffic.


# Response Time Percentiles (The "Real" User Experience)

A percentile tells you:
> **X% of requests completed in ≤ Y milliseconds**

Example:
- **95th percentile = 450 ms**

Means:
> 95% of requests finished in **450 ms or faster**  
> 5% were **slower than 450 ms**

|Percentile|Meaning|Why it matters|
|---|---|---|
|**50% (p50)**|Median response time|Typical user|
|**75% (p75)**|Upper-normal range|Performance consistency|
|**90% (p90)**|Slow users start here|Early warning|
|**95% (p95)**|SLA metric|Most common SLO|
|**99% (p99)**|Worst real users|Detect tail latency|


# Average Response Time
The Average (found in both the table and the yellow line on the charts) is the mathematical mean of all response times.

**What it tells you:** The general speed of the system.

**The Trap:** Averages can be misleading. If half your users get 100ms and the other half get 1,900ms, the average is 1,000ms, which doesn't represent anyone's actual experience.


# Important to notice

| **Metric**   | **Good Sign**                         | **Bad Sign**                                            |
| ------------ | ------------------------------------- | ------------------------------------------------------- |
| **RPS**      | Increases as you add more users.      | Stays flat while users increase (Saturated).            |
| **Average**  | Stays low and stable (e.g., < 500ms). | Gradually climbs as the test goes on.                   |
| **95%ile**   | Close to the Median/Average.          | Much higher than the Median (Inconsistent performance). |
| **Failures** | Stays at 0.                           | Increases (Server is crashing or rate-limiting).        |