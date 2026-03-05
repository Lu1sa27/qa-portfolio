# QA Strategy

## General Objective

Define a common framework to plan, execute, and control Quality Assurance activities across all projects at **Name**, ensuring reliable, stable products aligned with client expectations.

---

## Scope

This strategy applies to all systems, applications, and services developed or maintained by **Name**, including:

Example:
- Web Applications
- Mobile Applications
- APIs and Backend
- Internal and client projects
- Phases from requirements analysis to maintenance

---

## QA Strategy Principles

1. **Prevention before detection**  
   QA is involved from the beginning of the development lifecycle.

2. **Cross-team collaboration**  
   QA works together with Development, Product, and DevOps teams.

3. **Strategic automation**  
   Repetitive or critical tests should be automated whenever possible.

4. **Continuous measurement**  
   Quality metrics are used to continuously improve the QA process.

5. **Shared quality culture**  
   Quality is the responsibility of the entire organization.

---

## Standardized Testing Processes

1. QA Planning and Strategy  
2. Requirements Analysis  
3. Test Design  
4. Test Execution  
5. Defect Management  
6. Closure and Continuous Improvement  

See also: **QA Process and Lifecycle Documentation**

---

## Types of Testing Included

### Functional Testing

- Unit Testing
- Integration Testing
- System Testing
- User Acceptance Testing (UAT)

### Non-Functional Testing

- Performance Testing
- Security Testing
- Usability Testing
- Compatibility Testing

### Automation

- API Testing
- Regression Testing
- Smoke Tests

---

## Tools and Technologies

### QA Management

Example:
- Jira
- Zephyr

### API Automation

Example:
- Postman
- Newman

### Performance

Example:
- JMeter
- K6

### Security

Example:
- Charles Proxy
- AWS Services

---

## Quality Metrics

### Test Cases

**Total number of test cases**  
Measures the total volume of tests designed to validate functional and non-functional requirements.

**Test execution coverage vs planned tests**  
Evaluates the level of compliance with the test plan.

Formula:

(Executed test cases / Planned test cases) × 100


**Percentage of successful test cases**  
Indicates product stability and quality during execution.

Formula:

(Passed test cases / Executed test cases) × 100


---

### Defects

**Total number of reported defects**  
Reflects the total number of issues found during the testing cycle.

**Number and severity of defects found and resolved**  
Allows analysis of issue severity and the development team’s response capacity.

Breakdown example:

- Critical
- Major
- Minor

**Defects found by stage**  
Measures the effectiveness of the QA process by identifying defects in earlier stages of the lifecycle.

Stages may include:

- Requirements analysis
- Development
- QA testing
- Production

**Reopened defect rate**  
Indicates the quality of fixes.

Formula:

(Reopened defects / Closed defects) × 100

---

### Process

**Stakeholder or client satisfaction**  
Evaluated through surveys or feedback after the testing cycle is completed.

**QA process effectiveness**  
Determined by comparing defects detected during QA versus defects detected in production.

Formula:

(QA defects / (QA defects + Production defects)) × 100

---

## Global Acceptance Criteria

- 100% of critical requirements covered
- Zero blocking defects open at release
- Evidence documented and stored in the QA repository
- Final quality report validated by the QA Lead