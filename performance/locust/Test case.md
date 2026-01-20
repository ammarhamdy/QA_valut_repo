

## First: Translate _1500 daily users_ into load numbers

>For daily usage 1500 users

Daily Active Users (DAU) ≠ concurrent users.

Rule of thumb (very common in load testing):
- **Peak concurrent users ≈ 5–10% of DAU**

So for **1500 DAU**:

| Type               | Users     |
| ------------------ | --------- |
| Average concurrent | ~30–50    |
| Peak concurrent    | ~75–150   |
| Stress target      | 2–3× peak |


# Baseline (Average Load)

- Purpose: verify normal behavior
- Users: **30**
- Spawn rate: **2 users/sec**
- Duration: **15–20 min**


