# Model-Based vs Model-Free Reinforcement Learning in the Taxi-v3

**Author:** Pavan Sriram Kodati  
**Institution:** University of the Pacific  
**Course:** COMP-293A-ON1-60142 (Reinforcement Learning)  
**Instructor:** Prof. Chadi El Kari  

## 📌 Project Overview
This project conducts a comparative analysis of model-based and model-free reinforcement learning algorithms within the classic Taxi-v3 environment from Gymnasium. The primary objective is to explore to what extent model-free methods can approximate the theoretically optimal policy derived through Dynamic Programming.

## 🚕 Environment Description
The Taxi-v3 environment features a discrete observation space with 500 unique states. Each state represents a combination of the taxi's position, the passenger's location, and the destination. 
* **Action Space:** Six discrete actions (moving south, north, east, west, picking up, and dropping off).
* **Rewards:** -1 for each step taken, -10 for illegal pickup/dropoff attempts, and +20 for a successful passenger dropoff.

## 🤖 Algorithms Evaluated
1. **Dynamic Programming (Value Iteration):** Serves as the model-based baseline. It assumes full knowledge of the environment's transition dynamics and rewards to compute the optimal policy.
2. **Q-Learning:** An off-policy temporal difference (TD) method that updates value estimates using the maximum possible future action value.
3. **SARSA:** An on-policy TD algorithm that updates estimates based on the actual action taken by the agent.

## ⚙️ Hyperparameters
A deliberate balance was maintained between exploration and convergence to ensure effective learning:
* **Total Episodes:** 2000
* **Learning Rate:** 0.8
* **Gamma (γ):** 0.95
* **Epsilon (ε):** 0.1
* **N runs:** 20 (to average the Q-table across multiple seeds)

## 📊 Results Summary
* **Q-Learning:** Displayed faster and more stable convergence, with the average reward stabilizing near 0 after fewer than 200 episodes.
* **SARSA:** Showed a steep initial increase but had slower convergence due to its on-policy nature, remaining noisier as it considered exploratory behavior during learning.
* **Conclusion:** While DP achieves the true optimal policy using the environment model, both Q-Learning and SARSA are highly capable of approximating it through interaction. 

## 🚀 How to Run
1. Clone this repository to your local machine.
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
