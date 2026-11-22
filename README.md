# Mini-Project
Adaptive Congestion-Aware Routing in Software-Defined Networks Using Reinforcement Learning
Overview
This project simulates congestion-aware routing in a Software-Defined Networking (SDN) environment using a Deep Q-Network (DQN), a reinforcement-learning approach. A graph represents the network, and nodes are assigned congestion states. The agent learns to select routes from a source node to a destination while avoiding congested nodes and unnecessary loops.

The notebook demonstrates the agent under two network conditions:
- Low congestion: nodes have a lower probability of becoming congested.
- High congestion: nodes have a higher probability of becoming congested.
Project Objectives
- Model an SDN-style network topology as a graph.
- Simulate changing congestion conditions across network nodes.
- Train a reinforcement-learning agent to find routes from a source to a destination.
- Encourage successful routing and discourage congested paths and loops through reward and penalty values.
- Visualize the network topology and the agent's learning progress.
Technologies and Libraries
- Python 3.13
- NetworkX – network graph creation and path operations
- NumPy – numerical operations and state representation
- Matplotlib – network and learning-curve visualizations
- PyTorch – Deep Q-Network implementation and training
Project Structure
.
├── simulation-of-congestion-aware-sdn-via-q-learning.ipynb
└── README.md
Network Simulation
The notebook creates a network graph with 15 nodes, using a Waxman graph and additional edges. The example routing task uses:
- Start node: 12
- Destination node: 7
Nodes are visualized using colors:
- Red: congested node
- Green: non-congested node
The notebook generates congestion scenarios and checks that a valid route exists before running the agent.
Reinforcement Learning Approach
The notebook implements a Deep Q-Network (DQN) using PyTorch. The neural network contains two hidden layers with 128 units each.

The training setup includes:
- Training episodes: 3,000
- Optimizer: Adam
- Learning rate: 0.005
- Replay memory capacity: 2,000
- Batch size: 32
- Discount factor (gamma): 0.95
- Initial epsilon: 1.0
- Epsilon decay: 0.99
The reward design encourages the agent to reach the destination and discourages undesirable routing decisions:
- Reaching the destination: +100
- Loop penalty: -20
- Moving to a congested node: -30
- Ordinary step penalty: -1
Low- and High-Congestion Scenarios
The notebook trains and evaluates the routing agent in two scenarios:
1. Low congestion: approximately 35% probability of congestion for each eligible node.
2. High congestion: approximately 70% probability of congestion for each eligible node.
The notebook also plots the mean reward over training iterations for both scenarios. These plots help visualize how the agent's reward changes during training.
Installation
Install the required dependencies:
pip install networkx matplotlib numpy torch
Use Python 3.13 as specified in the notebook. A Jupyter Notebook environment is also required to run the .ipynb file.
How to Run
1. Clone or download this repository.
2. Install the dependencies listed above.
3. Open simulation-of-congestion-aware-sdn-via-q-learning.ipynb in Jupyter Notebook or JupyterLab.
4. Run the notebook cells in order.
5. Observe the network visualizations, training process, and reward plots for the low- and high-congestion scenarios.
Expected Outputs
- A graph visualization showing congested and non-congested network nodes.
- Training and route visualizations for the low-congestion scenario.
- Training and route visualizations for the high-congestion scenario.
- Learning curves showing mean average reward across iterations.
Notes
- The notebook uses randomly generated network and congestion states, so individual runs may produce different paths and reward curves.
- The notebook's implementation uses a Deep Q-Network (DQN). The project title contains “Q-Learning”; the implementation specifically uses a neural-network-based DQN approach.
- The plotted reward values are the values included in the notebook and should not be interpreted as guaranteed results for every run.
