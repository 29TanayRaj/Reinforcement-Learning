## Overview of Learning Paradigms

### **Machine Learning (ML)**

- **Supervised Learning**:
  - **Goal**: Learn a mapping from input to output.
  - **Problems**: 
    - Classification (categorical output).
    - Regression (continuous output).
  - Relies on labeled data for training.

- **Unsupervised Learning**:
  - **Goal**: Identify patterns or groupings within input data.
  - **Examples**:
    - Clustering: Group similar data points.
    - Frequent Pattern Mining: Identify repeating trends.

---

### **How Learning to Cycle Relates**

- **Supervised Learning?**: No.
  - Parents or guardians might provide vague instructions like "don't fall," but not precise control signals (e.g., "apply 3 pounds of pressure on the left pedal").
  - Supervision at this detailed level makes learning impractical.

- **Unsupervised Learning?**: No.
  - Watching videos of people cycling and trying to replicate their actions does not work.

- **Reinforcement Learning**:
  - Involves trial and error.
  - Feedback is minimal:
    - Falling down = Negative feedback.
    - Successfully balancing = Positive reinforcement.

---

## What is Reinforcement Learning (RL)?

- **Definition**: A learning paradigm where an agent learns to interact with its environment through **trial and error**, receiving rewards or punishments as feedback.
- **Inspiration**: Behavioral psychology experiments like Pavlov’s dog.
  - Dogs learned to associate stimuli (bell) with rewards (food), forming conditioned reflexes.

---

### Key Characteristics of RL

1. **Minimal Feedback**:
   - Rewards (positive) or punishments (negative).
   - No detailed supervision (e.g., no direct mapping from input to action).

2. **Interaction with the Environment**:
   - Learn by actively trying different actions and observing outcomes.

3. **Delayed Rewards**:
   - The outcome (reward or punishment) might not be immediately connected to the action that caused it.
   - Example: Dropping a catch in cricket may lead to losing a match much later.

4. **Sequential Actions**:
   - Rewards are often the result of a sequence of actions, not a single one.
   - Example: Winning a chess game requires a sequence of strategic moves.

5. **Stochastic Environments**:
   - The world is noisy and unpredictable, making learning more challenging.

---

## Learning in RL

- **Goal**: Learn a **policy**:
  - A mapping from states (inputs) to actions (outputs).
  - Example: Learning how to cycle involves associating balance, speed, and direction with appropriate actions.

- **Trial and Error Learning**:
  - Explore different actions to determine what leads to rewards.
  - Essential for learning in complex and uncertain environments.

---

## Applications of RL

- **Helicopter Control**:
  - Stanford and Berkeley used RL to train helicopters to perform complex maneuvers, such as flying upside down.
  - RL enabled finer control than human pilots.

- **Backgammon (TD-Gammon)**:
  - IBM's Jerry Tesauro trained an RL agent to play backgammon using **self-play**.
  - Resulted in a program capable of defeating world champion human players.


# Notes: Reinforcement Learning Applications and Key Insights

---

## **1. Helicopter Control**:
  - Stanford and Berkeley used RL to train helicopters to perform complex maneuvers, such as flying upside down.
  - RL enabled finer control than human pilots.

## **2. TD-Gammon: Reinforcement Learning in Backgammon**
- Jerry Tesauro developed **TD-Gammon**, a reinforcement learning (RL) agent.
- Achievements:
  - Became the **world's best backgammon player**.
  - Transitioned the claim from "best computer player" to "best player overall."
- Impact: Demonstrated RL's potential to master complex games.

---

## **3. Reinforcement Learning in Go**
- **Game Complexity**:
  - Go has a **huge branching factor**, making it hard for traditional algorithms.
  - Human players make intuitive leaps to navigate the vast search trees.
- **David Silver's Contribution**:
  - Worked with Jerry Tesauro at IBM.
  - Developed **TD Search**, an RL-based agent for Go.
  - Performance:
    - Achieves a decent level of play, though not yet at master human level.
- Insight: RL handles problems unsolvable by traditional machine learning or algorithms.

---

## **4. Robo Soccer: Complex Strategies with RL**
- Application: UT Austin's **Robo Soccer Team (Austin Villa)**.
- Achievements:
  - Champions for several years in the **Humanoid League**.
  - RL used for hard control problems like:
    - Balancing the robot on one leg.
    - Swinging the other leg to take accurate spot-kicks.
- Approach:
  - Combines RL with other AI techniques (planning, supervised learning).
  - Produces a highly competent, hard-to-beat robotic team.

---

## **5. Online Learning and RL in News and Ads**
- **Online Learning**:
  - Feedback arrives piecemeal, not available a priori.
  - Example: **News Story Selection**:
    - Problem: Select stories to display prominently on a webpage.
    - Feedback: A click on the story indicates a reward; no click means no reward.
    - RL Approach:
      - Trials to optimize story selection with minimal attempts.
      - Natural modeling for problems involving sequential feedback.

- **Ad Selection**:
  - Problem: Select ads to display on websites for maximum payoff.
  - Challenges:
    - Selecting the best subset from a set of candidate ads.
    - Balancing economic payoff with user engagement.
  - Use of RL:
    - Improves ad placement and selection strategies.
    - Forms a core part of **computational advertising**, a complex field combining economic and technical considerations.

---

## **6. Helicopter Control: RL in Robotics**
- Demonstration:
  - RL agents controlling helicopters, performing complex maneuvers (e.g., flying inverted).
  - Video example: Reinforcement learning enables precise control of a large, non-human-sized helicopter.
- Insight: RL excels in solving challenging control problems.

---

## **Key Takeaways**
- RL has achieved breakthroughs in:
  - Complex games (Backgammon, Go).
  - Robotics (Robo Soccer, Helicopter Control).
  - Real-world applications (News selection, Ad placement).
- Strengths of RL:
  - Handles minimal feedback and sequential decision-making.
  - Offers a natural framework for problems involving delayed rewards and trial-and-error learning.

