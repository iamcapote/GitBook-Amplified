---
icon: people-roof
description: >-
  Ensuring the security of the governance process is paramount to protect the
  protocol from malicious activities and unintended consequences.
---

# Governance Security Model

## Execution Timelocks

**Purpose**:

* Provide a buffer period to detect and prevent malicious proposals before they are executed.
* Allow stakeholders to take emergency actions if necessary.

**Timelock Durations**:

* **Standard Proposals**: 2-day timelock.
* **High-Risk Proposals**: May have extended timelocks (e.g., 5 days) for critical changes.
* **Emergency Proposals**: May have reduced timelocks to enable swift action.

## Emergency Protocols

To address urgent situations such as protocol hacks or liquidity drains, Amplified implements emergency protocols:

* **Emergency Pause Mechanism**:
  * **Activation**: Can be triggered by a multi-signature (multi-sig) group known as the Emergency Council.
  * **Function**: Pauses critical protocol functions (e.g., deposits, withdrawals) to prevent further damage.
* **Emergency Proposals**:
  * **Fast-Track Process**: Shortened discussion and voting periods.
  * **Timelock Bypass**: May bypass standard timelocks for immediate execution.
  * **Approval Requirements**: Higher approval thresholds to ensure consensus.

## Risk Management and Mitigation

**Security Measures**:

* **Smart Contract Audits**: Regular audits by reputable firms to identify vulnerabilities.
* **Bug Bounty Programs**: Incentivize community members to report security issues, with rewards proportional to the severity of the vulnerabilities.
* **Real-Time Monitoring**: Continuous monitoring of protocol activities to detect anomalies.

**Decentralized Security**:

* **Emergency Council**:
  * Composed of trusted community members, developers, and security experts.
  * Holds limited but critical powers to act swiftly in emergencies.
* **Multi-Signature Controls**:
  * Critical functions require multiple approvals to execute.
  * Reduces the risk of single-point failures or malicious actions.

**Governance Safeguards**:

* **Proposal Filters**: Automated checks to prevent malicious proposals from entering the voting process.
* **Veto Mechanism**: Emergency Council can veto malicious proposals during the timelock period.
