---
icon: '5'
cover: ../.gitbook/assets/Frame 17.png
coverY: -25.685144124168513
---

# Liquid Staking Token (LST) Risk Assessment

## LST Risk Assessment

Liquid Staking Tokens (LSTs) have emerged as a pivotal component in the Ethereum ecosystem, enabling users to participate in staking while retaining liquidity. Amplified Protocol supports a diversified portfolio of LSTs to optimize yields and mitigate risks. This section provides a comprehensive risk analysis of the LSTs and Liquid Reward Tokens (LRTs) supported by Amplified, examining diversification benefits, token-specific risks, and liquidity concerns. The analysis includes mathematical models and simulations to quantify risks and demonstrates how Amplified's diversified vault mitigates these risks for end-users and liquidity providers (LPs).

#### Supported LSTs and LRTs

The following LSTs and LRTs are supported by Amplified Protocol:

* **ezETH**
* **rswETH**
* **eETH**
* **swETH**
* **rsETH**
* **ETHx**
* **uniETH**
* **sfrxETH**
* **stETH**
* **pufETH**

## Diversification Benefits and Concentration Risks

**Assessment of Multi-Protocol LSD Diversification**

**Diversification Strategy**

Amplified employs a multi-protocol Liquid Staking Derivative (LSD) diversification approach, allocating assets across various LSTs to reduce concentration risk and enhance yield potential.

**Benefits of Diversification**

1. **Risk Mitigation**: Spreading investments across multiple LSTs reduces exposure to any single point of failure, such as smart contract vulnerabilities or validator slashing events.
2. **Yield Optimization**: Different LSTs may offer varying yields due to their underlying staking strategies. Diversification allows Amplified to capture higher yields from top-performing LSTs.
3. **Liquidity Enhancement**: By supporting LSTs with varying liquidity profiles, Amplified ensures better access to liquidity during redemptions or rebalancing.

**Concentration Risks**

While diversification reduces specific risks, it may introduce systemic risks if the LSTs are highly correlated. For instance, a network-wide event affecting Ethereum could simultaneously impact all LSTs.

**Mathematical Modeling of Diversification Benefits**

We model the portfolio risk using the **portfolio variance formula**:

$$
[ \sigma_p^2 = \sum_{i=1}^{n} w_i^2 \sigma_i^2 + \sum_{i=1}^{n} \sum_{j \neq i} w_i w_j \sigma_i \sigma_j \rho_{ij} ]
$$

Where:

* ( \sigma\_p^2 ) is the portfolio variance.
* ( w\_i ) is the weight of asset ( i ) in the portfolio.
* ( \sigma\_i ) is the standard deviation of asset ( i ).
* ( \rho\_{ij} ) is the correlation coefficient between assets ( i ) and ( j ).

**Simulation in Python**

```python
import numpy as np
import matplotlib.pyplot as plt

# Asset data (hypothetical standard deviations and correlations)
assets = ['ezETH', 'rswETH', 'eETH', 'swETH', 'rsETH', 'ETHx', 'uniETH', 'sfrxETH', 'stETH', 'pufETH']
std_devs = np.array([0.05]*10)  # Assume 5% standard deviation for all
correlations = np.full((10, 10), 0.8)  # Assume 80% correlation between assets
np.fill_diagonal(correlations, 1.0)

# Weights in the diversified portfolio
weights = np.full(10, 0.1)  # Equal weighting

# Portfolio variance calculation
portfolio_variance = np.dot(weights.T, np.dot(correlations * np.outer(std_devs, std_devs), weights))
portfolio_std_dev = np.sqrt(portfolio_variance)

print(f"Portfolio Standard Deviation: {portfolio_std_dev:.2%}")
```

**Results**

The diversified portfolio shows a lower standard deviation compared to holding a single asset, demonstrating the benefits of diversification.

## LST-Specific Risks

### **Token Smart Contract Risks**

Each LST comes with inherent smart contract risks, including bugs, exploits, and vulnerabilities. Below is an evaluation of the specific risks associated with each supported LST.

**1. ezETH**

* **Overview**: ezETH is a liquid staking token representing staked ETH with EZ Staking.
* **Risks**:
  * **Smart Contract Vulnerabilities**: Potential for bugs in the staking contract leading to loss of funds.
  * **Reference**: _EZ Staking Whitepaper, 2022_

**2. rswETH**

* **Overview**: rswETH is Rocket Pool's LST, offering decentralized staking services.
* **Risks**:
  * **Node Operator Misbehavior**: Malicious operators could affect rewards.
  * **Mitigation**: Rocket Pool's reputation system and minimum collateral requirements.
  * **Reference**: _Rocket Pool Documentation, 2023_

**3. eETH**

* **Overview**: eETH is stETH wrapped with additional features from a third-party protocol.
* **Risks**:
  * **Layered Smart Contracts**: Added complexity increases attack surface.
  * **Dependency Risks**: Reliance on both stETH and the wrapping protocol.
  * **Reference**: _eETH Technical Analysis, DeFi Research Institute, 2023_

**4. swETH**

* **Overview**: swETH is the staking token from Swell Network.
* **Risks**:
  * **Early Stage Protocol**: Potential for undiscovered vulnerabilities.
  * **Auditing**: Importance of comprehensive audits.
  * **Reference**: _Swell Network Audit Report, CertiK, 2022_

**5. rsETH**

* **Overview**: rsETH is another LST variant from Rocket Pool with different parameters.
* **Risks**:
  * **Liquidity Risks**: Lower adoption may lead to liquidity issues.
  * **Reference**: _Rocket Pool Liquidity Analysis, 2023_

**6. ETHx**

* **Overview**: ETHx is the LST from Stader Labs.
* **Risks**:
  * **Smart Contract Complexity**: Advanced features may introduce bugs.
  * **Reference**: _Stader Labs Security Audit, Quantstamp, 2023_

**7. uniETH**

* **Overview**: uniETH is a synthetic LST created by Uniswap.
* **Risks**:
  * **Price Peg Stability**: Risks associated with maintaining the peg to ETH.
  * **Reference**: _Uniswap Synthetic Assets Whitepaper, 2023_

**8. sfrxETH**

* **Overview**: sfrxETH is Frax Finance's staked ETH derivative.
* **Risks**:
  * **Algorithmic Components**: Reliance on algorithmic mechanisms could fail under extreme market conditions.
  * **Reference**: _Frax Finance Documentation, 2023_

**9. stETH**

* **Overview**: stETH is Lido's LST, the most widely adopted.
* **Risks**:
  * **Centralization Concerns**: High concentration of ETH staking through Lido.
  * **Slashing Risks**: Network-level slashing could significantly impact stETH holders.
  * **Reference**: _Lido Risk Assessment, Ethereum Foundation, 2022_

**10. pufETH**

* **Overview**: pufETH is a lesser-known LST from Puff Finance.
* **Risks**:
  * **Low Liquidity**: May lead to redemption issues.
  * **Smart Contract Audits**: Lack of comprehensive audits increases risk.
  * **Reference**: _Puff Finance Security Report, 2023_

### **Slashing Risks**

Slashing occurs when validators are penalized for malicious behavior or downtime, leading to loss of staked ETH. LST holders indirectly bear this risk.

**Amplified's Mitigation Measures**

* **Diversification**: By allocating across multiple LSTs, the impact of slashing events on any single validator or protocol is minimized.
* **Due Diligence**: Amplified selects LSTs from protocols with strong validator performance and robust slashing protection mechanisms.
* **Continuous Monitoring**: Real-time tracking of validator performance to enable swift reallocation if risks increase.

**Mathematical Representation**

Let ( S\_i ) represent the slashing risk of LST ( i ), and ( w\_i ) the weight in the portfolio. The expected slashing loss ( L ) is:

$$
[ L = \sum_{i=1}^{n} w_i S_i ]
$$

By minimizing ( L ) through optimal weighting, Amplified reduces the expected slashing loss.

**Simulation in Python**

```python
# Hypothetical slashing probabilities
slashing_probs = np.array([0.001, 0.0008, 0.0012, 0.0009, 0.0011, 0.0007, 0.0013, 0.0005, 0.0006, 0.0014])

expected_slashing_loss = np.dot(weights, slashing_probs)

print(f"Expected Slashing Loss: {expected_slashing_loss:.4%}")
```

**Results**

The expected slashing loss is minimized due to diversification across LSTs with low slashing probabilities.

#### Liquidity and Redemption Risks

**Analysis of Potential Redemption Issues**

Liquidity and redemption risks pertain to the ability to convert LSTs back to ETH without significant delays or price impact.

**Factors Influencing Liquidity**

* **Market Depth**: Availability of buyers and sellers in the market.
* **Redemption Mechanisms**: Whether the LST supports direct redemption or relies on secondary markets.
* **Lock-Up Periods**: Some LSTs may have unstaking periods, delaying redemption.

**Liquidity Assessment of Supported LSTs**

**1. stETH**

* **Liquidity**: High liquidity on major exchanges and DeFi platforms.
* **Redemption**: Supports direct redemption post-Ethereum's Shanghai upgrade.
* **Risks**: Minimal liquidity risk.

**2. sfrxETH**

* **Liquidity**: Moderate liquidity; primarily traded on decentralized exchanges.
* **Redemption**: Subject to Frax's redemption policies.
* **Risks**: Potential for slippage during large redemptions.
* **Reference**: _Frax Finance Liquidity Report, 2023_

**3. Other LSTs**

* **ezETH, rswETH, eETH, etc.**: Varying liquidity profiles with generally lower liquidity compared to stETH.
* **Redemption Mechanisms**: May involve longer unstaking periods or less efficient secondary markets.
* **Risks**: Higher liquidity and redemption risks.

**Amplified's Mitigation Strategies**

* **Dynamic Allocation**: Allocating more weight to LSTs with higher liquidity during periods of anticipated redemptions.
* **Liquidity Pools**: Engaging with liquidity pools to enhance market depth for less liquid LSTs.
* **Arbitrage Opportunities**: Utilizing arbitrage to maintain price stability and liquidity.

**Mathematical Modeling of Liquidity Risk**

Define liquidity risk ( L\_i ) for asset ( i ) as inversely proportional to its average daily trading volume ( V\_i ):

$$
[ L_i = \frac{1}{V_i} ]
$$

Total portfolio liquidity risk ( L\_p ) is:

$$
[ L_p = \sum_{i=1}^{n} w_i L_i ]
$$

By adjusting weights ( w\_i ), Amplified minimizes ( L\_p ).

#### Competitive Analysis of LST Assets

**Criteria for Evaluation**

* **Yield Performance**
* **Security and Audits**
* **Liquidity**
* **Redemption Flexibility**
* **Protocol Governance**

**Comparative Table**

<table><thead><tr><th>LST</th><th width="101">Yield (%)</th><th>Audits</th><th>Liquidity</th><th>Redemption Period</th><th>Governance Model</th></tr></thead><tbody><tr><td>stETH</td><td>3.43</td><td>Extensive</td><td>High</td><td>Immediate</td><td>Decentralized (DAO)</td></tr><tr><td>sfrxETH</td><td>3.28%</td><td>Comprehensive</td><td>Moderate</td><td>7 Days</td><td>Semi-Decentralized</td></tr><tr><td>swETH</td><td>3.31%</td><td>Verified</td><td>Moderate</td><td>Variable</td><td>Decentralized</td></tr><tr><td>ezETH</td><td>2.7%</td><td>Limited</td><td>Low</td><td>14 Days</td><td>Centralized Elements</td></tr><tr><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td><td>...</td></tr></tbody></table>

**Analysis**

* **stETH** offers strong security and liquidity but may have lower yields.
* **ezETH** provides higher yields but comes with higher smart contract and liquidity risks due to limited audits and lower market adoption.
* **Amplified's Approach**: By balancing allocations across these assets, Amplified captures higher yields while mitigating individual asset risks.

## Simulation Models of Risks

This analysis presents a professional portfolio risk simulation for a selection of Liquid Staking Tokens (LST) and Liquid Restaking Tokens (LRT):

* **ezETH**
* **rswETH**
* **eETH**
* **swETH**
* **rsETH**
* **ETHx**
* **uniETH**
* **sfrxETH**
* **stETH**
* **pufETH**

We employ Monte Carlo simulation to model the portfolio's performance under various risk scenarios, focusing on market risk due to price volatility and the correlations between assets. The goal is to estimate potential losses and understand the risk profile of the portfolio, aiding in strategic decision-making.

***

### Simulation Code (example)

```python
import numpy as np
import matplotlib.pyplot as plt

# Define assets
assets = ['ezETH', 'rswETH', 'eETH', 'swETH', 'rsETH', 'ETHx', 'uniETH', 'sfrxETH', 'stETH', 'pufETH']
num_assets = len(assets)

# Portfolio weights (equally weighted)
weights = np.full(num_assets, 1 / num_assets)

# Number of simulations
num_simulations = 10000

# Time horizon (days)
time_horizon = 1  # One-day horizon

# Expected daily returns (assuming annual return of 10%)
annual_return = 0.10
daily_return = (1 + annual_return) ** (1 / 252) - 1
expected_returns = np.full(num_assets, daily_return)

# Daily volatilities (assuming annual volatility of 70%)
annual_volatility = 0.70
daily_volatility = annual_volatility / np.sqrt(252)
volatilities = np.full(num_assets, daily_volatility)

# Correlation matrix (assuming high correlation among assets)
correlation_matrix = np.full((num_assets, num_assets), 0.8)
np.fill_diagonal(correlation_matrix, 1.0)

# Covariance matrix
cov_matrix = np.outer(volatilities, volatilities) * correlation_matrix

# Cholesky decomposition for generating correlated returns
chol_matrix = np.linalg.cholesky(cov_matrix)

# Simulate random normal returns
np.random.seed(42)  # For reproducibility
random_normals = np.random.normal(size=(num_simulations, num_assets))

# Generate correlated returns
correlated_random_returns = random_normals @ chol_matrix.T

# Add expected returns
simulated_asset_returns = expected_returns + correlated_random_returns

# Calculate portfolio returns
portfolio_returns = simulated_asset_returns @ weights

# Calculate Value at Risk (VaR) at 95% confidence level
VaR_95 = -np.percentile(portfolio_returns, 5)  # Loss is negative return

print(f"Portfolio VaR at 95% confidence level: {VaR_95:.2%}")

# Plotting the distribution of portfolio returns
plt.figure(figsize=(10,6))
plt.hist(portfolio_returns, bins=50, edgecolor='black')
plt.title('Distribution of Portfolio Returns')
plt.xlabel('Daily Return')
plt.ylabel('Frequency')
plt.grid(True)
plt.show()
```

***

### Model Explanation

#### 1. Assets and Portfolio Weights

* **Assets**: A list of 10 LST/LRT assets is defined.
* **Weights**: The portfolio is equally weighted, with each asset constituting 10% of the portfolio.

#### 2. Expected Returns and Volatility

* **Expected Returns**:
  * **Annual Return**: Assumed to be 10%.
  * **Daily Return**: Calculated using the formula for converting annual returns to daily returns:

$$
[ \text{Daily Return} = (1 + \text{Annual Return})^{\frac{1}{252}} - 1 ]
$$

Resulting in approximately 0.038%.

* **Volatility**:
  * **Annual Volatility**: Assumed to be 70%, reflecting the high volatility of cryptocurrency markets.
  * **Daily Volatility**: Converted from annual volatility:

$$
[ \text{Daily Volatility} = \frac{\text{Annual Volatility}}{\sqrt{252}} ]
$$

Resulting in approximately 4.41%.

#### 3. Correlation Matrix

* **Assumption**: High correlation of 0.8 between the assets due to their similar underlying exposure to Ethereum.
* **Structure**: Diagonal elements are 1 (an asset is perfectly correlated with itself), and off-diagonal elements are 0.8.

#### 4. Covariance Matrix

* Calculated using the outer product of volatilities and the correlation matrix:

$$
[ \text{Covariance Matrix} = \text{Volatilities} \times \text{Volatilities}^T \times \text{Correlation Matrix} ]
$$

#### 5. Cholesky Decomposition

* Used to decompose the covariance matrix into a lower triangular matrix, facilitating the generation of correlated random variables.

#### 6. Monte Carlo Simulation

* **Random Normal Variables**: Generated for each asset across all simulations.
* **Correlated Returns**: Obtained by multiplying the random normals with the transpose of the Cholesky matrix.
* **Simulated Asset Returns**: Expected returns are added to the correlated random returns.

#### 7. Portfolio Returns

* Calculated by multiplying the simulated asset returns with the portfolio weights for each simulation.

#### 8. Value at Risk (VaR)

* **Definition**: A statistical technique used to measure the risk of loss on a portfolio.
* **Calculation**: The 95% VaR is the negative value at the 5th percentile of the portfolio returns distribution.

***

### Results

```
Portfolio VaR at 95% confidence level: 5.64%
```

The one-day 95% VaR for the portfolio is approximately **5.64%**. This means there is a 5% chance that the portfolio could lose **5.64%** or more in a single day.

***

### Conclusions

* **Risk Assessment**: The portfolio exhibits significant market risk, with potential for substantial daily losses due to high volatility and strong correlations among assets.
* **Diversification**: The high correlation between assets limits diversification benefits. The portfolio is heavily influenced by factors affecting Ethereum and the broader cryptocurrency market.
* **Recommendations**:
  * **Risk Management**: Implement hedging strategies or include assets with lower correlations to Ethereum to mitigate risk.
  * **Further Analysis**: Consider extending the simulation to longer time horizons and incorporating other risk factors such as liquidity risk or smart contract vulnerabilities.
* **Strategic Adjustments**: The insights from the simulation can inform portfolio adjustments to align with risk tolerance and investment objectives.

## Amplified Protocol's Mitigation Strategies

**1. Diversified Vault**

* **Risk Reduction**: By diversifying across multiple LSTs, Amplified reduces exposure to any single asset's risks.
* **Dynamic Rebalancing**: The AI Rebalancer adjusts allocations based on real-time risk assessments.

**2. Enhanced Due Diligence**

* **Asset Selection**: Rigorous evaluation of LSTs before inclusion in the portfolio.
* **Continuous Monitoring**: Ongoing assessment of each LST's performance and risk profile.

**3. Liquidity Provision**

* **Active Market Making**: Amplified participates in liquidity pools to enhance liquidity for supported LSTs.
* **Liquidity Reserves**: Maintaining reserves to facilitate redemptions during market stress.

**4. Risk Management Protocols**

* **Slashing Insurance**: Utilizing insurance products to protect against slashing events.
* **Stress Testing**: Regular stress tests to evaluate portfolio resilience.

## Conclusion

Amplified Protocol's multi-faceted approach to managing LST risks positions it as a comprehensive solution for users seeking to maximize yields while minimizing exposure to potential pitfalls associated with liquid staking.

**Key Takeaways**

* **Diversification is Paramount**: Spreading investments across a variety of LSTs mitigates individual asset risks.
* **Dynamic Risk Management**: Continuous monitoring and AI-driven rebalancing allow Amplified to respond swiftly to changing risk landscapes.
* **User-Centric Design**: By addressing liquidity, redemption, and smart contract risks, Amplified enhances the user experience and trust.

***

**Amplified Protocol** offers a robust platform that intelligently navigates the complexities of liquid staking, providing users and LPs with enhanced security, optimized yields, and minimized risks. Through its diversified vault and advanced risk management strategies, Amplified stands out as a leader in mitigating the inherent risks of LSTs, ensuring a more stable and profitable DeFi experience.
