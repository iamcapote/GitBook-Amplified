---
icon: chart-mixed-up-circle-dollar
cover: ../../.gitbook/assets/Frame 3.png
coverY: 0
---

# Automated Liquidity Manager (ALM)

### Introduction

Amplified Protocol is an advanced liquidity management solution with an Active Liquidity Management (ALM) module, designed to optimize concentrated liquidity on Uniswap v3 and other AMM v3 platforms. Inspired by protocols like Arrakis, Amplified improves capital efficiency through decentralized, algorithm-driven market-making, helping liquidity providers (LPs) maximize earnings while reducing risks. Focused on Liquid Staking Tokens (LST) and Liquid Reward Tokens (LRT), it enhances liquidity efficiency by managing highly correlated assets. This document covers the problem statement, mechanics, and key features of Amplified’s ALM system and its impact on liquidity management.

### Problem Statement

#### 1. Limitations of Legacy AMMs

Traditional AMMs like Uniswap v2 lack the efficiency to compete with centralized exchanges due to their custodial nature and inefficiencies. Although AMMs have revolutionized decentralized trading, they often operate with one-size-fits-all bonding curves, which limit their capital efficiency. Market makers on these platforms cannot apply sophisticated strategies, leading to underutilized liquidity and higher costs for liquidity provision.

#### 2. Complexity of Concentrated Liquidity in AMM v3

Next-generation AMMs such as Uniswap v3 have introduced concentrated liquidity, enabling LPs to provide liquidity within specific price ranges. While this has increased capital efficiency, it also comes with increased complexity and risk for LPs. Without a sophisticated layer to automate and optimize liquidity management, the concentrated liquidity model struggles to compete with centralized market makers, which still provide the tightest spreads and most efficient liquidity allocations.

#### 3. Lack of Market-Making Infrastructure in DEXs

Centralized exchanges benefit from mature institutional market-making infrastructure, enabling efficient asset allocation and tighter spreads. Conversely, decentralized exchanges lack this level of sophistication. Amplified Protocol aims to bridge this gap by providing a decentralized, algorithmic, and automated solution for managing liquidity in Uniswap v3 and other AMM platforms, thus bringing CEX-level efficiency to decentralized trading environments.

#### 4. Capital Efficiency Across Concentrated Liquidity for LST/LRT Assets

Amplified Protocol focuses on maximizing capital efficiency for highly correlated assets, such as Liquid Staking Tokens and Liquid Reward Tokens. These assets typically maintain a stable relationship with each other, which makes them well-suited for concentrated liquidity strategies. By leveraging the correlation between LST and LRT assets, Amplified's built-in ALM module can significantly narrow the liquidity ranges, thereby increasing capital efficiency and reducing the need for excessive collateral. This approach ensures that liquidity is deployed more effectively, resulting in deeper pools and increased fee generation, all while minimizing the capital required to maintain these positions.

### Solution: Amplified Protocol

Amplified Protocol offers a trustless market-making infrastructure designed to run sophisticated algorithmic strategies on Uniswap v3. By utilizing Amplified Vaults, liquidity providers can enjoy active liquidity management in an automated, capital-efficient, non-custodial, and transparent manner.

#### Who Can Use Amplified?

* **Liquidity Providers**: Retail LPs, institutional funds, and Web3 protocols can all utilize Amplified ALM to actively manage their concentrated liquidity on Uniswap v3. LPs retain full custody over their funds and can withdraw them at any time.

Amplified empowers these stakeholders through a choice of three different vault management options:

1. **Trustless Vaults**: Managed via smart contracts with pre-defined on-chain strategies, offering a similar model to Curve v2 but allowing for static or dynamic strategies. This enables fully trustless, automated liquidity management.
2. **Managed Vaults**: Operated by professional market makers who run sophisticated off-chain strategies, allowing LPs to access advanced market-making methods.
3. **Self-Managed Vaults**: Designed for advanced users, these vaults are managed directly by the user, providing full control over the deployed strategies.

### Key Concepts of Active Liquidity Management

#### 1. Concentrated Liquidity Management for Correlated Assets

Concentrated liquidity allows LPs to allocate liquidity within specific price bands rather than across the entire price curve, increasing efficiency. For highly correlated assets like LST and LRT, managing liquidity within a tighter range can be particularly effective, as the price movements tend to follow similar trajectories, reducing the risk of being left with inactive liquidity.

Amplified Protocol simplifies this by managing liquidity positions automatically, allowing LPs to benefit from concentrated liquidity without the burden of manual monitoring. By focusing on correlated assets, Amplified further optimizes the usage of liquidity, resulting in lower capital requirements and reduced risk exposure.

#### 2. Rebalancing and Dynamic Adjustments

The core of Amplified Protocol's ALM system is its rebalancing strategy, which dynamically adjusts liquidity ranges to maintain profitability and minimize risk.

* **Price Oracle Integration**: Reliable price oracles are integrated to track price movements and trigger rebalancing actions.
* **Dynamic Price Range Adjustments**: Using market volatility as a variable, Amplified adjusts liquidity ranges dynamically. For instance, the width of the range is increased for volatile assets to minimize impermanent loss, while it is tightened during periods of stability.
* **Mathematical Optimization**: The rebalancing algorithm optimizes liquidity based on expected trading volumes and price variance. The target is to maximize earnings by adjusting liquidity positions to minimize exposure to less profitable price ranges.
* **Multi-Tier Positions**: Amplified's ALM module manages liquidity across multiple fee tiers within AMM v3, allowing LPs to capture trading volume from different fee structures concurrently. This ensures efficient use of capital across varying trading environments, increasing fee capture potential.
* **Cross-Pool Rebalancing**: Amplified also includes the ability to rebalance liquidity across multiple pools with different asset pairs. This feature allows the protocol to dynamically shift liquidity to pools with higher yield potential, ensuring that capital is always positioned for optimal profitability.

#### 3. Passive vs Active LP Positions

* **Passive Positions**: LPs that prefer stability can opt for passive management. The protocol periodically adjusts liquidity ranges to keep liquidity active in the optimal zone.
* **Active Positions**: Advanced LPs can choose active management, which involves frequent rebalancing to ensure liquidity remains within tighter and more profitable bands, thereby increasing fee-earning potential.

Amplified empowers users with options that align with their risk preferences and liquidity goals.

### Amplified Vaults for LST and LRT Assets

Amplified Protocol introduces "Vaults," which aggregate liquidity from multiple LPs, allowing for more efficient management and rebalancing, particularly for correlated assets like Liquid Staking Tokens LST and LRT.

#### 1. Vault Structure

* **Multi-User Access**: Vaults aggregate assets from multiple users, thereby reducing costs and enabling smaller LPs to participate in active liquidity management.
* **Optimized Rebalancing**: By aggregating liquidity, Vaults minimize the cost of rebalancing, which is then optimized to trigger only during significant price shifts or when profitability metrics are met.
* **Non-Custodial Nature**: Depositors retain custody of their assets, with the ability to withdraw at any time.

#### 2. Liquidity Pool Examples for LST and LRT

* **Example 1: ETH-wstETH Liquidity Pool** For an ETH-wstETH pool, Amplified Vaults can maintain a tight liquidity band around the typical price ratio of ETH to its staked derivative. The rebalancing strategy is designed to adjust automatically as market dynamics change, ensuring that the liquidity remains concentrated where trading volume is highest, thereby maximizing fees.
* **Example 2: LRT/BTC Liquidity Pool** In an LRT/BTC pool, Amplified can take advantage of the high correlation between BTC and ETH along with their associated LRT and LST assets. Since BTC and ETH tend to follow similar price trends, the LRT/BTC pool can be managed with tighter liquidity ranges, reducing the risks associated with impermanent loss. Amplified's ALM module dynamically adjusts these ranges in response to market conditions, ensuring that liquidity remains concentrated in the most profitable bands. Additionally, Amplified's cross-pool rebalancing feature allows liquidity to shift between the LRT/BTC pool and other highly correlated pools, such as ETH/LST, based on yield potential, maximizing both fee generation and capital efficiency while minimizing risks.

#### 3. Cross Fee Tier and Inventory Management

* **Cross Fee Tier Vaults**: Amplified Vaults support multiple fee tiers, allowing for liquidity allocation across different fee structures (e.g., 0.01%, 0.3%) to optimize trading volume capture. This is particularly useful for LST and LRT pools, where liquidity demand may vary across different fee tiers.
* **Inventory Management**: The protocol uses a portion of the deposited liquidity at a given time, ensuring an optimal balance between on-chain exposure and risk mitigation. This dynamic inventory management helps mitigate liquidity risks during volatile market conditions.

### Mechanism Design and Execution

#### 1. Portfolio Optimization with Risk Management

Amplified Protocol applies portfolio optimization strategies that dynamically adjust the liquidity range according to market volatility and trading activity.

* **Volatility Analysis**: The protocol uses a GARCH (Generalized Autoregressive Conditional Heteroskedasticity) model to predict future volatility and adjust liquidity positioning.
* **Transaction Cost Optimization**: Gas cost estimation and transaction batching ensure that rebalancing only occurs when it is economically viable. For example, if $G$ represents gas cost, a rebalance occurs if $f(v) > G$, where $f(v)$ is the projected profit from rebalancing.

#### 2. Risk Mitigation Tools

* **Impermanent Loss Management**: The protocol uses risk-adjusted metrics to decide when to expand liquidity ranges during periods of high volatility, minimizing exposure to adverse price movements.
* **Smart Liquidity Migration**: Amplified automatically migrates liquidity positions based on significant price shifts, minimizing LP losses. This process involves calculating expected returns  for different ranges and selecting the range with the highest net expected return.

### Risk Assessment and Mitigation for Amplified ALM Protocol

#### 1. Risk Assessment of Amplified ALM

Amplified Protocol's ALM module inherently involves risks associated with volatility, impermanent loss, rebalancing costs, and liquidity fragmentation across multiple pools. The primary risks include:

* **Impermanent Loss (IL)**: As with any AMM strategy, LPs are exposed to impermanent loss when the price of assets in a liquidity pool diverges. For highly correlated assets like LST and LRT, IL is lower, but non-negligible in highly volatile scenarios.
* **Volatility Risk**: Market volatility can result in rapid price movements, which may cause liquidity ranges to move out of optimal zones, leading to inactive liquidity and lost fee opportunities.
* **Rebalancing Costs**: Frequent rebalancing incurs gas fees, which may erode profitability, especially if the rebalancing is not optimized efficiently.
* **Liquidity Fragmentation**: Managing liquidity across multiple fee tiers and different pools can lead to fragmentation, where capital is not deployed in the most efficient manner possible.

#### 2. Professional Risk Mitigation Strategies

Amplified Protocol employs advanced risk mitigation strategies to address these concerns and enhance the efficiency of liquidity management:

* **Dynamic Liquidity Band Adjustments**: The protocol utilizes real-time market data and sophisticated predictive models, such as GARCH, to dynamically adjust liquidity bands in response to market volatility. This minimizes impermanent loss by ensuring liquidity is always within an optimal trading range.
* **Gas Efficiency through Transaction Batching**: To mitigate rebalancing costs, Amplified uses transaction batching and executes rebalancing only when economically justified. By assessing the expected profitability of each rebalance against gas costs, the protocol ensures that actions taken are cost-effective.
* **Correlated Asset Focus**: By focusing on highly correlated assets like LST and LRT, Amplified minimizes the risk of significant impermanent loss. The built-in ALM module exploits the natural price stability between these assets, ensuring tighter liquidity ranges and higher capital efficiency.
* **Cross-Pool Rebalancing**: The protocol's ability to rebalance liquidity across multiple pools with different asset pairs ensures that liquidity is always positioned in the pools with the highest yield potential, reducing the risk of fragmented and inefficient liquidity allocation.
* **Multi-Tier Positioning**: Managing liquidity across multiple fee tiers allows Amplified to capture trading volume from various market segments. This diversification mitigates risk by ensuring that LPs earn fees from different fee structures, reducing reliance on any single pool or tier.

By incorporating these risk mitigation measures, Amplified Protocol ensures that LPs can maximize their earnings while minimizing exposure to typical risks inherent in concentrated liquidity management. This professional approach to risk management positions Amplified as a robust solution for decentralized liquidity provision.
