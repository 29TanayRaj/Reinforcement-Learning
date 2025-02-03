
# Introduction to Bandit Problems
- **Bandit problems** are a class of problems in statistics.
- Named after **one-armed bandits**, which refer to **slot machines**.
- Slot machines have a lever (arm) that gamblers pull to try to win money.
- Casinos ensure these machines are **designed to take money** from players in the long run.

## Multi-Armed Bandit (MAB) Problem
- Instead of one lever (one-armed bandit), the **MAB problem** has **multiple arms** (n-armed bandit).
- Pulling an arm yields some **payoff**.
- The goal is to **maximize rewards** while balancing exploration and exploitation.

## Key Solution Concepts

### 1. **Asymptotic Correctness**
- Ensures that as **t → ∞**, the algorithm selects the best arm with the **highest payoff**.
- **Older literature** focuses on this approach, with some results on **rates of convergence**.
- Typically uses **simple algorithms** that guarantee eventual convergence.

### 2. **Regret Optimality**
- **Regret** measures the loss incurred due to not knowing the best arm initially.
- Defined as the difference between:
  - **Best possible reward** (if the optimal arm was known from the beginning).
  - **Actual reward** obtained through exploration.
- Goal: **Minimize regret** while learning efficiently.
- Trade-offs:
  - **Fast learning (steep slope)** → **Less regret**, but may risk missing key explorations.
  - **More exploration** → **Slower learning**, but ensures eventual convergence.
- **Lower bound on regret growth:**  
  - Regret must grow at least as **log(t)**.
  - No algorithm can achieve **sub-logarithmic regret**.

### 3. **PAC Optimality (Probably Approximately Correct)**
- **PAC (Probably Approximately Correct) learning** ensures:
  - The selected arm’s payoff is **approximately** close to the best arm.
  - This correctness holds with **high probability**.
- **Key parameters:**
  - **ε (epsilon):** Defines how close the selected arm is to the best arm.
  - **δ (delta):** Probability of achieving this closeness.
- **Epsilon-Delta PAC Guarantee:**
  - With probability **(1 - δ)**, the returned arm’s expected reward is **within ε** of the best arm.
- **Sample Complexity:**  
  - Measures the **minimum number of samples** needed to achieve an **ε-δ PAC guarantee**.
  - Optimization focuses on minimizing the number of arm selections.

## Summary of Solution Approaches
| Solution Concept       | Goal                                             | Key Consideration |
|-----------------------|-------------------------------------------------|-------------------|
| **Asymptotic Correctness** | Select the best arm as **t → ∞** | Long-term optimality |
| **Regret Optimality** | Minimize total regret over time | Trade-off between exploration and exploitation |
| **PAC Optimality** | Guarantee approximate correctness with high probability | Minimize sample complexity |

## Final Remarks
- Different solution concepts **lead to different algorithms**.
- Algorithms are often simple, but proving their correctness **requires deep analysis**.
- Understanding these concepts is key to designing effective **bandit algorithms**.
