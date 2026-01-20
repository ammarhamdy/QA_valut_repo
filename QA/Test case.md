
A **test case** is a structured set of conditions to validate a feature. 
It ensures you check:

- **Preconditions** → What must be true before running the test
    
- **Test steps** → Actions the tester performs
    
- **Expected result** → What should happen if the system works correctly
    
- **Status** → Pass / Fail / Blocked (filled after execution)
    

And as you said, you need to cover:
- ✅ **Normal flow (happy path)**
- ⚠️ **Edge cases**
- ❌ **Negative scenarios**


# Example Test Cases
Feature: **User Login**

| Test Case ID | Test Scenario                             | Preconditions       | Test Steps                                                                   | Expected Result                                               | Status    |
| ------------ | ----------------------------------------- | ------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------- | --------- |
| TC001        | Valid login (normal flow)                 | User account exists | 1. Open login page 2. Enter valid username & password 3. Click "Login"       | User is logged in and redirected to dashboard                 | Pass/Fail |
|              |                                           |                     |                                                                              |                                                               |           |
| TC002        | Invalid password (negative)               | User account exists | 1. Open login page 2. Enter valid username + wrong password 3. Click "Login" | Error message shown: "Invalid credentials"                    | Pass/Fail |
|              |                                           |                     |                                                                              |                                                               |           |
| TC003        | Empty fields (negative)                   | None                | 1. Open login page 2. Leave username & password blank 3. Click "Login"       | Validation error shown: "Fields cannot be empty"              | Pass/Fail |
|              |                                           |                     |                                                                              |                                                               |           |
| TC004        | SQL injection attempt (negative/security) | None                | 1. Enter `admin' OR '1'='1` as username and any password 2. Click "Login"    | Login should fail, error shown, system not compromised        | Pass/Fail |
|              |                                           |                     |                                                                              |                                                               |           |
| TC005        | Long username input (edge case)           | None                | 1. Enter 256+ character username 2. Enter valid password 3. Click "Login"    | Error shown: "Username too long" or input is truncated safely | Pass/Fail |
|              |                                           |                     |                                                                              |                                                               |           |
| TC006        | Session handling (edge case)              | User is logged in   | 1. Log in successfully 2. Open app in another browser tab 3. Check session   | User stays logged in consistently, no conflict                | Pass/Fail |

# Coverage Explanation

- **Normal Flow** → TC001
    
- **Negative Scenarios** → TC002, TC003, TC004
    
- **Edge Cases** → TC005, TC006

>>⚡ Pro tip: Usually these test cases are documented in **Excel**, **Jira Xray**, **TestRail**, or similar tools.


