# Project 2 - Continuous Control
## Training a DeepRL agent to solve the Unity Single-Agent Reacher task


The goal of this project is to train an agent to operate a double jointed robotic arm in a virtual world such that the arm maintains it's position in some target location. A reward of +0.1 is provided for each step that the agent's hand is in the goal location. A succesfully trained agent must get an average score of +30 over 100 consecutive episodes.


## Environment

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

## DDPG Architecture

To train the agent, I used the DDPG-pendulum example from the Udacity repository. My final network structure was:

- Fully connected layer - input: 33 (state size) output: 256
- Fully connected layer - input: 256 output 256
- Fully connected layer - input: 256 output: 4 (action size)

The hyperparameter selected were slightly different from the default model:

```bash
BUFFER_SIZE = 100000 #int(1e5)  # replay buffer size
BATCH_SIZE = 512 #128        # minibatch size
GAMMA = 0.95 #0.99            # discount factor
TAU = 1e-3              # for soft update of target parameters
LR_ACTOR = 0.001 #1e-4         # learning rate of the actor 
LR_CRITIC = 0.001 #1e-3        # learning rate of the critic
WEIGHT_DECAY = 1e-6 #0        # L2 weight decay

```
The Ornstein-Uhlenbeck noise has a sigma of **0.1**.

## Training Plot

The model was trained for 200 episodes but it was able to reach its target goal in just episodes. The score vs episode graph is shown bellow and it seems to be fairly stable.

![](reward_plot.png)

## Future Work
It would be interesting to see how batch normalization affects the model. Also, sampling the buffer might slightly improve the performance as well. It would also be interesting to see how extensively training the algorithm for large number of episodes would affect its performance.

