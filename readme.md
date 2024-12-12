# AI Snake Game

## Develop a Self-Learning AI Agent

Created an autonomous agent that uses Q-learning and reinforcement learning to play the Snake game by maximizing its score through food collection while avoiding wall collisions. 

By using a deep Q-learning network, the agent continuously improves its performance by learning from game states, actions, and rewards.

---

## Code Execution

Before running the program, create a virtual environment.

### Q-learning:

- *Execution*: Run Agent.py using the epsilon-greedy approach.
- *Description*:
  - Q-learning agent to play a basic Snake game using Pygame.
  - step(action): Takes an action (UP, DOWN, LEFT, RIGHT).
- *Reward System*:
  - +10 for eating food.
  - +1/-1 for moving closer to/farther from the food.
  - -10 for hitting walls or itself (game over).
- *Exploration and Exploitation*:
  - Balances exploration (random actions) and exploitation (choosing the best-known action) using epsilon-greedy:
    - Start with high exploration (EPSILON_START).
    - Gradually decay exploration using EPSILON_DECAY until reaching EPSILON_END.

- *Training Process*:
  - Runs multiple episodes of the game (EPISODES).
  - Trains the Q-learning agent by repeatedly playing and improving the Q-table.
  - At the end of training, plots the overall performance.

---

### Reinforcement Learning

- *Execution*: Download all files and run Agent.py to execute the program.

- *Reward System*:
  - +10 for eating food.
  - +1/-1 for moving closer to/farther from the food.
  - -10 for hitting walls or itself (game over).

- *Process*:
  1. Get the current state from the game.
  2. Use the agent's policy to decide on an action.
  3. Perform the action in the game, observe the reward, and the new state.
  4. Train the agent's short-term memory.
  5. Store the experience in replay memory.
  6. If the game ends:
      - Train on a batch of experiences from memory.
      - Save the model if it achieves a new high score.
      - Update and visualize training progress.

---

## Neural Network Details

### Linear_QNet:

- *Architecture*:
  - *Input Layer*: Takes the 11-dimensional state.
  - *Hidden Layer*: A dense layer with ReLU activation.
  - *Output Layer*: 3 neurons representing Q-values for the 3 possible actions.

- *Functionality*:
  - save: Saves the model's weights.

### QTrainer:

- *Purpose*:
  - Handles the training process using Adam optimizer and Mean Squared Error loss.

---

## Key Highlights

- The agent learns from its environment using experiences stored in replay memory.
- A neural network predicts Q-values for actions, optimizing them through training.
- The snake game provides a dynamic environment for the agent to learn navigation strategies.
