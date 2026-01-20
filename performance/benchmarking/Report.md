
**Project:** ....  
**Endpoint:** ....
**Date:** ....     
**Prepared by:** ...

* * *

# Summary

A short summary of results:
* ✓ API stable?
* ✓ Passed performance criteria?
* Key issues (if any)


* * *

## 2. **Test Environment**

| Item | Details |
| --- | --- |
| Client machine | Your hardware |
| Server environment | Production / Staging |
| Network | Wired / Wi-Fi |
| Tool | hey |
| Cookie auth | Yes/No |

* * *

## 3. **Test Scenarios & Results**

* * *

### ### **3.1 Smoke Test**

**Purpose:** Validate endpoint is reachable.

| Metric | Result |
| --- | --- |
| Requests | ______ |
| Concurrency | ______ |
| p50 | ______ |
| p90 | ______ |
| p95 | ______ |
| p99 | ______ |
| Errors | ______ |

**Notes:**

* * *

* * *

### ### **3.2 Light Load Test**

Simulate normal traffic.

| Metric | Result |
| --- | --- |
| Requests | ______ |
| p95 | ______ |
| p99 | ______ |
| Requests/sec | ______ |
| Errors | ______ |

**Notes:**

* * *

* * *

### ### **3.3 Stress Test**

Increase pressure until degradation.

| Metric | Result |
| --- | --- |
| Requests | ______ |
| Concurrency | ______ |
| p95 | ______ |
| p99 | ______ |
| Errors | ______ |
| Breaking point (p99 > 1s or >2% errors) | ______ |

* * *

### ### **3.4 Peak Load Test**

Simulate sudden high traffic.

| Metric | Result |
| --- | --- |
| Requests | ______ |
| Concurrency | ______ |
| p95 | ______ |
| p99 | ______ |
| Requests/sec | ______ |
| Error rate | ______ |

* * *

### ### **3.5 Soak Test**

Long-duration performance.

| Metric | Result |
| --- | --- |
| Duration | ______ |
| Avg response time | ______ |
| p95 | ______ |
| Error % | ______ |
| Memory/CPU drift? | Yes/No |

* * *

## 4. **Latency Percentiles Comparison**

Fill in after all tests:

| Test | p50 | p90 | p95 | p99 |
| --- | --- | --- | --- | --- |
| Smoke | ___ | ___ | ___ | ___ |
| Light | ___ | ___ | ___ | ___ |
| Stress | ___ | ___ | ___ | ___ |
| Peak | ___ | ___ | ___ | ___ |
| Soak | ___ | ___ | ___ | ___ |

* * *

## 5. **Server Stability Analysis**

* CPU issues?
    
* Memory growth?
    
* Slow database?
    
* CDN issues?
    
* Sessions expired?
    

Notes:

* * *

* * *

## 6. **Conclusions**

* Passed / Failed performance requirements
    
* Recommended optimizations:
    
    * Caching
        
    * DB indexing
        
    * CDN config
        
    * Code fixes
        
    * Load balancer tuning
        