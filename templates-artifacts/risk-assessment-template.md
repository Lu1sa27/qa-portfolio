# QA RISK ASSESSMENT – [Project Name]

---

## 1. Risk Assessment Objective

Identify potential risks that could impact system quality, stability, or release timelines.

The objective is to prioritize testing activities using **risk-based testing principles**.

---

## 2. Risk Identification Criteria

Risks are identified considering:

- Technical complexity
- Business impact
- Integration dependencies
- User exposure
- Security concerns
- Performance requirements

---

## 3. Risk Evaluation Method

Risks are evaluated using **Probability × Impact**.

| Level | Description |
|---|---|
| Low | Minor impact |
| Medium | Moderate impact |
| High | Major business impact |

---

## 4. Risk Assessment Matrix

| Risk ID | Category | Description | Probability | Impact | Risk Level |
|---|---|---|---|---|---|
| R1 | Integration | Third-party API failures | High | High | Critical |
| R2 | Data | Data validation issues | Medium | High | High |

---

## 5. Risk Mitigation Strategy

| Risk | Mitigation |
|---|---|
| API failures | Integration testing |
| Data validation | Boundary and negative testing |

---

## 6. Testing Prioritization

| Risk Level | Testing Focus |
|---|---|
| High | Extensive testing + automation |
| Medium | Functional + regression |
| Low | Basic validation |

---

## 7. Assumptions and Constraints

### Assumptions

- Environments available
- Requirements defined

### Constraints

- Limited testing time
- External dependencies