# Aaron Brown — Cybersecurity Portfolio

# Vulnerability Governance & Risk Acceptance Platform

> A working reference implementation of an enterprise vulnerability-governance operating model — connecting technical findings to risk prioritization, accountable ownership, remediation SLAs, security exceptions, and time-bound risk acceptance.

**Live Demo:** https://vulnerability-governance-platform.onrender.com/

---

## Overview

Vulnerability management is not simply a scanner-output problem.

Organizations have to answer harder questions:

- Which findings actually represent the greatest enterprise risk?
- Who owns remediation?
- How quickly should remediation occur?
- Which findings are overdue?
- When are compensating controls sufficient?
- When can risk be temporarily accepted?
- Who has authority to approve that decision?
- How should the same risk be communicated to executives, security teams, and application owners?

This project models that operating layer.

Rather than building another vulnerability scanner, the platform starts with vulnerability findings and demonstrates how they can be converted into:

**Finding → Risk → Owner → Remediation → Exception → Decision → Monitoring**

The result is a working governance application designed around how enterprise security programs actually manage vulnerability risk.

---

## Live Application

### Launch the platform

**https://vulnerability-governance-platform.onrender.com/**

The application includes four primary governance experiences:

| View | Purpose |
|---|---|
| **Executive** | Enterprise risk posture and leadership-level metrics |
| **Security** | Prioritized vulnerability governance and remediation queue |
| **Application Owner** | Owner-specific remediation accountability |
| **Exception Register** | Security exception and risk-acceptance lifecycle |

Individual vulnerabilities can also be opened as dedicated **Finding Detail** records showing the technical, business, scoring, remediation, and risk-acceptance context behind the finding.

---

## What This Project Demonstrates

This project focuses on the layer between **security tooling** and **security governance**.

### Risk-Based Prioritization

Findings are not prioritized solely by CVSS.

The scoring engine enriches technical severity with:

- CVSS severity
- CISA KEV-style known-exploited context
- Internet exposure
- Exploit maturity
- Business criticality
- Environment
- Compensating controls
- Approved exception context

The resulting score drives a governance priority and remediation SLA.

```text
Technical Severity
       +
Exploit Context
       +
Exposure
       +
Business Criticality
       +
Environment
       -
Compensating Controls
       -
Approved Exception Context
       │
       ▼
Enterprise Risk Score
       │
       ▼
Priority + Remediation SLA

Why I Built This

The most interesting security problems often occur after a tool identifies a finding.

Someone still has to determine:

how important it is,
who owns it,
how quickly it must be addressed,
whether compensating controls change the risk,
whether an exception is justified,
who can accept the residual risk,
when that decision expires,
and how leadership should understand the result.

This project demonstrates that layer.

It is less about finding vulnerabilities and more about building the governance system that turns vulnerability data into accountable security decisions.