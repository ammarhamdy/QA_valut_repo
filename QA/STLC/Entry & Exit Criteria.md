# **Entry & Exit Criteria in Test Planning Phase**

When you start any SDLC or STLC phase, you define **entry criteria** (what must be ready before the phase starts) and **exit criteria** (what must be true before the phase is considered complete). 

This ensures you don’t start too early or finish too early.


## **Entry Criteria (Before Test Planning Can Start)**

### **1. Completed [[Requirement Traceability Matrix (RTM)]]**

This means:
- All requirements (functional + non-functional) are documented.
- Each requirement has a unique ID.
- The RTM is mapped at least **requirements → test conditions** (initially).

Why this is needed?
- You can’t plan testing if you don’t know what you are testing.
- RTM ensures no requirement is missed in your test planning.

**Example:**

|Req ID|Requirement Description|Test Condition|
|---|---|---|
|R1|User login|Validate login with valid/invalid inputs|

If this matrix is not ready → your test scope will be unclear.

### **2. Initial Risk Analysis**

This means:
- The QA team has reviewed the product and identified **high-risk areas**.
- Risks include: functional complexity, security risks, performance risks, integrations, unclear requirements, etc.

Why needed?
- Risk analysis affects:
    - Test strategy
    - Test prioritization
    - Resource allocation
    - Test effort estimation

**Example:**
- Payment module → high risk → more testing effort, senior testers, detailed scenarios
- Settings page → low risk → basic validation only

Without risk analysis, your planning may be unrealistic or incomplete.


----

## **Exit Criteria (When the Test Planning phase is complete)**

### **1. Approved Test Plan**

The Test Plan must be:
- Written
- Reviewed
- Approved by:
    - QA Lead / Manager
    - PM / Product Owner
    - Possibly Dev Lead or Architect

The Test Plan includes:
- Scope (In-scope, Out-of-scope)
- Test strategy (approach)
- Test environment
- Test schedule
- Risks & mitigations
- Tools
- Team & responsibilities
- Deliverables
- Metrics

Once approved → you can start the Test Design phase.


### **2. Resource Commitments**

This means your test plan is not just “on paper”—but **management has agreed to provide required resources**, such as:

#### **Human Resources**
- Number of testers
- Senior/Mid/Junior mix
- Availability (full time? part time?)

#### **Environment & Tools**
- Test environment ready to create or scheduled to be created
- Test devices (Android phones, iPhones, laptops)
- Automation tools or licenses if needed
- Jira access, Test management tool access

If resources are not committed → planning is useless.

## **Example:**  
You planned for 3 testers for 2 weeks.  
Management confirms 3 testers will be available.  
✔ Now planning can officially finish.

If management says “sorry only 1 tester available”, then planning must be updated again.


## **Summary Table**

| Phase     | Criteria              | Meaning                                                |
| --------- | --------------------- | ------------------------------------------------------ |
| **Entry** | Completed RTM         | Requirements are fully mapped → testing scope is clear |
|           | Initial Risk Analysis | Risks identified → helps build a realistic plan        |
| **Exit**  | Approved Test Plan    | Stakeholders agree on the testing approach             |
|           | Resource Commitments  | Testers, environments, devices, tools are guaranteed   |

