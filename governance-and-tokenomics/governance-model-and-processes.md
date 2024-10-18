---
icon: people-roof
cover: ../.gitbook/assets/Frame 19.png
coverY: 0
---

# Governance Model and Processes

## 1. Introduction

The decentralized finance (DeFi) ecosystem has transformed traditional finance by offering open, permissionless, and transparent services. Central to DeFi success is strong governance for sustainability, security, and community involvement. Amplified DeFi Protocol, a pioneering super vault for Liquid Staking Tokens (LST) and Liquid Rebase Tokens (LRT), boosts capital efficiency, APY, and Ethereum security.&#x20;

This section explores Amplified's governance model and its token, LLT, incorporating best practices from top DeFi protocols like Uniswap, AAVE, and Frax, covering decision-making, security, and community engagement strategies.

## 2. The Importance of Governance in DeFi

Effective governance is the cornerstone of any successful DeFi protocol. It ensures that the protocol remains sustainable, secure, and adaptable in a rapidly evolving ecosystem. Key reasons why governance is crucial include:

* **Sustainability**: Enables the protocol to adapt to market changes and technological advancements.
* **Security**: Protects user assets and the protocol from malicious activities.
* **Community Engagement**: Fosters active participation and aligns incentives among stakeholders.
* **Transparency**: Builds trust through open and transparent decision-making processes.
* **Decentralization**: Distributes control among participants, reducing the risks associated with centralization.

By studying the governance models of successful protocols like Uniswap, AAVE, Optimism, Arbitrum, and Frax, Amplified aims to implement a governance framework that is both robust and flexible.

## 3. Overview of Amplified's Governance Model

Amplified's governance model is designed to empower LLT holders with direct influence over key protocol decisions. It emphasizes decentralization, transparency, inclusivity, and security.

#### Core Principles

* **Decentralization**: Decisions are made collectively by LLT holders, minimizing central authority.
* **Inclusivity**: All LLT holders have the right to participate in governance processes.
* **Transparency**: Governance proposals and decisions are openly shared with the community.
* **Security**: Robust mechanisms are in place to safeguard the protocol during governance activities.
* **Efficiency**: Streamlined processes ensure timely decision-making without compromising thoroughness.

## 4. Governance Processes

Amplified's governance process is designed to facilitate efficient and inclusive decision-making while ensuring security and transparency.

### Proposal Types and Decision Models

Inspired by the governance models of leading DeFi protocols like AAVE, Amplified categorizes proposals into several types:

1. **Temperature Check (Temp Check)**: Initial proposals to gauge community interest and sentiment.
2. **Amplified Request for Comment (ARC)**: Detailed proposals that invite in-depth discussion and feedback.
3. **Amplified Improvement Proposal (AIP)**: Formal proposals ready for on-chain voting and implementation.
4. **Emergency Proposals**: Rapid-response proposals to address critical issues, such as security vulnerabilities.

Each proposal type follows a structured process to ensure thorough consideration and community engagement.

### Proposal Submission

**Eligibility**: Any LLT holder can submit a governance proposal.

**Requirements**:

* **Temp Check**: A brief outline of the proposed changes, rationale, and expected impact.
* **ARC**: A detailed proposal including technical specifications, risk assessments, and supporting data.
* **AIP**: A finalized proposal ready for on-chain voting, including technical payloads and execution plans.

**Submission Platform**: Proposals are submitted through the official governance portal and are open for community discussion on forums.

### Community Discussion

**Discussion Periods**:

* **Temp Check**: Minimum of 5 days for initial feedback and gauging interest.
* **ARC**: Minimum of 5 days for in-depth analysis, technical reviews, and community feedback.

**Engagement**:

* LLT holders are encouraged to participate actively by providing feedback, asking questions, and suggesting modifications.
* Proposal authors may adjust their proposals based on community input to build consensus.

### Voting Mechanisms

**Off-Chain Voting (Snapshot)**

* **Purpose**: To gauge community sentiment during the Temp Check and ARC stages without incurring gas fees.
* **Platform**: Snapshot or similar off-chain voting platforms.
* **Voting Period**: Typically 3 days.
* **Eligibility**: LLT holders with staked tokens (veLLT) can participate.

**On-Chain Voting**

* **Purpose**: Formal voting on AIPs that will implement changes in the protocol.
* **Platform**: On-chain governance contracts.
* **Voting Delay**: A 1-day delay after proposal submission before voting starts.
* **Voting Period**: Typically 3 days.
* **Eligibility**: LLT holders with staked tokens (veLLT) participate directly or through delegation.

**Voting Power**:

* Determined by the amount of staked LLT (veLLT) and enhanced by lockup periods.
* Delegated voting power is counted towards the delegatee.

### Quorum Requirements and Thresholds

Different proposal types and decisions may have varying quorum requirements and approval thresholds, ensuring appropriate participation and consensus for different levels of impact.

**Quorum Requirements**:

* **Strategy Rebalancing**:
  * Quorum: 2% of total voting power.
  * Approval Threshold: Simple majority (>50%).
* **Protocol Updates**:
  * Quorum: 5% of total voting power.
  * Approval Threshold: Supermajority (≥66%).
* **Protocol Whitelisting**:
  * Quorum: 3% of total voting power.
  * Approval Threshold: Simple majority (>50%).
* **General Proposals**:
  * Quorum: 1% of total voting power.
  * Approval Threshold: Simple majority (>50%).

**Notes**:

* **Quorum**: The minimum number of votes required for a proposal to be valid.
* **Approval Threshold**: The minimum percentage of votes in favor for the proposal to pass.

### Implementation and Execution

**Execution Timelocks**:

* **Standard Timelock**: A default period (e.g., 2 days) between proposal approval and execution, allowing for final reviews.
* **Emergency Timelock**: Shorter or no timelock for urgent actions to address critical issues.

**Execution Process**:

1. **Security Review**: Before execution, proposals undergo a final security review by designated auditors or security councils.
2. **Queuing**: Approved proposals are queued with the timelock contract.
3. **Execution**: After the timelock expires, proposals are executed automatically by the smart contracts or through designated executors.
4. **Monitoring**: The community and security teams monitor the execution for compliance and correctness.

## Conclusion

Amplified's comprehensive governance model integrates best practices from leading DeFi protocols to empower LLT holders, promote transparency, and ensure security. By actively involving the community in critical decisions, Amplified not only enhances its own protocol but also contributes to the maturity and resilience of the broader DeFi ecosystem
