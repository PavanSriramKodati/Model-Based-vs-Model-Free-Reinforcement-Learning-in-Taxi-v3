# Model-Based-vs-Model-Free-Reinforcement-Learning-in-Taxi-v3

[cite_start]**Author:** Pavan Sriram Kodati [cite: 65]  
**Institution:** University of the Pacific  
[cite_start]**Course:** COMP-293A-ON1-60142 (Reinforcement Learning) [cite: 62, 63]  
[cite_start]**Instructor:** Prof. Chadi El Kari [cite: 68]  

## 📌 Project Overview
[cite_start]This project conducts a comparative analysis of model-based and model-free reinforcement learning algorithms within the classic Taxi-v3 environment from Gymnasium[cite: 74, 83]. [cite_start]The primary objective is to explore to what extent model-free methods can approximate the theoretically optimal policy derived through Dynamic Programming[cite: 87].

## 🚕 Environment Description
[cite_start]The Taxi-v3 environment features a discrete observation space with 500 unique states[cite: 90, 91]. [cite_start]Each state represents a combination of the taxi's position, the passenger's location, and the destination[cite: 91]. 
* [cite_start]**Action Space:** Six discrete actions (moving south, north, east, west, picking up, and dropping off)[cite: 92].
* [cite_start]**Rewards:** -1 for each step taken, -10 for illegal pickup/dropoff attempts, and +20 for a successful passenger dropoff[cite: 93].

## 🤖 Algorithms Evaluated
1. **Dynamic Programming (Value Iteration):** Serves as the model-based baseline. [cite_start]It assumes full knowledge of the environment's transition dynamics and rewards to compute the optimal policy[cite: 84, 85].
2. [cite_start]**Q-Learning:** An off-policy temporal difference (TD) method that updates value estimates using the maximum possible future action value[cite: 100].
3. [cite_start]**SARSA:** An on-policy TD algorithm that updates estimates based on the actual action taken by the agent[cite: 101].

## ⚙️ Hyperparameters
[cite_start]A deliberate balance was maintained between exploration and convergence to ensure effective learning[cite: 104]:
* [cite_start]**Total Episodes:** 2000 [cite: 102]
* [cite_start]**Learning Rate:** 0.8 [cite: 102]
* [cite_start]**Gamma (γ):** 0.95 [cite: 102]
* [cite_start]**Epsilon (ε):** 0.1 [cite: 102]
* [cite_start]**N runs:** 20 (to average the Q-table across multiple seeds) [cite: 102]

## 📊 Results Summary
* [cite_start]**Q-Learning:** Displayed faster and more stable convergence, with the average reward stabilizing near 0 after fewer than 200 episodes[cite: 37, 38].
* [cite_start]**SARSA:** Showed a steep initial increase but had slower convergence due to its on-policy nature, remaining noisier as it considered exploratory behavior during learning[cite: 34, 36].
* [cite_start]**Conclusion:** While DP achieves the true optimal policy using the environment model, both Q-Learning and SARSA are highly capable of approximating it through interaction[cite: 77]. 

## 🚀 How to Run
1. Clone this repository to your local machine.
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
