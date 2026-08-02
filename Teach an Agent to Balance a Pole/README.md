# Problem Statement
The problem that this project in this notebook solves is teaching an agent how to balance a pole using two methods:

Running a random agent: To observe its immediate failure in a classic RL environment.
Running a Q-Learning agent: To see how it learns over time and improves its performance.

I used solved the problem using the two primary methods/algorithms to address the pole-balancing problem:

Random Agent: This serves as a baseline, showing how an agent performs without any learning. It simply takes random actions (pushing the cart left or right) at each step.
Q-Learning Agent: This is the core reinforcement learning algorithm implemented. It uses:
Q-Table: A lookup table to store the estimated value of taking a specific action in a given state.
State Discretization (Binning): To handle the continuous state space of CartPole, the state variables are divided into discrete bins.
Epsilon-Greedy Exploration: A strategy to balance exploration (trying new actions) and exploitation (using known good actions). Initially, the agent explores more, and as it learns, it exploits more.
Q-Learning Update Rule: This rule updates the Q-table based on the reward received and the estimated future rewards, allowing the agent to learn which actions lead to better outcomes over time.

Here's a summary of the results, metrics, and performance observed in this notebook:

1. Random Agent Performance
Average Score: 23.6 timesteps survived.
Best Score: 81 timesteps survived.
Worst Score: 11 timesteps survived.
Observation: The random agent consistently failed quickly, demonstrating that random actions are ineffective for balancing the pole.

2. Original Q-Learning Agent Performance (Epsilon Decay: 0.995)
Training Progress (Average Score of Last 50 Episodes):
Initially (first 50 episodes): 18.5
Towards the end (last 50 episodes): 54.4
Overall Final Average Score (last 50 episodes): 54.4 timesteps survived.
Improvement over Random Agent: The Q-Learning agent showed an improvement of 30.8 points over the random agent's average score (54.4 - 23.6).
Learning Curve: The rolling average score (orange line) showed a clear upward trend, indicating that the agent learned over time. It consistently beat the random agent's average score by approximately episode 144.
Epsilon (Exploration Rate): Started at 1.0 (fully random) and decayed to 0.0816 by the end of 500 episodes, showing a transition from exploration to exploitation.
Observation: The Q-Learning agent successfully learned to balance the pole for significantly longer durations compared to the random agent, demonstrating the effectiveness of the Q-learning algorithm.

3. Comparison of Q-Learning Agents (Different Epsilon Decay Rates)
Original Agent (ε decay = 0.995): Last-50 average score: 54.4
Agent A (Fast Decay, ε decay = 0.990): Last-50 average score: 44.4
Agent B (Slow Decay, ε decay = 0.999): Last-50 average score: 31.3
Observation: The original agent with a medium decay rate (0.995) performed the best among the three tested agents, achieving the highest average score in the last 50 episodes. Agent A (faster decay) performed worse than the original, and Agent B (slower decay) performed the worst, suggesting that an optimal balance between exploration and exploitation is crucial for efficient learning in this environment.

I learned what exploitation, exploration and what the reward signal is.

# Technologies Used
(Libraries): Gymnasium, Numpy, Matplotlib, and Warnings.

(Frameworks): Gymnasium

(Tool): pip

# How to Run
1. Open Google Colab
2. Go to and click on File (Open Notebook)
3. Click and look for L09_Troy_ITAI_2376.ipynb (or L09_Troy_ITAI_2376)
