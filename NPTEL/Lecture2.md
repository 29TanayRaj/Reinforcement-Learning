
## Introduction to Reinforcement Learning

- **Reinforcement Learning (RL)** focuses on an agent learning through interactions with an environment.
- The agent **senses the state** of the environment and **takes actions** in response to that state.
- The environment reacts to the agent's actions by changing its state, and this interaction continues in cycles.

### Key Concepts:
- **Learning Agent**: The agent learns by interacting with the environment, which can be anything from a video game to real-world systems.
- **Environment**: Can consist of various elements, like a helicopter, a bicycle, or a backgammon game board.
- **State**: The current condition or configuration of the environment.
- **Action**: The move the agent takes in response to the state.
- **Reward**: Feedback from the environment, typically indicating how good or bad a specific action was.

## Action Selection and Future Planning

- The agent’s goal is not just to take actions that benefit its current state, but to plan for the future.
- **Optimal Behavior**: The agent should select actions that will lead to a beneficial state in the future, not just present rewards (e.g., capturing an opponent's queen in chess might not be optimal if it leads to a worse position).
  
### Key Challenges:
- **Delayed Evaluation**: Actions may have rewards that are delayed and not immediately obvious.
- **Sequence of Decisions**: The agent needs to consider the long-term consequences of its actions, rather than focusing on immediate rewards.

## Scalar Rewards and Mathematical Framework

- **Scalar Rewards**: RL typically uses scalar rewards (single numerical values) to represent the success or failure of actions.
  - For example, losing 100 points for a fall, gaining 5 points for food, or 20 points for winning a game.
- The goal is to maximize the total reward over time.
  
### Reward Structure:
- The reward is often simplified to a scalar for ease of optimization.
- In some cases, different components of rewards (vector values) may need to be balanced, which introduces complexity in decision-making.

## Supervised vs. Reinforcement Learning

- **Supervised Learning**: The agent receives input-output pairs with targets (e.g., a correct answer to a question). The learning process involves minimizing the error between the predicted and target outputs.
  
- **Reinforcement Learning**:
  - No target output is provided.
  - The agent learns through **trial and error**.
  - **Evaluation**: The agent receives evaluations (rewards or punishments) from the environment but does not know the correctness of its actions.
  
### Key Differences:
- RL doesn't have a clear target like supervised learning. Instead, the agent has to explore different actions to gather more information about which ones lead to better outcomes.

## Trial and Error in RL

- The core of RL is **trial and error**.
  - The agent doesn't know whether an action was good or bad until it receives feedback from the environment.
  - For example, in cycling, an agent (rider) might adjust force on the pedal to maintain balance, learning through feedback.
  
### Exploration vs. Exploitation:
- **Exploration**: Trying new actions to understand their outcomes.
- **Exploitation**: Using knowledge from previous trials to maximize future rewards.

## Temporal Difference Learning

- **Temporal Difference (TD) Learning**: A key concept in RL.
  - It is similar to **Pavlov’s Dog** experiment, where the dog learns to predict food after hearing a bell.
  - In RL, the agent learns to predict the **future rewards** it will receive for a given action.

### Intuition Behind TD Learning:
- Predictions made earlier in the process are less certain than those made later when more information is available.
  - Example: In a game, the agent's prediction of winning is more confident later in the game than at the start.
  
- **T+1 Prediction**: The prediction made at time `t+1` is more reliable than the one made at time `t`.

### Improving Predictions:
- To improve the prediction at time `t`, the agent can look ahead to time `t+1` and adjust its strategy accordingly.

- In Temporal Difference (TD) learning, the agent makes predictions about future rewards and adjusts them as new information becomes available.
- Example: In a game, an agent might initially predict a 60% chance of winning (0.6 probability). After making a move, if the situation worsens, the agent updates its prediction to a lower value (0.55).
- This process allows the agent to continuously refine its predictions based on experience, adjusting its strategies for better outcomes in future iterations.

### Impact on Behavioral Psychology and Neuroscience

- TD learning has had a significant impact on our understanding of **behavioral psychology** and **neuroscience**.
- There are models that explain some neurotransmitter behaviors in the brain, suggesting that animals might use forms of temporal difference learning.
- The concept has been applied to explain reward-based learning in animals and humans.

## Tic-Tac-Toe as a Reinforcement Learning Problem

- **Game Tree**: In a game like Tic-Tac-Toe, we can represent the different possible game states using a "game tree." Each state corresponds to a board position, and each action is a move made by either the agent (X) or the opponent (O).
  - Initially, there are 9 possible moves for the agent.
  - As the game progresses, fewer possible moves remain.

- **States and Actions**: The states are the board positions, and the actions are the moves the agent makes at each point in the game.
  - For instance, when it's the agent's turn (X), it decides which of the 9 possible positions to place an X.

- **Reward System**: The reward system is binary for simplicity:
  - **1** for a win (reward).
  - **0** for a loss (no reward).

### Imperfect Opponent

- The opponent should not be perfect because if the opponent always draws, the agent would never learn how to win or improve. Learning happens when the agent can exploit the mistakes made by an imperfect opponent.
- **Imperfect Opponent**: If the opponent makes mistakes, the agent can learn to exploit those mistakes and improve its strategy.

## State Value Function and Probabilities

- **Expected Reward**: For each board position, the agent tries to estimate the expected reward (probability of winning).
  - If the agent wins from a given position, it gets a reward of 1. If it loses or doesn't win, the reward is 0.
  - The agent will calculate the probability of winning from each position based on past games.

### Updating Probabilities

- After each game, the agent updates the **probability of winning** based on the outcome:
  - If the game is won, the winning probability for the states along the trajectory of the game is increased.
  - If the game is lost, the probability is decreased.
  
### Exploration and Learning

- **Learning from History**: After each game, the agent can compute the **average probability of winning** for each state across all the games played.
  - The probability updates help the agent become better at making decisions and predicting outcomes in future games.
- **Game Tree Exploration**: The agent explores the game tree, keeping track of the moves and outcomes to inform future decisions.

## Solving Tic-Tac-Toe with RL

- The solution involves estimating the **expected reward** (probability of winning) for each possible board position.
- For each position, the agent evaluates the possible next moves and chooses the one with the highest probability of winning.
  - **Look Ahead**: The agent looks ahead to see which move leads to the highest probability of winning and chooses that move.

### Storing and Updating Information

- **Tracking the Trajectory**: The agent tracks the trajectory of the game (the sequence of moves) from start to finish.
  - After completing a game, it updates the winning probabilities for each state along the trajectory.
  
- **Alternative Method**: The agent could also maintain a history of all the games played, averaging the probabilities of winning for each board position across all games.

### Estimating the Probability of Winning

- The agent uses the **stored history of moves** to estimate the probability of winning from each state. For each state:
  - If the agent wins from that position, the probability of winning is increased.
  - If the agent loses, the probability is decreased.
  
- **Updating State Values**: The agent constantly updates the value of each state based on the results from the games played.

### Final Decision-Making Process

- Once the agent has learned the value of each state, it evaluates all possible next states and selects the one that maximizes the probability of winning.
- This process forms the crux of **reinforcement learning** algorithms: learning the expected reward (or value) of each state to inform decision-making.

## Learning Expectations

- The agent learns by continuously adjusting its expectations about the outcome of different states.
- Over time, as the agent plays more games and updates its expectations, its ability to make optimal decisions improves.

# Temporal Difference Learning and Exploration-Exploitation in RL

## 1. Waiting Until the End vs. Learning Along the Way
- In simple games like **Tic-Tac-Toe**, you can wait until the end to update your strategy because the game has a limited number of moves and can be fully analyzed at the end.
- However, for more complex games like **chess**, you cannot always wait until the end to adjust your strategy. In such cases, you may need to learn during the game, making updates at each step to improve your chances of winning.

## 2. Temporal Difference (TD) Learning
- **TD learning** is introduced as a way to update the strategy incrementally while the game is still ongoing, without waiting for the outcome to be determined.
- The speaker uses an example where the agent (the player) thinks the probability of winning from a certain point is 0.6, but after exploring further, the best possible outcome is found to be 0.3. This discrepancy forces the agent to adjust its belief (lowering the probability of winning from 0.6 to something closer to 0.3).
- **Methods**
  - TD ($\lambda$)
  - Q-Learning
  - SARSA
  - Actor-Critic

## 3. Multiple Ways to Reach a Game State
- In games like **Tic-Tac-Toe**, there are multiple ways to reach the same board state (based on the sequence of moves), and each path can have different outcomes (some leading to wins, others to losses).
- The TD learning method adjusts probabilities based on the outcomes observed from different paths, helping to refine the strategy over time.

## 4. Exploration vs. Exploitation
- The idea of **exploration** (trying different moves to discover better strategies) vs. **exploitation** (using the best-known strategy to maximize immediate reward) is crucial in RL.
- If the agent always exploits, it might miss better opportunities. If it always explores, it might not perform well based on current knowledge. Balancing these two is a key challenge.
- The question arises about how long to keep exploring before switching to exploiting, which leads to the **Explore-Exploit Dilemma**.

## 5. Bandit Problems
- The speaker introduces **Bandit Problems** as a simplified form of RL where an agent has to choose between multiple actions to maximize rewards, but does not know the exact reward distribution for each action.
- The challenge in bandit problems is deciding how much to explore versus exploit, much like the dilemmas faced in RL.

## 6. Dynamic Programming
- **Dynamic Programming (DP)** is introduced as a method to solve problems by breaking them down into smaller subproblems, using previous solutions to build up to a complete solution.
- In the context of RL, DP can be used to estimate the best actions by considering all possible future outcomes (like calculating the probability of winning from every game state).
- However, RL methods like **TD learning** work differently by updating the agent's strategy based on observed samples (one-step outcomes) instead of using the complete game tree.

## Summary
The speaker is explaining the **Temporal Difference Learning** method and how it can be applied to games for incremental learning. The balance between **exploration** and **exploitation** is discussed, as well as the challenges involved in this balance. The speaker also introduces **Dynamic Programming** and explains how RL methods, including TD learning, differ from it by using sampled data to update strategies in real-time.


