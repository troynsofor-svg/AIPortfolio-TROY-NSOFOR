# Problem Statement
The problem that this project in this notebook solves is teaching an agent how to balance a pole using two methods:

Running a random agent: To examine its instant failure in a classic RL world.
Running a Q-Learning agent: To notice how it learns over time and enhances its performance.

# Approach
I solved the problem by using the two main techiques/algorithms to address the pole-balancing scenario:

Random Agent: This acts as the baseline, highlighting how the agent operates with no learning. It easily takes random actions (like pushing the cart left or right) in every step.

Q-Learning Agent: This is the main reinforcement learning algorithm that was executed. 
It applies:
Q-Table: A lookup table to keep the calculated value of taking a concrete action in a provided state.
State Discretization (Binning): To manage the persistent state space of CartPole, the state variables are separated into different bins.
Epsilon-Greedy Exploration: A method to balance exploration (attempting to do new actions) and exploitation (applying good actions that are recognized). In the beginning, the agent investigates more, then as it learns, it exploits more.
Q-Learning Update Rule: This rule upgrades the Q-table derived from the reward received and the calculated future rewards, enabling the agent to learn which actions caused better results over time.

# Results
Here's the breakdown of the results, metrics, and performance examined in the notebook:

1. Random Agent Performance
Average Score: 23.6 timesteps survived.
Best Score: 81 timesteps survived.
Worst Score: 11 timesteps survived.
Observation: The random agent compatibly failed rapidly, describing that random actions are inefficient for balancing the pole.

2. Original Q-Learning Agent Performance (Epsilon Decay: 0.995)
Training Progress (Average Score of Last 50 Episodes):
Initially (first 50 events): 18.5
Towards the end (last 50 events): 54.4
Overall Final Average Score (last 50 episodes): 54.4 timesteps survived.
Improvement over Random Agent: The Q-Learning agent demonstrated an enhancement of 30.8 points across the random agent's average score (54.4 - 23.6).
Learning Curve: The rolling average score (orange line) demonstrated a clear upward trend, meaning that the agent learned over a period of time. It compatibly beat the random agent's mean score at around episode 144.
Epsilon (Exploration Rate):Began at 1.0 (entirely at random) and decayed to 0.0816 by the last of the 500 episodes, representing a transition from exploration to exploitation.
Observation: The Q-Learning agent successfully learned how to balance the pole for crucially long durations compared to the random agent, describing the efficiency of the Q-learning algorithm.

3. Comparison of Q-Learning Agents (Different Epsilon Decay Rates)
Original Agent (ε decay = 0.995): Final-50 mean score: 54.4
Agent A (Fast Decay, ε decay = 0.990): Final-50 mean score: 44.4
Agent B (Slow Decay, ε decay = 0.999): Final-50 mean score: 31.3
Observation: The regular agent with a average decay rate (0.995) performed better than the other three tested agents, accomplishing the highest mean score in the final 50 episodes. Agent A (faster decay) performed badly than the regular agent, and Agent B (slower decay) performed more badly, recommending that an optimal balance between exploration and exploitation is important for proficient learning in the world.

# Key Findings
I learned what exploitation, exploration and what the reward signal is.

# Technologies Used
(Libraries): Gymnasium, Numpy, Matplotlib, and Warnings.

(Frameworks): Gymnasium

(Tool): pip

# How to Run
1. Open Google Colab
2. Go to and click on File (Open Notebook)
3. Click and look for L09_Troy_ITAI_2376.ipynb (or L09_Troy_ITAI_2376)
