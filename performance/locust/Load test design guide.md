


# Load Test Types

- **Smoke / Sanity Test**
    - **Purpose:** Quick check if the server responds
    - **Typical Behavior:** Very small number of users (1–10)
    - **Typical Duration:** **5–15 minutes** – just enough to confirm basic functionality
    
- **Light Load / Baseline Test**
    - **Purpose:** Observe how the server behaves under normal usage
    - **Typical Behavior:** Small percentage of expected users (5–20% of daily average)
    - **Typical Duration:** **30 minutes – 2 hours** – long enough to capture steady-state performance
    
- **Peak / Stress Test**
    - **Purpose:** Test limits and find the breaking point
    - **Typical Behavior:** High number of concurrent users (2–5× normal traffic)
    - **Typical Duration:** **15–60 minutes** – enough to push system to breaking point, but usually short to avoid prolonged outages
    
- **Soak / Endurance Test**
    - **Purpose:** Test stability over a long period
    - **Typical Behavior:** Average load sustained over an extended period (hours)
    - **Typical Duration:** **4–24 hours or more** – depending on how long you want to validate reliability
    
- **Spike Test**
    - **Purpose:** Observe server response to sudden traffic surges
    - **Typical Behavior:** Very rapid increase in users to see how the server handles spikes
    - **Typical Duration:** **5–30 minutes** – sudden bursts, usually multiple quick spikes in that window


# Calculate Concurrency Example
## Light Load / Baseline Test
**Purpose:** Observe how the server behaves under normal usage
**DAU:** 400  users
**Typical Behavior:** 
+ 5–20% of daily average
+ `(400 x 20) / 100 = 80 user`
**Duration:** 2 hours
**Concurrency:**
```less
Active hours: 2 hours (given)

Average session length: let’s assume 5 minutes (same as before)

Total users in test: 80 users

Traffic spread evenly over 2 hours (baseline behavior)
```
Total test duration:
```less
2 hours = 7200 seconds
```
Arrival rate:
```less
80 users / 7200 sec ≈ 0.011 users/sec
```
Concurrency:
```less
Concurrency = arrival_rate × average_session_time
5 minutes = 300 seconds
Concurrency = 0.011 × 300 ≈ 3.3 users
```