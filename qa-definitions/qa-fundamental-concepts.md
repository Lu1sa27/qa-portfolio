# QA Fundamental Concepts

This section contains key **Quality Assurance concepts** that provide a foundation for understanding testing strategies, processes, and best practices in software development.

---

# Quality Assurance vs Quality Control

Although often used interchangeably, **Quality Assurance (QA)** and **Quality Control (QC)** represent different aspects of quality management.

### Quality Assurance (QA)

Quality Assurance focuses on **preventing defects** by improving development and testing processes.

It is **process-oriented** and aims to ensure that the right methodologies, standards, and practices are followed throughout the software lifecycle.

Examples of QA activities:

- Defining testing strategies
- Establishing QA processes
- Reviewing requirements
- Creating quality standards
- Process improvement initiatives

### Quality Control (QC)

Quality Control focuses on **detecting defects** in the actual product through testing activities.

It is **product-oriented** and involves verifying that the system behaves as expected.

Examples of QC activities:

- Test execution
- Defect reporting
- Validation of fixes
- Test result analysis

---

# Types of Testing

Testing can be categorized based on the **purpose of the validation being performed**.

### Functional Testing

Validates that the system behaves according to the defined requirements and business rules.

Examples:

- Login validation
- Form submissions
- API responses
- Business logic verification

### Non-Functional Testing

Evaluates system attributes such as **performance, reliability, usability, and security**.

Examples:

- Performance testing
- Security testing
- Usability testing
- Compatibility testing

### Regression Testing

Ensures that **existing functionality continues to work correctly after changes** such as bug fixes or new features.

### Smoke Testing

A small set of critical tests executed to verify that **the system is stable enough for further testing**.

---

# Test Levels

Test levels represent the **different stages at which testing activities occur** during the software development lifecycle.

### Unit Testing

Tests individual components or functions in isolation.

Typically performed by developers.

### Integration Testing

Validates interactions between integrated components or services.

Example: API integrations or database interactions.

### System Testing

Evaluates the **complete and integrated system** to ensure it meets functional and non-functional requirements.

### User Acceptance Testing (UAT)

Testing performed by **end users or stakeholders** to confirm the system meets business needs.

---

# Defect Lifecycle

The defect lifecycle defines the **different states a defect passes through from discovery to closure**.

Typical defect states include:

1. **New** – The defect is reported and logged.
2. **Assigned** – The defect is assigned to a developer.
3. **In Progress** – The issue is being investigated or fixed.
4. **Resolved** – The developer provides a fix.
5. **Retest** – QA verifies the fix.
6. **Closed** – The defect is confirmed as fixed.
7. **Reopened** – The issue persists after verification.

Proper defect lifecycle management ensures **clear communication and traceability between QA and development teams**.

---

# Risk-Based Testing

Risk-Based Testing prioritizes testing efforts based on the **potential impact and likelihood of failures**.

Instead of testing everything with the same intensity, QA focuses on **areas that present the highest risk to the business or system stability**.

### Risk evaluation factors

- Business impact
- Frequency of use
- System complexity
- Historical defect data
- Integration dependencies

### Benefits

- Efficient use of testing resources
- Faster identification of critical issues
- Better alignment with business priorities

---

# Test Environments

A **test environment** is the infrastructure where testing activities are executed.

Different environments support different stages of development and validation.

### Common environments

**Development Environment**

Used by developers for initial coding and unit testing.

**Testing / QA Environment**

Used by QA teams to execute functional and integration tests.

**Staging Environment**

A production-like environment used for final validation before release.

**Production Environment**

The live environment used by end users.

Maintaining **environment stability and configuration consistency** is essential for reliable testing results.

---

### Best practices

- Avoid using sensitive production data
- Maintain versioned datasets
- Automate test data creation when possible
- Ensure data consistency across environments

---

# Summary

Understanding these foundational QA concepts helps teams:

- Build better testing strategies
- Improve collaboration between QA and development
- Prioritize testing efforts effectively
- Deliver higher-quality software