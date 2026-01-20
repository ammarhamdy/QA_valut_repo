
https://docs.qase.io/general/get-started-with-the-qase-platform/test-cases
---

# What is a test case in software testing?

A test case contains all the details about our test. 
In `Qase`, a test case is a specific set of instructions and conditions that outline a test to be carried out successfully.

It includes testing procedures, necessary inputs, execution conditions, and expected results to achieve a testing objective.

In `Qase`, you can define various parameters and expected outcomes of a particular testing scenario.


# Basic Fields – Test Case Properties

|**No.**|**Field**|**Description**|
|---|---|---|
|**1**|**Title**|Define the name of a test case.|
|**2**|**Status**|Can be **Active**, **Draft**, or **Deprecated**.|
|**3**|**Description**|Additional details for more context about a test case.|
|**4**|**Suite**|Choose which Test Suite the new case belongs to.|
|**5**|**Severity**|Can be **Trivial**, **Minor**, **Normal**, **Major**, **Critical**, **Blocker**, or **Not Set**.|
|**6**|**Priority**|Can be **Low**, **Medium**, **High**, or **Not Set**.|
|**7**|**Type**|Select what type of testing is applicable for the test case.|
|**8**|**Layer**|Pick a layer of the test case: **End-to-End**, **API**, or **Unit Test**.|
|**9**|**Is Flaky**|Mark the test case as flaky if it is unstable.|
|**10**|**Milestone**|Select whether the test case is related to a Milestone (created separately).|
|**11**|**Behavior**|Can be **Destructive**, **Negative**, **Positive**, or **Not Set**.|
|**12**|**Automation Status**|Choose between **Manual** and **Automated**.|
|**13**|**To be Automated?**|Checkbox available only when Automation Status = **Manual**.|
|**14**|**Is Muted?**|Checkbox to mark tests as muted; muted test failures do not impact overall test run status.|