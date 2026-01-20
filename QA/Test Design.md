
# What is Test Design?

**Test design** is the process of creating **test cases, test conditions, and test data** to verify that a system meets its requirements.

It’s basically the “bridge” between:

- **What the system should do** (requirements, user stories, specifications)
    
- **How you will check it** (test cases, scripts, automation).


Test design is the structured way of deciding _what to test, how to test, and with what data_. It ensures your automation framework is **efficient, covers all requirements, and avoids redundancy**.

---
# Key Elements of Test Design

1. **Test Conditions**
    
    - High-level aspects to test (e.g., “Login with valid credentials”).
        
2. **Test Cases**
    
    - Step-by-step actions + expected results (manual or automated).
        
    - Example: _Enter valid email + password → Expect: Dashboard page opens._
        
3. **Test Data**
    
    - Inputs needed to execute tests.
        
    - Example: `user@example.com / Password123`.
        
4. **Test Environment Setup**
    
    - Ensuring correct configurations (browsers, APIs, DBs, etc.) for running tests.

---
# Test Design Techniques

There are several standard techniques testers use (often asked in interviews):

- **Equivalence Partitioning (EP)**  
    Group inputs into valid/invalid sets to reduce test cases.  
    Example: If a field accepts 1–100, test with 5 (valid), 0 (invalid), 101 (invalid).
    
- **Boundary Value Analysis (BVA)**  
    Test at the edges of input ranges.  
    Example: Test 1, 100, 0, 101.
    
- **Decision Table Testing**  
    Useful when different input combinations give different outcomes.
    
- **State Transition Testing**  
    For systems where output depends on state changes (like login attempts).
    
- **Use Case Testing**  
    Based on user scenarios/end-to-end workflows.


---
# Why It Matters in Automation

- A well-designed test case = easy to **automate and maintain**.
    
- Prevents duplicate/unnecessary tests → saves execution time.
    
- Helps achieve **good coverage** with fewer, smarter test cases.

---
# Example

Let’s take a simple **Login Form** example and build a **mini Test Design Document**. This is the kind of exercise you may face in interviews.

## Test Design Example: Login Form

### Feature Under Test

User login functionality on a website/app.

### Requirements

1. User must enter a valid email and password.
    
2. Email must follow correct format (`user@example.com`).
    
3. Password must be at least 8 characters, with at least 1 uppercase, 1 number, 1 special character.
    
4. Invalid credentials should show an error.
    
5. Successful login redirects user to dashboard.

### Test Conditions

1. Login with valid credentials.
    
2. Login with invalid email format.
    
3. Login with correct email, wrong password.
    
4. Login with empty email field.
    
5. Login with empty password field.
    
6. Login with both fields empty.
    
7. Check password length and complexity rules.
    
8. Successful login should redirect to dashboard.


### Test Cases & Data

| **ID** | **Test Case**                               | **Input Data**                              | **Expected Result**                                  |
| ------ | ------------------------------------------- | ------------------------------------------- | ---------------------------------------------------- |
| TC01   | Valid login                                 | Email: `user@test.com`Password: `Passw0rd!` | User redirected to dashboard page                    |
|        |                                             |                                             |                                                      |
| TC02   | Invalid email format                        | Email: `usertest.com`Password: `Passw0rd!`  | Error: “Invalid email format”                        |
|        |                                             |                                             |                                                      |
| TC03   | Wrong password                              | Email: `user@test.com`Password: `Wrong123!` | Error: “Invalid credentials”                         |
|        |                                             |                                             |                                                      |
| TC04   | Empty email                                 | Email: _(blank)_Password: `Passw0rd!`       | Error: “Email is required”                           |
|        |                                             |                                             |                                                      |
| TC05   | Empty password                              | Email: `user@test.com`Password: _(blank)_   | Error: “Password is required”                        |
|        |                                             |                                             |                                                      |
| TC06   | Both fields empty                           | Email: _(blank)_Password: _(blank)_         | Error: “Email and Password are required”             |
|        |                                             |                                             |                                                      |
| TC07   | Password complexity check (too short)       | Email: `user@test.com`Password: `abc`       | Error: “Password must be at least 8 characters long” |
|        |                                             |                                             |                                                      |
| TC08   | Password complexity check (no special char) | Email: `user@test.com`Password: `Password1` | Error: “Password must include special characters”    |

### Notes

- This design includes **positive** and **negative** cases.
    
- Can be extended to include:
    
    - Brute force lockout (e.g., 5 wrong attempts = account locked).
        
    - Remember Me / Forgot Password flows.
        
    - Cross-browser/device testing.




